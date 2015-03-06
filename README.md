# DankMemesDemo

A quick example workflow of using 2D art assets in Three.js.

Specifically, this workflow tests to see if Three.js and Blender can be used to animate armatures in 2D, as well as create a scene of 2D images with parallax.

## About the demo

[Try in now](http://willy-vvu.github.io/DankMemesDemo/Step%204/) in the browser! Use the arrow keys to move.

During the walking and landing animation, there is some strange scaling and moving that occurs. I'm not sure what's causing this, but oh well.

## Step 1 - Art

The process starts with 2D art assets. I've filled the Step 1 folder with the reference material I used. The images can come in any source: drawn on a graphics tablet, photographs of real-world art, or in my case, screenshots.

## Step 2 - Slicing and Texture packing

In this step, the art from before is sliced into its component parts and packed into textures. If the artists can create the art in multiple parts to begin with, this step will be made quite easy.

You'll need to know that:
- *Packed textures must be square, and have both width and height being a power of 2.*
- Transparency is key. Make sure you know how to work with transparent images.

Software I used:
- GIMP 2: GIMP is where I spent the most time. I specifically used it for separating background from foreground as well as slicing and rebuilding parts of images. Splitting Aurora into multiple parts proved challenging, as I drew from various source artworks and tried to cut parts in a way that would recombine to a reasonable effect.
- Inkscape: Inkscape helps combine multiple separate images into one image, while preserving the original images. I used this to combine and arrange the backdrop layers into a packed texture after I split them up with GIMP.

## Step 3 - Arranging and Animating

After the art has been sliced and packed into textures, it's time to put it back together again, but animated and in 3D! I spent all my time in this step in Blender.

You'll need to know how to:
- Create and edit meshes
- UV unwrap
- Create and animate armatures
- *Sort the faces of the animated mesh*
- *Adjust face normals of a mesh*
- Export your models in the Three.js format

## Step 4 - Importing into the Browser

With exported, game-ready 3D models, it's time to write the code to see it in action.

*Note: You'll need to start a server to view Step 4 properly if you've downloaded the project locally.* An easy way to do this is to with Python 3.x is to run `python -m http.server`, which will start a server on port 8000. You can then head to `localhost:8000/Step 4` in your browser to see it in action.

You'll need to know how to:
- Start a simple server
- Import Scenes using `THREE.ObjectLoader` and Meshes using `THREE.JSONLoader`
- Use `THREE.SkinnedMesh` and `THREE.Animation`
- Blend between animations using animation weights
- Create transparent materials with textures *- make sure to check the normals and sort faces from Step 3, or else the faces may not show up!*

And, that's it! Go make some awesome interactives with art.
