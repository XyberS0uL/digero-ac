Quest Timer keeps track of quests you've completed, and when you'll be able to complete them again. It will automatically start quest timers based on triggers you can download or define yourself. You can store your quests online and access them from any computer you play AC
on, or see your timers out-of-game. Quest Timer will also download new quests
as they are submitted to my site, to keep you up to date with the latest quest
timers!

## Download ##
[Quest Timer v2.4.2 Alpha](http://digero-ac.googlecode.com/files/Quest_Timer_v2.4.2%20Alpha.msi)

## Tab Descriptions ##
### Quests ###
> This tab is pretty straightforward. Click on any of the quest names to sort by name, or the time left to sort by that. Click Edit to bring up the Add/Edit tab with that quest's info for editing. Hold down CTRL and click the red X to delete the quest.

> ![http://digero-ac.googlecode.com/svn/wiki/screenshots/quest_timer-1.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/quest_timer-1.gif)

### Notes ###
> On this tab, you can view/add notes for quests. Click Copy to copy the note to the clipboard, /say to say the note outloud, and /f to say the note to your fellowship. You'll need to hold CTRL when clicking the X to delete the note.

> You can also get to this tab by typing `/qtimer notes [quest name]` (quest name is optional). If you don't specify a quest name, it'll just show notes for the currently selected quest.

> ![http://digero-ac.googlecode.com/svn/wiki/screenshots/quest_timer-2.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/quest_timer-2.gif)

### Add/Edit Quest ###
> Use this tab to add a new quest or edit an existing one. If you enter the name of an existing quest and haven't started adding any triggers or length info, Quest Timer will automatically fill in the existing information so you can edit it. When typing the dates and times, simply enter them in your local format. To verify that you typed the correct format, Quest Timer will convert the date to the Month Day, Year format in the edit box.

> ![http://digero-ac.googlecode.com/svn/wiki/screenshots/quest_timer-3.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/quest_timer-3.gif)

### Other Characters ###
> On this tab you can view the quest timers for the other characters in your quest file. Characters will only show up in this list if they have completed a quest.

> ![http://digero-ac.googlecode.com/svn/wiki/screenshots/quest_timer-4.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/quest_timer-4.gif)

### Internet > Available Quests ###
> If you specify on the options tab to download new quests, this will show the quests that have been downloaded. Any quests that are new since you last checked for new quests will be green. Click the blue + to add a quest to your list, or View to review/edit the quest information before adding it. Click any of the first three columns to sort by that column (i.e., click on a quest's name to sort by name, etc)

> If you want to reset the list and download all of the available quests again, type `/qtimer checknew reset`

> ![http://digero-ac.googlecode.com/svn/wiki/screenshots/quest_timer-5.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/quest_timer-5.gif)

### Internet > Submit Quests ###
> Here you can select quests from your quest file to submit to the server. Quests in your file are checked against the list of downloaded quests. If they don't exist, they will appear green; if they do exist, but with different trigger/duration data, they will appear yellow; and if the exist with the same info, they will appear red. See the Notes section for more info.

> ![http://digero-ac.googlecode.com/svn/wiki/screenshots/quest_timer-6.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/quest_timer-6.gif)

### Internet > Settings ###
> You can turn on/off the various internet functions of Quest Timer. If you have a custom site to handle uploading or downloading, enter the URL here. (See the Notes section for info on how to upload to multiple sites).

> Since all characters share one quest file, the only good way for the server to keep track of which file to save/get when uploading/downloading is a username and password. **Do not use a sensitive password!** The password is sent and stored unencrypted.

> ![http://digero-ac.googlecode.com/svn/wiki/screenshots/quest_timer-8.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/quest_timer-8.gif)

### Settings ###
> You can turn on/off the various functions of Quest Timer.

> ![http://digero-ac.googlecode.com/svn/wiki/screenshots/quest_timer-7.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/quest_timer-7.gif)

## Notes ##
  * Since all characters share the same quest file, when you delete a quest with one character, it will be deleted for all other characters, and any timer info and notes will be lost

  * You can use the wildcards `* ? #` to match arbitrary letters/numbers, and the pipe `|` as an "OR" for matching multiple different names.
    * `*` matches zero or more of any letter or number
    * `?` matches exactly one letter or number
    * `#` matches any single digit (0-9)
    * `|` is used to separate different complete names and match any one of them (don’t put spaces between the name and the pipe)

> For example, `*Gem of Enlightenment|*Gem of Forgetfulness` will match any of the gems in the Skill Change Quest; however, `*Gem of Enlightenment|Forgetfulness` will not.

  * Quest Timer supports the ability to merge quest definitions from other people with yours. For example, you can download all of the quests in this site's quest database as a merge file. When you get a merge file, save it in the Quest Timer folder and name it `merge_quests.xml`. Next time you log in, Quest Timer will instruct you how to merge it.
> If when merging quests, you have multiple copies of the same quest with different names, you can either delete the new ones or use the Converter program (outside AC) to move your timers under the new quest name and delete the old one.

  * In order to improve performance, I recommend that you don't simply add all of the quests that are available on the Internet tab. There are over 300 quests available for download, but I recommend you look through the list and choose the ones you plan to use. If you ever decide you want a quest later, it'll still be there on the Internet tab. When you delete a quest that you had added from the Internet tab, it'll reappear there so you can add it back later if you choose.

  * If you want a quest timer to only be triggered if you pick up an item from a specific corpse or chest, enter the item's name for 'Pickup' and the corpse or chest name (including 'Corpse of' for corpses) for 'Chest/Corpse.' The timer will only be started if you pick up that item while the corpse or chest is open. This is useful for a quest where the item you loot is droppable (instead of setting the "droppable" flag, which doesn't work very well).

  * You may want to upload your quests to additional sites -- for instance, you use my site to store your file, but your clan's site to see the timer info. To do this, open the settings.xml file and follow the instructions in the comment under `<AdditionalUploadURLs>`

  * To specify a different site to handle downloading or submitting new quests, change the `QuestDatabaseURL` field in settings.xml