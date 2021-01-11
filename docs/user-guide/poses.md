# Poses

<p style="text-align:center"><img src="../../img/poses_panel.jpg" alt="Poses panel"/></p>

Poses are a fundamental part of how RBF drivers works. They represent a snapshot of all the
[inputs](../inputs) and [driven properties](../driven-properties) that you
have defined. When you create a *pose* you are telling the system that when the
[inputs](../inputs) are like *this*, the
[driven properties](../driven-properties) should be like *that*. RBF Drivers will work
out the in-between bits for you, so that behaviors and animations are smooth and predictable.

!!! Note
    While not strictly required, it's advisable to set up
    [driven properties](../driven-properties) before you add the poses. If you add new
    [driven properties](../driven-properties) after you have created poses, all the poses
    for those [driven properties](../driven-properties) will have the same values, which
    is rarely what you want. You can of course go back and
    [edit the poses](../#viewing-and-updating-poses) if you wish.

___________________________________________________________________________________________________

## Adding and removing poses

<p style="text-align:center"><img src="../../img/poses_panel_addremove.jpg" alt="Add/remove pose buttons"/></p>

To add a pose, simply click the **+** button next to the list of poses. The RBF driver will record
the current state of the [inputs](../inputs) and the
[driven properties](../driven-properties) and save it as a pose. It's usually a good idea
to change the name of the pose to something more meaningful, which you can do by double-clicking
on the pose name in the list.

To remove a pose, click the **-** button next to the list of poses. The pose data will be removed
and the RBF driver will be automatically recalculated.

___________________________________________________________________________________________________

## Viewing and Updating poses

<p style="text-align:center"><img src="../../img/poses_panel_viewapply.jpg" alt="View/apply pose buttons"/></p>

It's sometimes helpful to review the poses you have already defined, and optionally update them.
Clicking the apply button will apply the selected pose to the scene. You can then make changes,
and if you wish, overwrite the selected pose by clicking the update button.

If you want to manually edit the selected pose, clicking the edit button will bring up a dialog box
with the saved values the pose. Once you confirm your changes the pose will be updated.

<p style="text-align:center"><img src="../../img/poses_panel_edit.jpg" alt="Edit pose dialog"/></p>

___________________________________________________________________________________________________

## Moving poses

<p style="text-align:center"><img src="../../img/poses_panel_moveupdown.jpg" alt="Move pose up/down buttons"/></p>

The poses list follows the typical Blender interface, so you can move poses up or down with the
list using the move up/down buttons. The RBF driver operates irrespective of the order of poses,
but it can be useful to order the poses in a way that makes sense for you.
