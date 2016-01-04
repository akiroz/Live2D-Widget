## Live2D-Widget
a little cross-platform desktop widget based on the Live2D Sample App in the SDK

[nw.js](https://github.com/nwjs/nw.js) builds are avaliable on [http://nwjs.io/](http://nwjs.io/)
I have tested all 3 platforms on nw.js version 0.12.x

### Usage:
* adjust window size in package.json
* drag using invisible handle at top of window
* move: look
* scroll: zoom
* l-click: touch
* r-click: cycle models

### Install (Windows/Linux):
1. extract the right nw.js package to the root directory
2. run `nw(.exe)`

### Install (Mac OS):
1. rename the root directory to `app.nw`
2. put it inside `nwjs.app/Contents/Resources/`
3. run `nwjs.app`

### Add/Remove Models:
1. put/delete model folder inside `assets/live2d/`
2. (add only) inspect your `*.model.json`, make sure it implements the `idle` motion
3. (add only) optionally implement the `tap_body` motion with proper `hit_areas` defined
4. (add only) if the model doesn't fit properly inside your window, add/edit the `layout` section inside `*.model.json`
   (see `assets/live2d/haru/haru.model.json` for reference)
5. edit `src/LAppDefine.js` (around line 33), define/remove your `*.model.json` path(s)
6. edit `src/LAppLive2DManager.js` (around line 36), change the modulo to the number of model(s)
7. edit `src/LAppLive2DManager.js` (around line 40), add/remove cases for your model(s)

### Issues/Todo:
* sound doesn't work in nw.js
* transparency in linux doesn't work unless GPU is disabled but WebGL requires GPU
* transparency in Mac OS will show a visible title string
* presist window position between sessions
* automatically scan for models inside assets
