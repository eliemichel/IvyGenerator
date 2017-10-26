An Ivy Generator
================

This is mostly the code from Thomas Luft's IvyGenerator, as available on [its official website](http://graphics.uni-konstanz.de/~luft/ivy_generator/) as of October 26th, 2017.

Like the original code, all the changes available here are released under the GPLv2 license (see LICENSE file). This version also relies on glm, which follows the so-called "Happy Bunny License" (a modified MIT License).


Releases
--------

The upstream project stopped at version 1.3. I numbered my releases accordingly.

### v1.4

The initial motivation for this new release, and for this whole fork actually, was that the viewport was mirrored in the original program. So I mostly fixed this, but in order to be able to build this version I also cleaned up the code so that it can work using Qt5, CMake as a build system, glad instead of glee, glm instead of GLUT and some other minor fixes.

[Download IvyGenerator v1.4](https://github.com/eliemichel/IvyGenerator/releases/tag/v1.4)

Builds are available for Windows 64bit. I my add binaries for linux any time soon, but would need some external help for OSX.


Contact
-------

 * thomas.luft@web.de
 * elie.michel@exppad.com


Usage
-----

Import your obj+mtl scene, double-click to place the ivy root,
press "grow", and enjoy watching the ivy growing! Press "birth"
to generate the full geometry. Use the export function to save
your ivy geometry as obj+mtl for usage in your 3d world.
Please triangulate your obj scene before loading it, and keep
your scenes simple, since the growing process slows down in
complex scenes heavily. In case your ivy is growing inside your
objects, use the "flip normals" button to flip the surface
normals of your objects. You can customize your ivy using the
provided settings - tool-tips will help you to understand
the settings.


### Camera controls

rotate - left mouse button
track - left mouse button + control
dolly - right mouse button
orbit - left mouse button + shift

