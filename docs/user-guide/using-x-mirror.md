# Using X-Mirror

!!! Caution
    X-mirroring only works while x-mirror is enabled for the armature you are working on. If you
    want an RBF driver to be mirrored, make sure you enable it before creating the RBF driver, and
    always have it enabled while editing the RBF driver. If you have already created a driver that
    you want to mirror to the other side of the armature, you can use the
    [**Paste Symmetrical** option from the **Add Driver** menu](../managing-drivers#copying-pasting-drivers)

RBF Drivers have full support for Blender's x-mirror option built in, and there's nothing extra
you have to do to get it to work, other than enable x-mirror for the armature. You'll find a
list below of what you can expect to be automatically mirrored for RBF Drivers.

* Addition/Removal of RBF drivers
* The RBF driver's name
* RBF settings
* Input properties and rotation modes
* Addition/Removal of driven properties
* Driven property names
* Driven property types and settings
* Addition/Removal of poses
* Pose names
* Pose positions in the pose list

!!! Note
    [Manual edits to poses](../poses#viewing-and-updating-poses) are not mirrored. There is no
    way for **RBF Drivers** to reliably predict what you want to do on the opposite side of the rig
    when manually setting pose data values. Under these circumstances you will need to make the
    desired change on both sides of the rig.
