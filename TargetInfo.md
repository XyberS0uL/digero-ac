Target Info tells you what monsters have had debuffs cast on them, regardless of who cast them. You just have to be around when the vuln is cast. This is very useful in a fellow, where you have a few mages casting vulns at the same time. Makes avoiding those annoying recasts easier!!

It displays the vulns in an onscreen HUD for the creature or player you currently have selected. You can cycle through vulned or nonvulned monsters (and/or players) using hotkeys you define with DHS.

The plugin can also recommend which vulns to cast on your target, using the data from Crossroad of Dereth's creature database.

## Download ##
[Target Info v3.1.1 Alpha](http://digero-ac.googlecode.com/files/Target_Info_v3.1.1%20Alpha.msi)

## Screenshots ##
![http://digero-ac.googlecode.com/svn/wiki/screenshots/target_info_HUD_Attached.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/target_info_HUD_Attached.gif)
![http://digero-ac.googlecode.com/svn/wiki/screenshots/target_info_HUD_Icons_Only.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/target_info_HUD_Icons_Only.gif)

![http://digero-ac.googlecode.com/svn/wiki/screenshots/target_info_0.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/target_info_0.gif)
![http://digero-ac.googlecode.com/svn/wiki/screenshots/target_info_4.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/target_info_4.gif)
![http://digero-ac.googlecode.com/svn/wiki/screenshots/target_info_5.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/target_info_5.gif)
![http://digero-ac.googlecode.com/svn/wiki/screenshots/target_info_6.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/target_info_6.gif)

## Notes ##
  * To move the HUD, just click and drag it to where you'd like it to be.

  * The Range on the Cycle tab is measured in AC-"yards" (or "meters" if you have a non-US version; they're the same length in AC). The edge of the indoor radar is 25 yards, and the outdoor radar is 75 yards.

  * Cycling vulned/non-vulned creatures should work just like cycling monsters or items does with the regular AC interface, except that you can define your own custom max range which may not necessarily be the edge of the radar.

  * Clearing the vulns on a creature/player is useful if their debuffs get dispeled. There's no way for Target Info to be able to tell exactly which debuffs were removed when the dispel particle effect plays, so this command remains manual. You can access it through the button, a hotkey, or the command `/tinfo clearsel`.

  * Type `/tinfo help` for a list of available chat commands.

  * The recommended vulns database is provided by [/http://ac.warcry.com/compendium/creature/ Crossroads of Dereth]. If you notice any incorrect or outdated information, let CoD know!

  * Target Info uses the spellwords that people say to make a (very good) guess of what debuff was cast in the event that the particle effect is ambiguous (like Bludge Vuln and Imperil). You do not need to unfilter spellwords if you have them filtered.

> If Target Info can't make a good guess, or if the spell was cast by a monster (who don't say spell words), the plugin will revert to the groups that it used in v2.8.8 and earlier.

  * This plugin was originally written by Jer. Since he no longer plays AC and doesn't develop his plugins any more, I've decided to take up working on Target Info and a few other of his plugins.

## Features in Concept ##
  * A list of Monsters/Players that have vulns or debuffs cast on them, showing what's cast on them, their distance, etc. Also perhaps a list of non-vulned creatures

  * The ability to customize what Target Info considers "debuffed," for the purpose of cycling or displaying them in the list. This would be helpful if you're with another mage and casting say, piercing vuln while the other mage is casting imperil. Or, if you're a melee/archer attacking creatures that are debuffed for your damage type.

## Known Issues ##
  * If you have a background enabled for a HUD, its size "lags" behind the HUD's actual size by 1 second. Set the HUD background color to "clear" to get rid of the background for now.

  * The self vuln HUD is currently broken and doesn't work.