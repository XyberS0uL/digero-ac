GoArrow displays an arrow on your screen that points towards coordinates that you specify. This is very handy if you have to run to coordinates with obstacles in the way (like mountains), or if you're just directionally-challenged, like me =D

GoArrow has the ability to find a route between any two locations in Dereth, as well as look up locations' details from either the [Crossroads of Dereth atlas](http://ac.warcry.com/atlas/search.php) or the [ACSpedia atlas](http://www.acspedia.com/).

GoArrow also has an interactive surface map and can display maps from [ACMaps](http://www.acmaps.com/) for any dungeon.

## Download ##
[GoArrow v1.2.0.1](http://digero-ac.googlecode.com/files/GoArrow_v1.2.0.1.msi)

Updates for the map and route finder (download these after installing GoArrow):
  * [Updated map of Dereth](http://digero-ac.googlecode.com/files/DerethMap.zip) (replace `DerethMap.zip` in the GoArrow folder)
  * [Updated MapRegions.xml](http://digero-ac.googlecode.com/files/MapRegions.xml) (save it to the GoArrow folder)

## Screenshots ##
### GoArrow Toolbar ###
> ![http://digero-ac.googlecode.com/svn/wiki/screenshots/goarrow/goarrow_toolbar.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/goarrow/goarrow_toolbar.gif)

### Arrow ###
> ![http://digero-ac.googlecode.com/svn/wiki/screenshots/goarrow/goarrow_arrow.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/goarrow/goarrow_arrow.gif)
> ![http://digero-ac.googlecode.com/svn/wiki/screenshots/goarrow_ani.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/goarrow_ani.gif)

### World Map ###
> ![http://digero-ac.googlecode.com/svn/wiki/screenshots/goarrow/goarrow_dereth-map.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/goarrow/goarrow_dereth-map.gif)

### HUD Settings ###
> ![http://digero-ac.googlecode.com/svn/wiki/screenshots/goarrow/goarrow_0-0.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/goarrow/goarrow_0-0.gif)
> ![http://digero-ac.googlecode.com/svn/wiki/screenshots/goarrow/goarrow_0-1.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/goarrow/goarrow_0-1.gif)
> ![http://digero-ac.googlecode.com/svn/wiki/screenshots/goarrow/goarrow_0-2.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/goarrow/goarrow_0-2.gif)

### Atlas and Route Finding ###
> ![http://digero-ac.googlecode.com/svn/wiki/screenshots/goarrow/goarrow_1-0.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/goarrow/goarrow_1-0.gif)
> ![http://digero-ac.googlecode.com/svn/wiki/screenshots/goarrow/goarrow_1-1.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/goarrow/goarrow_1-1.gif)
> ![http://digero-ac.googlecode.com/svn/wiki/screenshots/goarrow/goarrow_1-2-0.gif](http://digero-ac.googlecode.com/svn/wiki/screenshots/goarrow/goarrow_1-2-0.gif)

## Notes ##
  * When entering coordinates, you can enter pretty much any text as long as it contains coordinates somewhere. For instance, you can paste the entire string: `Jim tells you, "Menhir Ring 4 :: 44.7N, 80.9W (relative to me: 1.2S, 0.3E)"` and GoArrow will pick out the first set of coordinates it finds (44.7N, 80.9W).

  * The lists of locations on the Search, Route, Favorites, and Recent tabs respond the same way to mouse clicks:
    * Click on the name or coords to see the location's details.
    * Ctrl+Click on the name or coords to set the location as the route end.
    * Shift+Click on the name or coords to set the location as the route start.
    * Click on the GoArrow icon on the right to set the arrow's destination coordinates.
    * Click on the location's icon on the left to remove the location from the list.

  * Unlike Oracle of Dereth and Navi III's route-finding algorithms, GoArrow's algorithm works faster with more start locations enabled.

  * The "Here" button is very useful for setting a waypoint inside of a dungeon, where AC won't tell you the coordinates. Be sure to turn on "Show Arrow Indoors" if you want to use the arrow in a dungeon.

  * You can pick which mouse buttons you use to control the maps on the HUDs > Dereth and HUDs > Dungeon tabs.

  * When zooming on a map, the point under the mouse cursor will be kept in the same spot on the screen. That way, you can put the mouse over the point you want to zoom to and zoom directly into it.
> There are two exceptions to this:
    1. If the Dereth Map is centered on the player, zooming in will keep it centered on the player.
    1. If you hold down Shift or Control, the map will stay centered on the point where it's currently centered.

## Source Code ##
The source code for GoArrow is available from the [GoArrow project on GoogleCode](http://goarrow.googlecode.com).