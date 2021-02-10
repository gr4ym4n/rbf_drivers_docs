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

## Adding and Removing Poses

<p style="text-align:center"><img src="../../img/poses_panel_addremove.jpg" alt="Add/remove pose buttons"/></p>

To add a pose, simply click the **+** button next to the list of poses. The RBF driver will record
the current state of the [inputs](../inputs) and the
[driven properties](../driven-properties) and save it as a pose. It's usually a good idea
to change the name of the pose to something more meaningful, which you can do by double-clicking
on the pose name in the list.

To remove a pose, click the **-** button next to the list of poses. The pose data will be removed
and the RBF driver will be automatically recalculated.

___________________________________________________________________________________________________

## Viewing and Updating Poses

<p style="text-align:center"><img src="../../img/poses_panel_viewapply.jpg" alt="View/apply pose buttons"/></p>

It's sometimes helpful to review the poses you have already defined, and optionally update them.
Clicking the apply button will apply the selected pose to the scene. You can then make changes,
and if you wish, overwrite the selected pose by clicking the update button.

!!! Note
    If the RBF driver is [enabled](../managing-drivers#enabling-and-disabling-drivers) then
    applying the pose will not necessarily show the exact pose you defined, instead you will see
    how it will be when driven, taking into account the interpolation, weight and effect settings.
    When the RBF driver is [disabled](../managing-drivers#enabling-and-disabling-drivers) you will
    see the exact pose without the effect of the interpolation, weight or effect settings.

If you want to manually edit the selected pose, clicking the edit button will bring up a dialog box
with the saved values for the pose. Once you confirm your changes the pose will be updated.

<p style="text-align:center"><img src="../../img/poses_panel_edit.jpg" alt="Edit pose dialog"/></p>

___________________________________________________________________________________________________

## Moving poses

<p style="text-align:center"><img src="../../img/poses_panel_moveupdown.jpg" alt="Move pose up/down buttons"/></p>

The poses list follows the typical Blender interface, so you can move poses up or down with the
list using the move up/down buttons. The RBF driver operates irrespective of the order of poses,
but it can be useful to order the poses in a way that makes sense for you.

___________________________________________________________________________________________________

## Advanced Pose Options

<p style="text-align:center"><img src="../../img/poses_panel_advancedoptions.jpg" alt="Advanced pose options"/></p>

### Pose Weight

Each pose has a **weight** value displayed below the list of poses. The **weight** value can be
adjusted using the slider. With a value of 1.0 (the default) the pose will be fully considered by
the RBF driver, with a value of 0.0 it will effectively be ignored, as if it did not exist.

!!! Note
    The **weight** that you set for a pose is used to modify the internal weight that the RBF
    driver is calculating for it. This means that there will be a gradual falloff or easing as
    the pose weight is reduced which will be dependant on the pose values and interpolation
    settings.

The weight of a pose can be useful for temporarily visualizing the effect a pose is having on the
driven properties, or for fine tuning the contribution of particular poses, but it also offers a
lot of advanced possibilities due to the fact that it can itself be driven.

You could for example add a vanilla driver to the weight value of a pose and use the bezier curve or
modifier options to ease a pose in or out, or control it from the value of some other property or
properties. You could even drive it with another RBF driver!

### Pose Effect

In addition to a **weight**, each pose also has an **effect** parameter, also situated below the
list of poses. Whereas the **weight** of a pose affects its contribution to the final driven
property values, the **effect** directly modifies the final driven property values.

Let's say you that you've set things up so that at **Pose 1**, the rotation of **Arm.L** is 90
degrees in the X axis. If you set the **effect** of **Pose 1** to be 0.5, **Arm.L**
will now be rotated to 45 degrees at that pose.

You can use the **effect** parameter to simply fine-tune poses after they have already been set up,
but you could just as well update or edit the actual pose values instead. The real power comes with
the fact that, like the **weight** parameter, the **effect** can itself be driven.

!!! Note
    The slider for the **effect** value goes from 0.0 to 1.0 as you would normally want to modify
    it within this range, but the parameter itself can be changed or driven outside of this range.
