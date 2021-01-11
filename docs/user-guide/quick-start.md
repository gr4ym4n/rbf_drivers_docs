# Quick-Start

This guide will walk you through a really simple setup so you can get a feel for the workflow
involved in setting up RBF drivers. It's not a particularly real-world example but it will
serve to get you up and running quickly and give you an intuitive understanding of RBF Drivers.

## Setting up the scene

Once you've got RBF Drivers [installed](./user-guide/installation), open up Blender and delete the
default camera and light by selecting them in viewport and hitting **x**, or by selecting them in
the outliner and choosing **Delete** from the context menu. You can leave the default cube where
it is.

<p style="text-align:center"><img src="img/quickstart_001.jpg" alt="Quick start scene setup 1"/></p>

Add an armature object to the scene (**shift-a** or **Add** menu > **Armature**), and move it
out of the way so you can see it beside the cube. 3 units along the Y-axis should do the trick.

<p style="text-align:center"><img src="img/quickstart_002.jpg" alt="Quick start scene setup 2"/></p>

___________________________________________________________________________________________________

## Setting up the RBF driver

We're going to set up an RBF driver that uses the location of the bone to simultaneously drive all
the transform properties of the cube next to it.

Since RBF drivers are attached to pose bones, we need to have the bone selected in pose mode.
Select the armature object, put it into pose mode, and ensure the bone is active by clicking on it
in the viewport.

<p style="text-align:center"><img src="img/quickstart_003.jpg" alt="Quick start scene setup 3"/></p>

Now select the **Bone Properties** panel, find the **RBF Drivers** section and click **Add** to
create a new RBF driver.

<p style="text-align:center"><img src="img/quickstart_004.jpg" alt="Quick start scene setup 4"/></p>

<p style="text-align:center"><img src="img/quickstart_004b.jpg" alt="Quick start scene setup 4"/></p>

!!! Note
    You might notice that the RBF driver we just created is highlighted in red. This is just to let
    you know that it's not yet operational because we haven't defined any
    [inputs](./user-guide/inputs), [driven properties](./user-guide/driven-properties) or
    [poses](./user-guide/poses) yet. We're going to fix that next.

___________________________________________________________________________________________________

## Add inputs

For this example, we're just going to be using a single location axis, but to keep things simple go
ahead and select all the Location transform channels under the **Inputs** section of the RBF driver.
Leave the others unchecked.

<p style="text-align:center"><img src="/img/quickstart_005.jpg" alt="Quick start scene setup 5"/></p>

___________________________________________________________________________________________________

## Add Driven Properties

Now we're going to add driven properties for each of the cube's transform channels.

* Click the **Add** button at the top of the **Driven Properties** section of the RBF Driver panel to
  create a new driven property.
* Change the driven property type to **Transform Channel** using the dropdown menu next to the driven
  property's name.
* Select the *Cube* from the *Object* field, and set the *Type* to *X Location* (it will probably
  be set as such by default)

Repeat the above steps for *Y Location*, *Z Location*, *X Rotation*, *Y Rotation*, *Z Rotation*, 
*X Scale*, *Y Scale*, and finally *Z Scale*. The Driven Properties panel should look like the image
below.

<p style="text-align:center"><img src="/img/quickstart_006.jpg" alt="Quick start scene setup 6" width=400/></p>

___________________________________________________________________________________________________

## Adding Poses

Now that we've told the RBF driver what [inputs](.//user-guide/inputs) we're using, and what properties
we want to be driven, we're ready to define [poses](.//user-guide/poses) for it to follow.

Our first pose will define our starting point, which is just how things are, so go ahead and click the
**+** button next to the **Poses** list at the bottom of the
[RBF Drivers panel](.//user-guide/managing-drivers/). A *Rest* pose will appear in the list.

<p style="text-align:center"><img src="/img/quickstart_007.jpg" alt="Quick start scene setup 7"/></p>

Go back to the 3D view and move the pose bone 1 unit along the Y axis, then go back to
**Object mode** and select the cube. Rotate the cube however you wish, rescale it however you
like, and move it off a bit in any direction you like, keeping it fairly close to the bone though
so we can keep them both in view. I ended up with the scene below.

<p style="text-align:center"><img src="/img/quickstart_008.jpg" alt="Quick start scene setup 8"/></p>

Reselect the armature object, put it back into pose mode and ensure that the bone is selected.
Go back to the the **Poses list** and add a second pose.

At this point we can review our [poses](.//user-guide/poses) using the
[**Apply**](.//user-guide/poses/#viewing-and-updating-poses) button next to the list of
[poses](.//user-guide/poses). Go ahead and select a pose in the list and click
[**Apply**](.//user-guide/poses/#viewing-and-updating-poses) to view it in the 3D viewport.

<p style="text-align:center"><img src="/img/quickstart_009.jpg" alt="Quick start scene setup 9"/></p>

Now we're ready to see things in action.

___________________________________________________________________________________________________

## Activating the RBF Driver

By default our RBF Driver will be disabled because we want the driven properties to remain under
our control while we set up our poses. To enable them, check the box next to the driver in
the list.

<p style="text-align:center">
<img src="/img/drivers_panel_mutehlt.jpg" alt="Quick start scene setup 10"/>
</p>

___________________________________________________________________________________________________

## Playtime

Now that the RBF driver is operational, you can move the pose bone and it will drive the cube
between the poses you defined:

<p style="text-align:center">
<img src="/img/quickstart_010.gif" alt="Quick start scene setup 11"/>
</p>

Now's a good time to play around with the [RBF settings](.//user-guide/rbf-settings). Try adjusting
the [interpolation](.//user-guide/rbf-settings#interpolation) and
[smoothing](.//user-guide/rbf-settings#smoothing) to see what they do.
