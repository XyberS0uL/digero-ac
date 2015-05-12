Media Control allows you to control Windows Media Player (and others) from within AC. It provides functionality similar to multimedia keyboards, with buttons for Play/Pause, Stop, Fwd, Bkwd, and Volume. It doesn't actually interface with the player, so it can't tell you what song is playing or let you edit a playlist.

Media Control has DHS support, so you can assign hotkeys to the various functions.

## Download ##
[Media Control v1.1.0.0](http://digero-ac.googlecode.com/files/Media_Control_v1.1.0.0.msi)

## Screenshot ##
![http://digero-ac.googlecode.com/svn/wiki/screenshots/media_control.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/media_control.gif)

## Notes ##
  * If you have Decal Hotkey System installed, you can set up hotkeys for the various functions of Media Control.

  * **Other Players:** _Add these to PlayerApps.ini in the Media Control folder. Only add the ones you plan to use._
    * iTunes **// iTunes**
    * {DA7CD0DE-1602-45e6-89A1-C2CA151E008E} **// foobar2000**
    * PlayerCanvas **// Quintessential Player**
> More to come as they're requested.

  * You can add support for other media players in Media Control, provided that they respond to Windows Messages for Play/Pause, etc. Adding a new media player is not trivial. You need to find the player window's class name, then add that to PlayerApps.ini in the Media Control folder. You can use a program like Spy++ to find the class name. (I don't believe it's available for free -- it comes packaged with Visual Studio).
> Your best bet is to ask me to try to find the class name for another media player =)

## Known Bugs ##
There's a problem with the view icon that causes it to have a cyan background instead of transparent.