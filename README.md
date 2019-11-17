Blender Stuff
=============

My student files for https://www.udemy.com/blenderenvironment and
https://www.youtube.com/playlist?list=PLjEaoINr3zgEq0u2MzVgAaHEBt--xLB6U. 

## Current Issues (2.81 unless mentioned otherwise)

1. Renders happen twice. Somtimes the second pass it will render all my hidden stuff and then remove    it in the last moment before render completes. Other times the hidden stuff is there.
2. HOW DO I MAKE IT NOT RENDER ALL THE HIDDEN STUFF??? [1]
3. For my coffee mug and saucer, when transmission is 1 and roughness is 0, Blender is "helpfully"
    using some sort of river rock texture that comes from who-knows where.
4. When moving an object: even when I'm in axis restrict mode (e.g. only move on Y), Blender
    will still move on other axis if an object is encountered. I Do. Not. Want. This.

## Random notes

* Can't zoom in anymore? Turn off Perspective Mode with numpad-5.
* To "bridge" empty faces (like on the coffee cup handle):
    * Delete the opposing faces
    * Select vertices on both sides (4 on each side if square/rectangular)
    * Hit F3 and look for Bridge Edge Loops
* Use Solidify modifier in object mode to give something thickness
* Use Subdivide Surface modifier to add geometry

## "Creating the coffee"
_Documenting this on its own since it gave me problems._
* Make sure you've applied your Subdivide Surface. This will let you select inside faces.
* Double-check that the bottom normals are facing up (blue). 
    * Can check in Viewport Overlays -> Face Orientation. Blue is good, red is bad. 
    * If bad, then select and recalculate normals.
* Use your favorite method to select faces within the cup. (I used circle select)
* Shift-D to duplicate.
* P to separate (by Selection)

## Other Stumbling Blocks
* Weird shit happening when moving vertices? Check your Proportional Editing setting


[1]
![not hidden](donut-blender28/renders/please-please-dont-render-hidden-objects.png)
