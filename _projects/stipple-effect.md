---
title: Stipple Effect
description: "Pixel art editor that supports animation and scripting"
web-link: "https://stipple-effect.github.io"
gh-link: "https://github.com/stipple-effect/stipple-effect"
status: "Maintained"
start-year: 2023
end-year: 2025
index: 0
---

![Onion skinning](https://raw.githubusercontent.com/stipple-effect/docs/master/assets/graphics/onion-skin.gif)

*Stipple Effect* is a pixel art editor that has the potential to revolutionize 2D indie game development with its approach to scripting. It has all the standard features of a raster graphics editor, along with a host of features specifically intended to facilitate the creation of pixel art for video games or online distribution.

Such features include:
* [**Split/stitch**](https://stipple-effect.github.io/docs/sizing#splitstitch-frames): Stitch an animation into a sprite sheet or split a static project into an animation with as little as a single click or keystroke
* [**Pixel grid**](https://stipple-effect.github.io/docs/pixel-grid): Easily customize the size of pixel grid cells. The box select tool selection area can be snapped to the grid.
* [**Onion skinning**](https://stipple-effect.github.io/docs/layer#onion-skin)
* [**Easy and intuitive outlining system**](https://stipple-effect.github.io/docs/outline)
* **Palettes**
  * Import and export palettes
  * [Populate a palette with colors from the project canvas](https://stipple-effect.github.io/docs/color-actions#extract-canvas-colors-to-palette)
  * [**Palettization**](https://stipple-effect.github.io/docs/color-actions#palettization): Map project canvas colors to their nearest equivalent palette color
* [**Export file types**](https://stipple-effect.github.io/docs/save#exporting)
  * PNG sprite sheet
  * Separate PNGs per frame
  * Animated GIFs
  * MP4 video
* And much more...

## Scripting

*Stipple Effect* really shines when users harness the power of the [scripting system](https://stipple-effect.github.io/docs/scripting).

In *Stipple Effect*, there are three main applications for scripting:
* [Automation](https://stipple-effect.github.io/docs/automation-scripts)
* [Previews](https://stipple-effect.github.io/docs/preview-scripts)
* [Color transformations](https://stipple-effect.github.io/docs/color-scripts)

## Development

* Designed and implemented a desktop GUI application
* Designed and implemented [a scripting language](/projects/deltascript)
* Released and marketed *Stipple Effect* with no budget; currently has thousands of downloads and over 500 stars on GitHub
* Wrote comprehensive documentation for the [core program](https://stipple-effect.github.io/docs) and its [scripting API](https://stipple-effect.github.io/api)

## Technologies

#### Java

The source code for *Stipple Effect* is written in Java 17.

#### [Delta Time](/projects/delta-time)

*Stipple Effect* is built on top of my *Delta Time* library. *Delta Time* handles actions such as the program execution loop, text rendering, and UI element logic.

#### [DeltaScript](/projects/deltascript)

*Stipple Effect* uses its own domain-specific language for scripting. This language is an extension dialect of *DeltaScript*.

## More information

* [Website](https://stipple-effect.github.io)
* [Source code](https://github.com/stipple-effect/stipple-effect)
