# Handy Work

A module for doing efficient real-time pose detection from WebXR Hand Tracking using Web Workers to ensure it doesn't interfere with the main thread

The pose tracking module is Framework Agnostic, it doesn't rely on any particular library it should work just as well with THREE as BabylonJS or Play Canvas. 

Poses can be found in the `/poses/` folder and additional poses are welcome 

There is also an [AFrame module](./README-AFRAME.md) which handles pose tracking and displaying hand models.

## Hand Pose Module Usage Example

```javascript
import {
  update as handyWorkUpdate,
  loadPose
} from "../build/esm/handy-work.js";

loadPose('relax', '../poses/relax.handpose');
loadPose('fist', '../poses/fist.handpose');
loadPose('flat', '../poses/flat.handpose');
loadPose('point', '../poses/point.handpose');

// In RAF
handyWorkUpdate([controller1, controller2], referenceSpace, frame, callback);
```
## Using via a CDN

If you use it via a CDN because it uses a Worker you need to use the 
standalone version which has the Worker encoded as a string.

```javascript
import('https://cdn.jsdelivr.net/npm/handy-work@1.4.0/build/esm/handy-work.standalone.js')
.then(function ({
  update,
  loadPose,
  dumpHands
}) {
  const handyWorkUpdate = update;
  const dumpHands = dumpHands;
  const loadPose = loadPose;

  loadPose('relax', POSE_FOLDER + 'relax.handpose');
  loadPose('fist', POSE_FOLDER + 'fist.handpose');
  loadPose('flat', POSE_FOLDER + 'flat.handpose');
  loadPose('point', POSE_FOLDER + 'point.handpose');
  loadPose('horns', POSE_FOLDER + 'horns.handpose');
  loadPose('shaka', POSE_FOLDER + 'shaka.handpose');
  loadPose('vulcan', POSE_FOLDER + 'vulcan.handpose');
}.bind(this));
```

<!--DOCS-->
Need to install the following packages:
jsdoc-to-markdown@9.1.1
Ok to proceed? (y) <!--DOCS_END-->
