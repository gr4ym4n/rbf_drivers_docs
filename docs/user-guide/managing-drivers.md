# Managing Drivers

The user interface for RBF Drivers is situated under the **Bone properties** tab of the
**Properties** panel, so you'll need to have a pose bone active in the viewport.

!!! Note
    Each RBF driver is associated with a pose bone which acts as the driver, unlike Blender's
    normal drivers, where you associate a driver with a driven property. This is due to the
    fact that a single RBF driver can handle multiple driven properties.

<p style="text-align:center"><img src="../../img/drivers_panel_a.jpg" alt="Empty drivers panel"/></p>

If you haven't yet created any RBF drivers for the active pose bone, the RBF Drivers panel
will simply display a button to add your first RBF driver.

<p style="text-align:center"><img src="../../img/drivers_panel_adddriver.jpg" alt="Add driver button"/></p>

Clicking the button will bring up a menu where you can choose to either add a new driver, or
if you have previously copied a driver to the copy/paste buffer, paste a copy of that driver into
the list. There is also an option to "Paste Symmetrical" which you can use to paste a mirrored copy
of the driver (see the section on [x-mirroring](../using-x-mirror) for further details)

!!! Note
    RBF Drivers are compatible with Blender's x-mirror option for armatures. If you want to create
    and edit matching drivers for both sides of your rig, you should have x-mirror enabled while
    doing so. More information on handling mirrored RBF drivers is available
    [here](../using-x-mirror).
___________________________________________________________________________________________________

## The Drivers List

Once you've added an RBF Driver you'll see a list of the RBF Drivers for the active pose bone,
with the currently selected RBF driver highlighted. You can create additional drivers using the
**+** button beside the list.

<p style="text-align:center"><img src="../../img/drivers_panel_b.jpg" alt="Drivers panel"/></p>

!!! Note
    You will probably notice that when you add a new driver it is highlighted in red. In order to
    function the driver needs to have at least one [input property](../inputs), at least
    one valid [driven property](../driven-properties), and at least two valid 
    [poses](../poses). Once these have been defined, the red highlight will be removed.

The list of RBF drivers follows Blender's usual user interface standards so it should be mostly
self-explanatory. You can add or remove drivers, move them up or down within the list, and double
click on the name to rename it. There are however a couple of controls that are not quite as
obvious.

___________________________________________________________________________________________________

## Enabling and Disabling Drivers

<p style="text-align:center"><img src="../../img/drivers_panel_mutehlt.jpg" alt="Driver mute checkbox"/></p>

Once a driver is functional (not highlighted in red) there will be a small check box next to its
name in thr drivers list, which by default will be unchecked. This is where you enable or disable
that particular driver and though small it is quite important. Because *RBF Drivers* is creating
drivers for the driven properties you have defined, as long as those properties are being driven
you won't be able to adjust them in the viewport and set your poses. Therefore, while you're
defining your poses, you should have the driver disabled, then when you're ready enable it by
checking the box in the list.

___________________________________________________________________________________________________

## Copying/Pasting Drivers

<p style="text-align:center"><img src="../../img/drivers_panel_copyhlt.jpg" alt="Driver copy button"/></p>

The copy button will copy the currently selected RBF driver into the copy/paste buffer, from which
it can be pasted onto other bones.

Once copied, you can paste a driver onto another bone by clicking on the **+** button in that
bone's RBF Drivers panel and selecting either "Paste" or "Paste Symmetrical". In the former case
the driver and all its settings, inputs, driven properties and poses will be copied directly to
the new driver. When using "Paste Symmetrical", driven properties that transform bones named using
any of Blender's standard left/right suffixes (.L, .R, .LEFT, .RIGHT, etc.) will be set to drive
the corresponding bone on the opposite side of the armature.

!!! Note
    The "Paste Symmetrical" operator will only switch the suffix for bones on
    [Transform Channels](../driven-properties#transform-channel). Data paths that you have defined
    for [Single Properties](../driven-properties#single-property) are left unchanged, whether or
    not they target a pose bone.

    The operation will also not attempt to adjust pose values, so in cases where the
    orientation of the bone on one side of the armature does not correspond to that of the bone on
    the other side you may find that things move or rotate in the wrong direction and will need to
    make adjustments accordingly.


___________________________________________________________________________________________________

## Rebuilding Drivers

<p style="text-align:center"><img src="../../img/drivers_panel_updatehlt.jpg" alt="Driver update button"/></p>

The update button is used to manually recalculate the RBF driver. Under normal circumstances you
will not need to use this, since the RBF driver will automatically recalculate things in the
background as you make changes. Nevertheless, because RBF drivers are built on Blender's native
tools (drivers and custom properties) you are free to edit or delete them. This is strongly advised
against unless you are sure you know what you are doing, but if you do so, whether intentionally or
accidentally, you can use this button to force the RBF driver to recalculate itself.
