---
version: v1.4.8
category: API
redirect_from:
    - /docs/v0.24.0/api/power-save-blocker/
    - /docs/v0.25.0/api/power-save-blocker/
    - /docs/v0.26.0/api/power-save-blocker/
    - /docs/v0.27.0/api/power-save-blocker/
    - /docs/v0.28.0/api/power-save-blocker/
    - /docs/v0.29.0/api/power-save-blocker/
    - /docs/v0.30.0/api/power-save-blocker/
    - /docs/v0.31.0/api/power-save-blocker/
    - /docs/v0.32.0/api/power-save-blocker/
    - /docs/v0.33.0/api/power-save-blocker/
    - /docs/v0.34.0/api/power-save-blocker/
    - /docs/v0.35.0/api/power-save-blocker/
    - /docs/v0.36.0/api/power-save-blocker/
    - /docs/v0.36.3/api/power-save-blocker/
    - /docs/v0.36.4/api/power-save-blocker/
    - /docs/v0.36.5/api/power-save-blocker/
    - /docs/v0.36.6/api/power-save-blocker/
    - /docs/v0.36.7/api/power-save-blocker/
    - /docs/v0.36.8/api/power-save-blocker/
    - /docs/v0.36.9/api/power-save-blocker/
    - /docs/v0.36.10/api/power-save-blocker/
    - /docs/v0.36.11/api/power-save-blocker/
    - /docs/v0.37.0/api/power-save-blocker/
    - /docs/v0.37.1/api/power-save-blocker/
    - /docs/v0.37.2/api/power-save-blocker/
    - /docs/v0.37.3/api/power-save-blocker/
    - /docs/v0.37.4/api/power-save-blocker/
    - /docs/v0.37.5/api/power-save-blocker/
    - /docs/v0.37.6/api/power-save-blocker/
    - /docs/v0.37.7/api/power-save-blocker/
    - /docs/v0.37.8/api/power-save-blocker/
    - /docs/latest/api/power-save-blocker/
source_url: 'https://github.com/electron/electron/blob/master/docs/api/power-save-blocker.md'
excerpt: "Block the system from entering low-power (sleep) mode."
title: "powerSaveBlocker"
sort_title: "powersaveblocker"
---

# powerSaveBlocker

> Block the system from entering low-power (sleep) mode.

Process: [Main](http://electron.atom.io/docs/tutorial/quick-start#main-process)

For example:

```javascript
const {powerSaveBlocker} = require('electron')

const id = powerSaveBlocker.start('prevent-display-sleep')
console.log(powerSaveBlocker.isStarted(id))

powerSaveBlocker.stop(id)
```

## Methods

The `powerSaveBlocker` module has the following methods:

### `powerSaveBlocker.start(type)`

* `type` String - Power save blocker type.
  * `prevent-app-suspension` - Prevent the application from being suspended.
    Keeps system active but allows screen to be turned off.  Example use cases:
    downloading a file or playing audio.
  * `prevent-display-sleep` - Prevent the display from going to sleep. Keeps
    system and screen active.  Example use case: playing video.

Returns `Integer` - The blocker ID that is assigned to this power blocker

Starts preventing the system from entering lower-power mode. Returns an integer
identifying the power save blocker.

**Note:** `prevent-display-sleep` has higher precedence over
`prevent-app-suspension`. Only the highest precedence type takes effect. In
other words, `prevent-display-sleep` always takes precedence over
`prevent-app-suspension`.

For example, an API calling A requests for `prevent-app-suspension`, and
another calling B requests for `prevent-display-sleep`. `prevent-display-sleep`
will be used until B stops its request. After that, `prevent-app-suspension`
is used.

### `powerSaveBlocker.stop(id)`

* `id` Integer - The power save blocker id returned by `powerSaveBlocker.start`.

Stops the specified power save blocker.

### `powerSaveBlocker.isStarted(id)`

* `id` Integer - The power save blocker id returned by `powerSaveBlocker.start`.

Returns `Boolean` - Whether the corresponding `powerSaveBlocker` has started.
