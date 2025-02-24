---
title: Top Down Sprite Maker
description: "Desktop GUI application for generating fully configurable pixel art character sprite sheets in various art styles"
web-link: "https://flinkerflitzer.itch.io/tdsm"
gh-link: "https://github.com/jbunke/tdsm"
status: "In development"
start-year: 2025
end-year: 2025
index: 1
---

![Making myself](https://raw.githubusercontent.com/jbunke/tdsm-art/refs/heads/master/_tdsm/assets/runthrough.gif)

*Top Down Sprite Maker (TDSM)* is a flexible and powerful pixel art character creation tool.

I took a logic-first approach with the code, which resulted in a highly flexible, modular design that can easily be adapted to any style of pixel art sprites with any complexity of composition rules.

## Key Features

* **Complex customization logic:** Customization layers are connected with rules that cause them to affect each other
  * **Layer masks:** Equipping a hat or helmet will mask the hair pixels that should be confined by the headwear [**[ screenshot ]**](https://raw.githubusercontent.com/jbunke/tdsm-art/refs/heads/master/_tdsm/assets/mask.gif)
  * **Dynamic updates:** Changing your body type propagates changes to your clothing layers to reflect the updated sprite dimensions without altering the data of the clothing equipped [**[ screenshot ]**](https://raw.githubusercontent.com/jbunke/tdsm-art/refs/heads/master/_tdsm/assets/change-propagation.gif)
* **Controlled randomization:** Each customization layer can be "locked"; locking a layer will ignore it when a random sprite is generated, giving the user granular control over which components may be randomized [**[ screenshot ]**](https://raw.githubusercontent.com/jbunke/tdsm-art/refs/heads/master/_tdsm/logo/itch/feat-lock-layers.gif)
* **100% configurable sprite sheets**
  * **Custom sprite size:** Pad or crop each animation frame at any edge for sprites ranging from 1x1 pixel to 128x128 [**[ screenshot ]**](https://raw.githubusercontent.com/jbunke/tdsm-art/refs/heads/master/_tdsm/assets/padding.gif)
  * **Sequencing & Inclusion:** Determine the *order of directions and animations in the exported sprite sheet*, as well as which directions and animations to *include* [**[ screenshot ]**](https://raw.githubusercontent.com/jbunke/tdsm-art/refs/heads/master/_tdsm/assets/sequencing.gif)
  * **Layout:** Determine the axis along which directions and animations are exported in the sprite sheet, as well as how distinct animations follow one another [**[ screenshot ]**](https://raw.githubusercontent.com/jbunke/tdsm-art/refs/heads/master/_tdsm/assets/layout.gif)
* **Export formats:** In addition to the standard PNG sprite sheet, *TDSM* optionally exports the sprite sheet's metadata in a JSON file, and the sprite sheet as a *Stipple Effect* project with the contents of each customization layer on its own layer in the file [**[ screenshot ]**](https://raw.githubusercontent.com/jbunke/tdsm-art/refs/heads/master/_tdsm/assets/export-formats.gif)

## Development

* Designed and implemented a desktop GUI application, only using dependencies that I wrote myself
* Made/adapted all base pixel art assets myself using [*Stipple Effect*](/projects/stipple-effect), my own pixel art editor

## Technologies

#### Java

The source code for *TDSM* is written in Java 17.

#### [Delta Time](/projects/delta-time)

*TDSM* is built on top of my *Delta Time* library. *Delta Time* handles actions such as the program execution loop, text rendering, and UI element logic.

## More information

* [Website](https://flinkerflitzer.itch.io/tdsm)
* [Source code](https://github.com/jbunke/tdsm)
