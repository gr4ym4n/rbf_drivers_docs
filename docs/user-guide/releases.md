# Releases

## 1.0 (January 11 2021)

- Initial release

## 1.1 (February 01 2021)

- [Added support for x-mirror](../using-x-mirror)
- [Added ability to copy/paste RBF drivers, optionally accounting for symmetry](../managing-drivers#copying-pasting-drivers)
- [Added *Shape Key* driven property type](../driven-properties#shape-key)
- [Driven properties can now be moved up/down within the stack](../driven-properties)
  
## 1.2 (February 09 2021)

- New [advanced pose options](../poses#advanced-pose-options). Pose [weight](../poses#pose-weight) and [effect](../poses/#pose-effect) can now be adjusted *and driven*!
- Multiple transform channels and shape keys can now be added as driven properties in a single pass using the **Add** button dropdown
- Mirrored shape keys are now supported with x-mirroring and paste symmetrical using standard left/right suffixes (.L, .R, etc.)
- Moved the **Add** driven property button to the bottom of the stack
- Changes to driven property settings now update the RBF network
- Improved the reliability of the computed pose weight when using gaussian interpolation
- Fixed an issue where changes to driven property settings could result in an orphaned driver
- Fixed an issue where editing a pose could result in an RBF network update even if the driver was not operational
- Fixed an issue where swing/twist rotation inputs were not able to function correctly
- Fixed an issue with pose weights being clamped when they shouldn't be
- Fixed an issue where duplicating bones that have RBF drivers could result in linked drivers even after the driver was updated
- Deprecated smoothing parameter which will be removed in a future release
