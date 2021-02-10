# Driven Properties

The **Driven Properties** section of the RBF Drivers panel is where you define the outputs for the
RBF driver. You can add almost any property of any object here.

!!! Note
    Just like Blender's native drivers, driven properties need to be integers, booleans or floats.
    In practice you will probably only ever be driving float properties.

___________________________________________________________________________________________________

## Adding Driven Properties

<p style="text-align:center"><img src="../../img/drivenprop_add.jpg" alt="Adding Driven properties"/></p>

Clicking the **Add** button in the **Driven Properties** pane will display a menu from which you
can select what type of property or properties you wish to drive.

Selecting **Single Property** will simply add a new driven property into the list. Selecting either
**Transforms** or **Shape Keys** will open a dialog box where you can choose an object (and
optionally a bone) and select one or more properties to add in one go.

<p style="text-align:center">
    <img src="../../img/drivenprop_add_transforms.jpg" alt="Add Transforms Popup"/>
    <img src="../../img/drivenprop_add_shape_keys.jpg" alt="Add Shape Keys Popup"/>
</p>

___________________________________________________________________________________________________

## Driven Property Types

<p style="text-align:center"><img src="../../img/drivenprop_type.jpg" alt="Driven property types"/></p>

You can select from either **Single Property**, **Transform Channel** or **Shape Key**, depending
on what type of property you wish to drive. You can also provide a useful name for the property and
move it up or down within the stack to help you keep track of things.

### Single Property

<p style="text-align:center"><img src="../../img/drivenprop_singleprop.jpg" alt="Driven property single property type"/></p>

The **Single Property** type allows you to set a path to any of Blender's properties
(though it will need to be an integer, boolean or float property to be driven). The simplest way to
do this is to select the object you want to drive, then copy and paste the path to the property by
right-clicking on that property in the user interface and selecting **Copy Data Path** from the
context menu.

If the data path is incorrect, or the property cannot be driven, the path will be highlighted in
red.

!!! Note
    When using the **Copy Data Path** option from the context menu, the data path that is copied to
    the clipboard will not include the array index for array-like Blender properties. It is
    sometimes necessary to append it to the path yourself. For example, if you wanted to drive the
    delta location x of an object, the data path given by Blender will be 'delta_location', whereas
    you will want to set the driven property's data path to 'delta_transform[0]'

### Transform Channel

<p style="text-align:center"><img src="../../img/drivenprop_xformchan.jpg" alt="Driven property transform channel type"/></p>

Selecting **Transform Channel** allows you to choose a transform channel to drive. If you select
an armature object, you can (optionally) drive a transform channel of a pose bone. If no bone
is selected the transform channel on the object itself will be driven.

!!! Note
    **Transform Channel** properties are really just a convenience. Driving the X Location channel
    of an object is entirely equivalent to creating a **Single Property** for the "location[0]"
    path.

!!! Note
    Unlike [inputs](../inputs#rotation-modes), the rotation modes available for driving
    rotation channels are limited to **Euler**, **Quaternion** and **Axis/Angle** to match the
    types of rotation properties available for objects and bones. The rotation mode of the
    driven property should almost always correspond to the rotatation mode of the object or bone
    being driven. When you select an object or bone, the correct rotation mode will be set for you
    automatically.

### Shape Key

<p style="text-align:center"><img src="../../img/drivenprop_shapekey.jpg" alt="Driven property shape key channel type"/></p>

Selecting **Shape Key** from the dropdown menu allows you can set a mesh object and choose from
the shape keys defined for that mesh. If you have a valid shape key selected, you can also adjust
the value of the shape key directly from the driven property pane so you don't have to switch back
and forth between the rig and mesh while setting [poses](../poses).

!!! Note
    It is preferred to use a driven **Shape Key** property rather than manually adding the path for
    the shape key's value to a **Single Property**. While the latter will correctly drive the value,
    the shape key's value property will not show as being driven in the UI (highlighted in purple).
