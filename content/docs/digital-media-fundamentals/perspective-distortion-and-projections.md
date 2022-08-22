---
title: Perspective Distortion and Projections
draft: false
---
# Notes on Perspective Distortion and Projections

The term “distortion” can be somewhat misleading, because the optical phenomenon of perspective distortion simulates our expectations  - and how our own eyes work. I like the term because it is accurate, a shift in scale relative to distance is a distortion certainly, and it gently reminds us not to get too caught into paradigms of real world cameras, or not to take it for granted.

The angle, or zoomed-in-ness, of a lens is measured two ways. The first is with an angle of the field of view. This is how game engines usually work. Many games let us change the field of view. On actual lenses, it’s measured in millimeters. Which is a strange unit. The mm measurement is the distance between the optical center of the lens and the image sensor. The lower the mm number, the wider the lens. (“zoomed out”). The bigger the number, the more “reach” this “telephoto” lens has. “zoomed in”.
Wide angle lenses refer to lenses that typically produce images with more dramatic perspective distortion than our human vision. (fisheye, 9 – 34mm). Normal lenses refer to lenses where the perspective distortion is unremarkable, considering “normal” human vision (35-70mm), and telephoto is any lens more zoomed in than normal.

Those mm generalities refer to 35mm film lenses or full frame cameras. Other sensor size lenses may show an “equivalent” mm marking, just so photographers understand what to expect if it were on a 35mm film camera body, as our “scale”. This scale of using these mm measurements of 35mm film cameras (in digital, we call them “full frame” cameras) is so universal, 3D modeling software, rendering software, and game engines will use this measurement instead of (or along side) the more pedantically accurate “horizontal field of view” (FOV) measurement.

![Screenshot of unity scene with perspective camera](/images/digital-media/perspec1.png)

*A unity scene with a perspective camera. Note that the blue and red spheres appear further away, and the green sphere takes up about twice as much area as the blue.*

![Screenshot of unity scene with orthographic camera](/images/digital-media/perspec2.png)

*The exact same scene with an orthographic camera. The spheres distance from the camera is irrelevant. Note how you can no longer see the left side of the cube.*

Unity’s Camera Component has a checkbox that lets you choose between a FOV slider, or choose a “physical camera” that gives you the ability to adjust the mm focal length measurement. They both just change the field of view.
It’s important to know that the lens width doesn’t affect the perspective distortion in the slightest.
No matter how far you zoom in, the image taken doesn’t change. It just crops.

No, seriously. Lens choice is simply cropping the image. Two photos shot from the same place of the same subject with wider or more telephoto lenses. The relative size of all the objects in the image will be the same. One image will show more of the scene, and all objects may all be smaller within that frame. But if you took the telephoto image, cropped to the same frame size, and expanded it to match, they would be the same image.

A reason some photographers like resolution – and spend lots of money on high megapixel cameras (even though final images often don’t use a fraction of that data) is freedom to crop in a bit after the fact, and to shoot a bit wider than the scene. Although for other optical distortion and pixel processing reasons this isn’t “as good” as “getting it right in camera”.

**Perspective Projection** is, in computer graphics, probably referring to how a virtual camera, in a virtual 3D scene, behaves like we expect regular cameras to behave (in terms of perspective distortion). Things look right. Problem is, this can make doing a lot of things in 3D difficult, particularly as we interface with 3D scenes with 2D screens.

**Orthographic projection** is different. It has no perspective distortion.

In a 3D environment, orthographic projection allows us to look at the world as if it were 2D, only on two axis, the third axis sort of compressed, or whatever color is closest to the camera will show up, basically.

It’s like holding up a picture frame to the world, and running forward, sandwiching everything in. Draw a bunch of parallel straight lines out (perpendicular to your picture frame), and the first color they hit is the color of that, uh, “pixel”. Doesn’t matter how far or how close something is to the camera.

For 3D modeling, and working in 3D space, its often extremely useful to switch to orthographic projection and move and manipulate objects in 2D (like top-down, arranging aligning house 3d models on a street).

**Isometric Projection** is a certain kind of orthographic projection, with certain angles of the camera. It tends to be smart. It’s readable, easy to create 2D art for, and easy to simulate with 2D game engines. Certain common world-grid lines are angled along pixel-paths where aliasing is less of an issue. It can be simulated in 2D game engines as well without as much headache for designers and developers.

**Equirectangular Projection** is easiest to understand as a latitude/longitude projection, where the lat/long coordinates of a sphere (er, globe) are the x/y coordinates of an image. A 2:1 aspect ratio image can cover an entire sphere. Technically, this is a sort of “Cylindrical” projection, and sometimes we say “spherical projection” instead of “equirectangular”, so sometimes “spherical” is a type of “cylindrical” projection. That’s very confusing, and why I recommend being pedantic and using “equirectangular” and not “spherical” when referring to projection.

![Equirectangular Projection](/images/digital-media/pano1.jpg)
*360 Photo of Mellon Center by Hunter Dyar.*

360 images and 360 video (like on youtube) are created for equirectangular projection. Because of the projection, there is the least amount of distortion around the middle (equator) or the images, which we care about the most. People tend not to look straight up or down.

**Other types**, like Azimuthal projection (where the globe is mapped to a radial coordinate system) or Conic projection (radial coordinate system, but using arcs, not full circles), we don’t really care about much since (while super interesting) they don’t apply to 3D graphics. Stereographic is a projection method that can make 360 images look like “little planets”. It can be fun.
