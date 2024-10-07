---
title: Stipple Effect
description: "A pixel art editor that supports animation and scripting"
web-link: "/se"
gh-link: "https://github.com/jbunke/stipple-effect"
status: "Maintained"
start-year: 2023
end-year: 2024
index: 0
---

![A preview script in action](https://raw.githubusercontent.com/jbunke/se-docs/master/assets/graphics/complex-preview.gif)

*Stipple Effect* is designed to facilitate a variety of workflows and to encourage rapid, iterative creation of video game art assets and other types of artwork.

* made by a solo game developer with the needs and skill sets of other indie devs in mind
* lightweight and simple to learn and use, yet allows for considerable depth and complexity
* expressive scripting API that can be used to automate program actions and create dynamic preview and color transformations with complex logic

## Features
* Symbiotic relationship between layers and frames
    * [Linked and unlinked layers](https://raw.githubusercontent.com/jbunke/se-docs/master/assets/graphics/linked-layers.gif)
* [Two-color system: Stipple Effect's brush, pencil, and gradient tool allow for interesting combinations of the primary and secondary colors](https://raw.githubusercontent.com/jbunke/se-docs/master/assets/graphics/combination-modes.gif)
    * Dither mode
    * Blend mode
    * Noise mode
* State management
    * [Granular undo and redo](https://raw.githubusercontent.com/jbunke/se-docs/master/assets/graphics/granular-undo-redo.gif)
* Animation playback
    * [Onion skinning](https://raw.githubusercontent.com/jbunke/se-docs/master/assets/graphics/onion-skin.gif)
    * Edit during playback
* [Split/stitch](https://raw.githubusercontent.com/jbunke/se-docs/master/assets/graphics/split-stitch.gif)
    * Split a project into frames
    * Stitch frames together into a sprite sheet
* Palettes
    * Import and export palettes
    * [Palettization](https://raw.githubusercontent.com/jbunke/se-docs/master/assets/graphics/palettization.gif)
    * [Extract colors in a project to a palette](https://raw.githubusercontent.com/jbunke/se-docs/master/assets/graphics/extract-colors.gif)
* Selection
    * [Family of selection tools designed for pixel-perfect selection](https://raw.githubusercontent.com/jbunke/se-docs/master/assets/graphics/selection-tools.gif)
    * [Intuitive and powerful outlining utilities](https://raw.githubusercontent.com/jbunke/se-docs/master/assets/graphics/outline.gif)
* [Pixel grid](https://raw.githubusercontent.com/jbunke/se-docs/master/assets/graphics/pixel-grid.gif)
    * Easily enable/disable and modify the size of the pixel grid cells
    * The box select tool can snap to the grid
* And much more!

## Development
* Here

## Technologies
#### Java
The source code for *Stipple Effect* is written in Java 17.

#### [Delta Time](/projects/delta-time)
*Stipple Effect* is built on top of my *Delta Time* library. *Delta Time* handles actions such as the program execution loop, text rendering, and UI element logic.

#### [DeltaScript](/projects/deltascript)
*Stipple Effect* uses its own domain-specific language for scripting. This language is an extension dialect of *DeltaScript*.

## More information
* [Website](/se)
* [Source code](https://github.com/jbunke/stipple-effect)
