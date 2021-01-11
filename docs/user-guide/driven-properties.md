# Driven Properties

The **Driven Properties** section of the RBF Drivers panel is where you define the outputs for the
RBF driver. You can add almost any property of any object here.

!!! Note
    Just like Blender's native drivers, driven properties need to be integers, booleans or floats.
    In practice you will probably only ever be driving float properties.

___________________________________________________________________________________________________

## Driven Property Types

<p style="text-align:center"><img src="img/drivenprop_type.jpg" alt="Driven property types"/></p>

Much like
<a href="https://docs.blender.org/manual/en/latest/animation/drivers/drivers_panel.html#driver-variables" target="_blank">
Blender's driver variables</a>, you can select from either **Single Property** or **Transform Channel**.
You can also provide a useful name for the property to help you keep track of things.

### Single Property

<p style="text-align:center"><img src="img/drivenprop_singleprop.jpg" alt="Driven property single property type"/></p>

The **Single Property** type allows you to set a path to any of Blender's properties
(though it will need to be an integer, boolean or float property to be driven). The simplest way to
do this is to select the object you want to drive, then copy and paste the path to the property by
right-clicking on that property in the user interface and selecting **Copy Data Path** from the
context menu.

If the data path is incorrect, or the property cannot be driven, the path will be highlighted in
red.

### Transform Channel

<p style="text-align:center"><img src="img/drivenprop_xformchan.jpg" alt="Driven property transform channel type"/></p>

Selecting **Transform Channel** allows you to choose a transform channel to drive. If you select
an armature object, you can (optionally) drive a transform channel of a pose bone. If no bone
is selected the transform channel on the object itself will be driven.

!!! Note
    **Transform Channel** properties are really just a convenience. Driving the X Location channel
    of an object is entirely equivalent to creating a **Single Property** for the "location[0]"
    path. 

!!! Note
    Unlike [inputs](./user-guide/inputs#rotation-modes), the rotation modes available for driving
    rotation channels are limited to **Euler**, **Quaternion** and **Axis/Angle** to match the
    types of rotation properties available for objects and bones. The rotation mode of the
    driven property should almost always correspond to the rotatation mode of the object or bone
    being driven. When you select an object or bone, the correct rotation mode will be set for you
    automatically.
