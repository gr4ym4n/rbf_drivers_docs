# Inputs

The Inputs section of the RBF Drivers panel is where you select which transform properties
on the pose bone you want to use to drive things. You can select from location, rotation and
scale channels, or any combination thereof.

<p style="text-align:center"><img src="/img/inputs.jpg" alt="Minimum precision setting"/></p>

## Rotation Modes

<p style="text-align:center"><img src="/img/inputs_rmode.jpg" alt="Minimum precision setting"/></p>

All of <a href="https://docs.blender.org/manual/en/latest/animation/drivers/drivers_panel.html#rotation-channel-modes" target="_blank">
Blender's driver rotation modes</a> are also available for RBF drivers. This includes the
swing/twist modes introduced recently. These can be especially useful in setups where you only
care about the orientation of a bone, and not its Y-axis rotation. In this case you would
select **Swing and Y Twist** and enable the W, X and Z rotation channels.

!!! Note
    If all rotation channels are enabled as inputs, the RBF driver will always use quaternions
    for the basis of it's calculations regardless of the rotation mode setting, as this provides
    the highest degree of reliability.