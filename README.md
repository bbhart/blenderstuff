Blender Stuff
=============

My student files for https://www.udemy.com/blenderenvironment and
https://www.youtube.com/playlist?list=PLjEaoINr3zgEq0u2MzVgAaHEBt--xLB6U. 

## Resources
* [Blend Swap](https://blendswap.com)
* [Poliigon](https://www.poliigon.com/)
* [HDRIHaven](https://hdrihaven.com/hdris)
* [HDR Labs](https://hdrlabs.com)
* [HDR Skies](https://hdr-skies.com) has... wait for it... HDR skies


## Current Issues (2.81 unless mentioned otherwise)

### Outstanding


### Resolved
1. ~~Renders happen twice. Sometimes the second pass it will render all my hidden stuff and then remove    it in the last moment before render completes. Other times the hidden stuff is there.~~ **Answer:** In View Layer, I checked `Render Single Layer` and that fixed it.
2. ~~HOW DO I MAKE IT NOT RENDER HIDDEN STUFF??? [1] IIRC older versions let you select item-by-item
   what would be shown in the viewport and in the render.~~ **Answer:** Click the Funnel icon in the 
   object organizer area (top right) and click `Disable in Renders`. This adds an icon to the organizer that you can then click to hide in the render. Shift-click to hide children, too.
3. ~~For my coffee mug and saucer, when transmission is 1 and roughness is 0, Blender is "helpfully"
    using [some sort of river rock texture](https://www.youtube.com/watch?v=TaRx-s5RH6Q) that 
    comes from who-knows-where. [This .blend file](https://github.com/bbhart/blenderstuff/blob/52cb4cbfa4dcebf28826a55b27d10801fd723888/donut-blender28/donut-and-coffee.blend) should show 
    the problem.~~ **Answer:** Seems this is by design. It projects a random HDRI background onto
    the mesh in Look Dev mode since it can't do the glass or transparent materials in this mode.
4. ~~When moving an object: even when I'm in axis restrict mode (e.g. only move on Y), Blender
    will still move on other axis if another object is encountered. I Do. Not. Want. This.
    I'd just hide the other object, but I need it to help me align. [Here's a video](https://www.youtube.com/watch?v=axg2Etkm6s4).~~ **Answer:** Unclick the magnet icon so it doesn't snap 
    during transform.

## Random notes

* Can't zoom in anymore? ~~Turn off Perspective Mode with numpad-5.~~ You're focused on the wrong object. Select the object you want to work with and then do `numpad-.`.
* To "bridge" empty faces (like on the coffee cup handle):
    * Delete the opposing faces
    * Select vertices on both sides (4 on each side if square/rectangular)
    * Hit F3 and look for Bridge Edge Loops
* Use Solidify modifier in object mode to give something thickness
* Use Subdivide Surface modifier to add geometry. You won't have your faces on both sides, though, 
  until you apply it.

## "Creating the coffee"
_Documenting this on its own since it gave me problems._
* Make sure you've applied your Subdivide Surface. This will let you select inside faces.
* Double-check that the bottom normals are facing up (blue). 
    * Can check in Viewport Overlays -> Face Orientation. Blue is good, red is bad. 
    * If bad, then select and recalculate normals.
* Use your favorite method to select faces within the cup. (I used circle select)
* Shift-D to duplicate.
* P to separate (by Selection)

## Adding the denoiser
1. Go to Compositing tab.
1. Click Use Nodes.
1. Shift-A and add Denoise.
1. On View Layer Properties panel on the right, click Denoising Data.
1. From Render Layers to Denoise, connect Noisy Image to Image, Denoising Normal to Normal, Denoising Albedo to Albedo. 
1. Connect Denoise image output to composite image.
1. Re-render.

## Rigid Body stuff
* If you increase the number of frames for animation, you also need to increase the rigid body cache size.
    * Scene -> Rigid Body World -> Cache, then bump up the End.
* You need to actually run the animation once so Blender can simulate the physics. Otherwise you end up with animation that
    stops in the middle somewhere. 
* To connect two rigid body objects together, select both and then use the Object menu -> Rigid Body -> Connect.
* To make an object stationary in the rigid body simulation, select it and uncheck Dynamic under Physics properties.
* Meshes not interacting like you'd expect? Make sure you apply your scaling. 

## Other Stumbling Blocks
* Weird shit happening when moving vertices? Check your Proportional Editing setting


