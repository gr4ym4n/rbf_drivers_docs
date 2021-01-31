# RBF Settings

The RBF Settings section of the RBF Drivers panel is where you control how the selected RBF
Driver interpolates between all your poses.

<p style="text-align:center"><img src="../../img/rbfsettings.jpg" alt="RBF Settings"/></p>

___________________________________________________________________________________________________

## Interpolation

Each of the available interpolation types will change how closely the
[driven properties](../driven-properties) stick to the [poses](../poses)
you have defined, as well as how smoothly and quickly they transition between them. You don't
need to know how each of them works, you can simply select which one works best for you by
switching between them and playing around in the viewport.

<p style="text-align:center"><img src="../../img/rbfsettings_ipo.jpg" alt="Interpolation setting"/></p>

### Linear

Linear interpolation will simply transition linearly between the [poses](../poses)
based on the current [inputs](../inputs). The
[driven properties](../driven-properties) will remain very close to the defined
[poses](../poses). This works well when you want a very tight fit to your data points,
particularly for smaller data sets.

### Gaussian

The gaussian option will provide a smooth, bell-shaped curve, easing the transitions between poses
in and out. It's often a good choice if your data points are somewhat scattered. You can affect the
transition timing by changing the [radius](../#radius) setting, or providing a custom
[radius](../#radius) for complete control.

### Multi-Quadratic Biharmonic

Multi-quadratic biharmonic interpolation generally provides a nice median between the smooth
characteristics of [gaussian](../#gaussian) and strictness of [linear](../#linear) and is the default
setting. Your mileage may vary depending on your data set but it's usually my preferred option.

### Inverse Multi-Quadratic Biharmonic

Inverse multi-quadratic biharmonic offers a slight variant on
[multi-quadratic biharmonic](../#multi-quadratic-biharmonic), pushing things a bit further at the ends.

___________________________________________________________________________________________________

## Radius

<p style="text-align:center"><img src="../../img/rbfsettings_rad.jpg" alt="Radius setting"/></p>

!!! Note
    The radius setting will *not* show when [interpolation](../#interpolation) is set to [Linear](../#linear)

### Mean

The radial basis function will use the average distance between all data points.

### Variance

The radial basis function will use the variance of the distances between all data points.

### Standard Deviation

The radial basis function will use the standard deviation between all data points. This is
probably the most commonly used dispersion measure in RBF networks and the default for RBF Driver

### Custom

By selecting a *Custom* radius, an input field will appear where you can input whatever radius you
wish. You're unlikely to use this option unless you're familiar with your data set and how the
interpolation functions work but feel to play around providing different values here to see the
effect.

!!! Note
    When using a [custom radius](../#custom), each time you update the radius value the RBF network
    data needs to be recalculated and the drivers recreated. This is not a small task, and with
    complex drivers you may notice a slight lag in the interface when sliding the radius value.

___________________________________________________________________________________________________

## Smoothing

<p style="text-align:center"><img src="../../img/rbfsettings.jpg" alt="Smoothing setting"/></p>

Increasing the smoothing value will relax the fit of the
[driven properties](../driven-properties) to the [poses](../poses), essentially
increasing the visual effect of the interpolation. Under most circumstances the interpolation
alone will provide pleasing results, but do play around with the smoothing to become familiar
with its effect.

!!! Note
    Each time you update the smoothing value the RBF network data needs to be recalculated and
    the drivers recreated. This is not a small task, and depending on your system, with complex
    drivers you may notice a slight lag in the interface when sliding the smoothing value.
