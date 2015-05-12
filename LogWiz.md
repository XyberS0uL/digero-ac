LogWiz creates logs of chat text in either plain text or full color. You can choose which types messages it logs, add timestamps to every line of the log, make separate logs for each character, choose which characters it will log for and more. It will make a new log file each day so you don't have huge logs to sort through.

## Download ##
[LogWiz v2.0.0.0](http://digero-ac.googlecode.com/files/LogWiz_v2.0.0.0.msi)

## Screenshots ##
![http://digero-ac.googlecode.com/svn/wiki/screenshots/logwiz1.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/logwiz1.gif)
![http://digero-ac.googlecode.com/svn/wiki/screenshots/logwiz2.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/logwiz2.gif)

## Notes ##
  * Logs are stored in the `Logs` directory under the plugin's installation folder. Remember where you install it! Default is `C:\Program Files\Decal Plugins\LogWiz`

  * To view XML logs, open them in a web browser, such as Internet Explorer or Firefox.

  * If you plan to dual log in AC, be sure to use the XML logging option instead of text.

  * Type `/logwiz help` for a list of chat commands.

  * The "stealth mode" option will remove the LogWiz window from Decal, and disable any chat messages from the plugin, including errors (these messages will still be written in the log). LogWiz will still respond to chat commands, and will still be visible in the Decal Agent, where you enable/disable plugins. Type `/logwiz stealth off` to disable stealth mode.

  * For advanced users: LogWiz uses an XSLT file to display the XML logs. This file is in the Logs/