# Overview

Before we delve into what RBF drivers are, it's helpful to take a quick look at
<a href="https://docs.blender.org/manual/en/latest/animation/drivers/index.html" target="_blank">
Blender's built-in drivers</a>, then we can see how RBF drivers are different, and what makes them
so powerful.

#### Blender's drivers

On a basic level, Blender's drivers allow you to control the value of one property using
the value from another property. So for example, let's imagine we're creating a ballet-dancer:
you could use a driver to tilt her
<a href="https://en.wikipedia.org/wiki/Tutu_(clothing)" target="_blank">tutu</a> out of the way
as she raises her leg above 45 degrees to the left, or improve the deformation around the elbow
by driving a corrective shape-key using the rotation of her forearm.

Blender's drivers allow a high degree of control, with the possibility of adjusting the
relationship between the properties using an F-Curve, or combining multiple properties
together using a mathematical expression. Essentially they enable us to create a one-to-one
or many-to-one relationship between properties. They are a very powerful feature, but they
also have their limitations.

#### Limitations of Blender's drivers

Let's now imagine we want the tutu to behave more naturally: we want it to react to the
dancer's legs wherever they go. We could use physics, but that's going to be very tricky in a
case like this, and put a heavy load on the system. Alternatively we could rig the tutu, but
animating it by hand is going to be extremely tedious, and a setup using constraints or drivers
is almost impossibly complex.

Alternatively, perhaps we want to improve the deformation around the shoulder area, and add
some realistic muscle movements to the
<a href="https://en.wikipedia.org/wiki/Scapula" target="_blank">scapula</a> region; notoriously
challenging areas for rigging and animation. Given the range of motion in the shoulder, we are
likely to need a very complicated combination of constraints, drivers and shape keys to get
anywhere near our goal.

#### RBF Drivers

Although they're built on Blender's native drivers (more on that later), RBF drivers offer a
much simpler, quicker and more effective way to solve problems like these. Rather than being
limited to creating one-to-one or many-to-one relationships between properties, they allow us
to create one-to-many, or even many-to-many relationships. Returning to our example above, we
can control the *entire* tutu rig using *all* the rotation channels of the leg, or simultaneously
animate *multiple* bones *and* shape keys around the shoulder region using *both* the location
*and* rotation of the shoulder joint.

This might sound complicated, but in fact with RBF drivers we simply tell the system that when the
leg is up *here*, the tutu should move to *there*, and when the arm moves back *here*, the clavicle
goes over *there* and the shoulder stretches like *this* and bulges out like *that*. The RBF driver
then does all the hard work to figure out where the tutu and the character mesh should go as we move
the leg and shoulder around.

#### How it works

You first choose which bone you want to be the **driver**, and which **input** properties of the
bone you want to use (location, rotation, etc). You then add all the properties of the bones,
objects, shape-keys, etc. that you want **driven**. Lastly you take snapshots (**poses**) of
each different state that your rig, mesh etc. should be in, so for example you might rotate the
arm upwards, add a shape key to correct the mesh around the shoulder, and record a pose, then
rotate the arm forwards, add another shape key, and a second pose.

As you're doing this, the system will do a whole lot of math behind the scenes and create a
number of drivers that will smoothly interpolate between your different poses and drive your
**driven** properties in a predictable way. The system does as much computation as possible
up-front, and all of the drivers it creates strictly limit themselves to
<a href="https://docs.blender.org/manual/en/latest/animation/drivers/drivers_panel.html#simple-expressions">
simple expressions</a>. This means that the actual mathematical functions that are run on each
frame are being run in C within Blender's internal graph, and take advantage of your multi-core
CPU. It also means that there's no hidden magic, the system is exposed to you so you can play with
it as you see fit, and you can share or sell your creations freely because the end-user doesn't
need to have RBF Drivers installed to use it.
