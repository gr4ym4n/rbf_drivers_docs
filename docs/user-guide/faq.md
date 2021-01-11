
If you don't find the answer to your question below, [get in touch](user-guide/getting-help).

## General

### Can I share or sell my models, rigs etc. if I use RBF Drivers?

You absolutely can! RBF Drivers was designed very specifically to build on Blender's native
capabilities and although you need to have the add-on installed to create or edit RBF drivers,
once they're running all the data and functions they need are encapsulated in custom properties
and drivers, so you can export, link, share or sell your models and rigs freely and they'll work
on any compatible version of Blender, whether or not the add-on is installed.

### What are these custom properties that get added to my rig?

Each RBF driver has to perform a number of intermediate steps to produce the final result, and
needs access to different pieces of data to perform those steps. In order to operate within the
limitations imposed by Blender's dependency graph, RBF drivers will add a couple of custom
properties to the driving bone, and to the armature (the Armature ID data-block, not the object)
to which the bone belongs. Depending on how many properties and poses are being managed by the
RBF driver there may be one or more properties defined.

These properties are necessary for RBF driver to work and they shouldn't be deleted or edited
directly unless you are sure you know what you're doing. If you do accidentally mess something
up, you can click the [update button](user-guide/managing-drivers#rebuilding-drivers) to the
right of the [list of RBF Drivers](user-guide/managing-drivers#the-drivers-list) to rebuild
the properties for that RBF Driver.

<p style="text-align:center"><img src="img/rbfdriver_update_btn.jpg" alt="Update Button" width="400"/></p>

We purposefully chose to use custom properties rather than hiding them in a custom API because
it allows you to export and share the rigs and models you have created using RBF Drivers with
other uses who do not have a copy of the add-on.

### What are all these drivers I can see in the driver's panel?

RBF Drivers are designed to take advantage of Blender's native capabilities and build on top of
the tools Blender already provides. Nevertheless they are somewhat complex and each RBF Driver
needs to make a few intermediate calculations to produce the final result. In order to achieve
this it will create a couple of extra array properties and drive the elements of those properties,
which in turn will drive the [driven properties](user-guide/driven-properties) you defined in the
RBF driver.

___________________________________________________________________________________________________

## Performance

### How many RBF drivers can I have running at one time?

There are no limits imposed on how many RBF drivers you can add, but they are inherently more
demanding on the system than constraints and basic drivers. You can theoretically have as many
as your computer will run without slowing to a crawl but they are really only intended to be
used here and there for specialized needs. In short, if a simple constraint or two will do the
job you are better off going with a simple solution, but when you need an RBF Driver, use one!

### How many driven properties can I add?

You can have as many driven properties as you wish, but bear in mind that RBF drivers are
inherently more demanding on the system than constraints and basic drivers so they should
be used sparingly.

### How many poses can I have?

Because RBF driver consolidates everything down to native Blender drivers, it needs to fit certain
calculations into driver expressions, which are limited within Blender to having a maximum length
of 256 characters. RBF Drivers do their very best to pack as much as possible into an expression
by reducing floating-point precision (according to your [settings](user-guide/rbf-settings)) and
storing values in properties and referencing them with variables where necessary. Nevertheless,
eventually these expressions can grow beyond the aforementioned limits, in the unlikely event that
this happens the RBF driver will fail to update and you will be notified that an expression is too
long. In this case you will need to reduce the number of poses and update again. This being said,
part of the beauty of RBF drivers is that you rarely need more than a few poses to achieve a great
result.

___________________________________________________________________________________________________

## Limitations

### Why can't I use things other than a pose bone as a driver?

The primary use-cases for RBF drivers are in rigging and character animation. Although other uses
are possible, they can invariably be supported simply by creating a bone where you might otherwise
use an empty, or giving the object an armature.

### Why can I only use transform properties as inputs?

One of the principal aims in creating RBF Drivers was that it should work with Blender's native
tools, and allowing the vast number of properties available to be used as inputs would make it
too easy to push them beyond their limits and break things. This being said, transform properties
allow you to do pretty much anything. You can always add an extra bone, drive a transform property
on it, and use that as input to the RBF Driver.
