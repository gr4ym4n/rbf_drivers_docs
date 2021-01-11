# Managing Drivers

The user interface for RBF Drivers is situated under the **Bone properties** tab of the
**Properties** panel, so you'll need to have a pose bone active in the viewport.

!!! Note
    Each RBF driver is associated with a pose bone which acts as the driver, unlike Blender's
    normal drivers, where you associate a driver with a driven property. This is due to the
    fact that a single RBF driver normally drives multiple driven properties.

If you haven't yet created any RBF drivers for the active pose bone, the RBF Drivers panel
will simply display a button to add your first RBF driver.

<p style="text-align:center"><img src="../../img/drivers_panel_a.jpg" alt="Empty drivers panel"/></p>

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

## Rebuilding Drivers

<p style="text-align:center"><img src="../../img/drivers_panel_updatehlt.jpg" alt="Driver update button"/></p>

To the right of the driver's list, the middle button is used to manually recalculate the RBF
driver. Under normal circumstances you will not need to use this, since the RBF driver will
automatically recalculate things in the background as you make changes. Nevertheless, because
RBF drivers are built on Blender's native tools (drivers and custom properties) you are free
to edit or delete them. This is strongly advised against unless you are sure you know what you
are doing, but if you do so, whether intentionally or accidentally, you can use this button to
force the RBF driver to recalculate itself.
