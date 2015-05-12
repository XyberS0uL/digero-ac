## Tell me about your site! ##
If you have a site that communicates with Quest Timer, [let me know](http://vnboards.ign.com/pm_send.asp?usr=729875)! I'd love to see it =)

## Store quests on your own site ##
If you'd rather use your own site than mine to store your Quest Timer info, you'll need to have a server that supports server-side scripting (e.g. PHP, ASP). It's also much easier to deal with if you have access to a SQL database, but it's also doable by saving the Quest XMLs as files on your server. All of my examples use a SQL database. For convenience, you can see the ~~SQL table structures~~.

I've made the ~~PHP source code~~ available for some relevant pages. Each section below also contains a link to the source code for the specific page that section deals with.

In order to keep the URLs simple in the plugin, I used a switch statement in quest\_timer.php to deal with the request depending on the mode: ~~View the code~~


## Request Protocol (from the plugin) ##
Quest Timer makes all of its requests with `POST`. Every request contains the following:
| `mode` | Mode can be: `loadquests`, `savequests`, `newquests`, `submitquests`, (or `plugininfo`, which is sent only to my site) |
|:-------|:-----------------------------------------------------------------------------------------------------------------------|
| `currrentcharacter` | The name of the current character |
| `currentworld` | The world that the current character is on |
| `currentguid` | The GUID of the current character (in decimal, not hex) |
| `acctchars` | A comma-delimited list of characters that are currently in the XML (including the current character, even if they're not listed in the XML), in the format: `Name [Server]` |
| `gmtoffset` | The timezone offset for the user's computer (e.g. `-0500` for EST) |
| `currenttime` | The **GMT** date on the client's computer |
| `plugin` | `Quest Timer` |
| `plugin_ver` | Major.Minor.Revision (e.g. `2.2.0`) |
| `random` | A random number to prevent caching (ignore this) |


## Response Protocol (from the server) ##
_All responses must be in XML format!_

Quest Timer verifies that the response was what it was expecting by checking the root tag's name. The root element is the outermost element. There can be only one root element per XML document. Tags can either be written `<tag></tag>` or `<tag/>`. The second is just shorthand for the first that can be used when the element contains no child nodes. Remember that XML is _case-sensitive_.

Each mode has specific tag name(s) it checks for, but there are a few things that are the same for every mode:

To report an error to Quest Timer: `<error reason="" />` (remember the closing slash!)
The error tag must be the root element of the response.

To have Quest Timer display a note from the server, add a comment outside the root element, with "Note:" as its first 5 characters: `<!-- Note: blah -->` You can have up to 10 notes, each up to 200 characters long.

## Save (Store) Quests ##
The mode for this is `savequests`. In addition to the common request arguments, a `savequests` request contains:
| `username` | This is so your site can uniquely identify who's sending the file. |
|:-----------|:-------------------------------------------------------------------|
| `password` | The supplied password. |
| `lastmodified` | The **GMT** date that the quest file was last modified by the plugin. This is in the format `yyyy-mm-dd hh:mm:ss` (e.g. `2007-09-26 11:29:11`) |
| `uploadct` | The number of times the plugin has uploaded the file, or `-1` if no checking is to be performed. |
| `compare_merge` | See below for more info. |
| `questxml` | The actual XML file as a string. |

If `uploadct` is not provided OR `-1`, do not check against the quest file's upload count. Otherwise, if the provided uploadct is less than the number of times that the file has been uploaded according to the server (which would indicate that the quest file was uploaded from another computer), return `<OldFile/>`.

Every success response should include `uploadct="[Num Uploads]"` as an attribute of the root tag (e.g.: `<Success uploadct="7"/>`). Increment `uploadct` before returning it to the plugin. The plugin does nothing with this value except store it and give it back to the server with the next `savequests` request.

`compare_merge` can take on 3 different values:
<table cellpadding='5' border='1'>
<tr><td><code>NONE</code></td><td>Do not perform any checking (this is how my server script behaved before v2.3.1).</td></tr>
<tr><td><code>COMPARE</code></td><td>Check for discrepancies in the info for characters <b>other than the current one</b>.<br>
<br>
If there are discrepancies, return <code>&lt;OtherCharMismatch/&gt;</code> and <b>DO NOT</b> update the file on the server.<br>
<br>
Otherwise, continue as normal and return <code>&lt;Success uploadct=""/&gt;</code>.</td></tr>
<tr><td><code>MERGE</code></td><td>Check for discrepancies in the info for characters <b>other than the current one</b>.<br>
<br>
If there are discrepancies, use the uploaded data for the current character and the server database's info for all other characters, then return<br>
<br>
<pre><code>&lt;Merged uploadct="" restoredquests=""&gt;<br>
    &lt;Quests&gt;    ┐<br>
        ...     ├── The updated quest file<br>
    &lt;/Quests&gt;   ┘<br>
&lt;/Merged&gt;<br>
</code></pre>

In the case where a quest was deleted in the uploaded file, but has active timers for other chars, put it back in the file. <code>restoredquests=""</code> should have a comma-delimited list of the quests that were restored.<br>
<br>
Otherwise, continue as normal and return <code>&lt;Success uploadct=""/&gt;</code>.</td></tr>
</table>

To recap, the root tag of the response can be any of the following:
  * `<OldFile/>`
  * `<OtherCharMismatch/>`
  * `<Merged uploadct="" restoredquests=""><Quests>...</Quests></Merged>`
  * `<Success uploadct=""/>`
  * `<error reason=""/>`

View source for: ~~savequests.php~~

Uploading should continue to work fine if your server script does not implement the new features. Quest Timer still treats the old response of `<Success/>` the same as it did before. Also, if you do update your script, be sure that it'll still work with old versions of Quest Timer. Check if the new arguements were actually passed to the script, or check the plugin version.

## Load (Fetch) Quests ##
The mode for this is `loadquests`. In addition to the common request arguments, a `loadquests` request contains:
| `username` | This is so your site can uniquely identify who's sending the file. |
|:-----------|:-------------------------------------------------------------------|
| `password` | The supplied password. |
| `lastmodified` | The **GMT** date that the quest file was last modified by the plugin. This is in the format `yyyy-mm-dd hh:mm:ss` (e.g. `2007-09-26 11:29:11`) |

The response will either be the quests.xml document as it was sent to the server (with `<Quests>` as the root tag), or if the `lastmodified` date is newer or equal to the date that was sent when last saving, the response should simply be `<OldFile/>`. If the user has chosen to download the quests file even if the one on the server is older, the `lastmodified` date will be `1990-1-1 00:00:00`.

Return the `uploadct` in a comment outside the root tag, in the format `<!-- uploadct = 5 -->`

View source for: ~~loadquests.php~~

## Quest Database ##
I won't give detailed instructions on this, since it's unlikely that anyone will make a new quest database, but you can view the code if you'd like.

View source for: ~~newquests.php~~ and ~~submitquests.php~~ (for communication with the plugin)

View source for: ~~qt\_viewquests.php~~ (for users adding quests: ~~this page~~)

## Viewing Timers Online ##
The way I did this is probably more complicated than you need. Feel free to try to figure out the source. It has a few comments ;-)

View source for: ~~qt\_viewtimers.php~~

## Note about PHP ##
Just to clear up some confusion if you don't know PHP and plan to write your scripts in another language. In some strings, you might see something like:
  * `"Username $username was created"`
`$username` is a variable, and that's just a shorthand way of writing something like
  * `"Username " . $username . " was created"`

Similarly, when accessing arrays, the following are equivalent:
  * `"Username $data[username] was created"`
  * `"Username " . $data['username'] . " was created"`