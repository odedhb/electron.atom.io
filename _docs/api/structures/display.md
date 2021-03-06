---
version: v1.4.8
category: API
redirect_from:
    - /docs/v0.24.0/api/structures/display/
    - /docs/v0.25.0/api/structures/display/
    - /docs/v0.26.0/api/structures/display/
    - /docs/v0.27.0/api/structures/display/
    - /docs/v0.28.0/api/structures/display/
    - /docs/v0.29.0/api/structures/display/
    - /docs/v0.30.0/api/structures/display/
    - /docs/v0.31.0/api/structures/display/
    - /docs/v0.32.0/api/structures/display/
    - /docs/v0.33.0/api/structures/display/
    - /docs/v0.34.0/api/structures/display/
    - /docs/v0.35.0/api/structures/display/
    - /docs/v0.36.0/api/structures/display/
    - /docs/v0.36.3/api/structures/display/
    - /docs/v0.36.4/api/structures/display/
    - /docs/v0.36.5/api/structures/display/
    - /docs/v0.36.6/api/structures/display/
    - /docs/v0.36.7/api/structures/display/
    - /docs/v0.36.8/api/structures/display/
    - /docs/v0.36.9/api/structures/display/
    - /docs/v0.36.10/api/structures/display/
    - /docs/v0.36.11/api/structures/display/
    - /docs/v0.37.0/api/structures/display/
    - /docs/v0.37.1/api/structures/display/
    - /docs/v0.37.2/api/structures/display/
    - /docs/v0.37.3/api/structures/display/
    - /docs/v0.37.4/api/structures/display/
    - /docs/v0.37.5/api/structures/display/
    - /docs/v0.37.6/api/structures/display/
    - /docs/v0.37.7/api/structures/display/
    - /docs/v0.37.8/api/structures/display/
    - /docs/latest/api/structures/display/
source_url: 'https://github.com/electron/electron/blob/master/docs/api/structures/display.md'
title: "Display Object"
sort_title: "display object"
---

# Display Object

* `id` Number - Unique identifier associated with the display.
* `rotation` Number - Can be 0, 90, 180, 270, represents screen rotation in
  clock-wise degrees.
* `scaleFactor` Number - Output device's pixel scale factor.
* `touchSupport` String - Can be `available`, `unavailable`, `unknown`.
* `bounds` [Rectangle](http://electron.atom.io/docs/structures/rectangle)
* `size` Object
  * `height` Number
  * `width` Number
* `workArea` [Rectangle](http://electron.atom.io/docs/structures/rectangle)
* `workAreaSize` Object
  * `height` Number
  * `width` Number

The `Display` object represents a physical display connected to the system. A
fake `Display` may exist on a headless system, or a `Display` may correspond to
a remote, virtual display.
