---
title: Stipple Effect
description: "Pixel art editor that supports animation and scripting"
web-link: "/se"
gh-link: "https://github.com/jbunke/stipple-effect"
status: "Maintained"
start-year: 2023
end-year: 2024
index: 0
---

![Onion skinning](https://raw.githubusercontent.com/jbunke/se-docs/master/assets/graphics/onion-skin.gif)

*Stipple Effect* is a pixel art editor that has the potential to revolutionize 2D indie game development with its approach to scripting. It has all the standard features of a raster graphics editor, along with a host of features specifically intended to facilitate the creation of pixel art for video games or online distribution.

Such features include:
* [**Split/stitch**](https://raw.githubusercontent.com/jbunke/se-docs/master/assets/graphics/split-stitch.gif): Stitch an animation into a sprite sheet or split a static project into an animation with as little as a single click or keystroke
* [**Pixel grid**](https://raw.githubusercontent.com/jbunke/se-docs/master/assets/graphics/pixel-grid.gif): Easily customize the size of pixel grid cells. The box select tool selection area can be snapped to the grid.
* [**Onion skinning**](https://raw.githubusercontent.com/jbunke/se-docs/master/assets/graphics/onion-skin.gif)
* [**Easy and intuitive outlining system**](https://raw.githubusercontent.com/jbunke/se-docs/master/assets/graphics/outline.gif)
* **Palettes**
  * Import and export palettes
  * [Populate a palette with colors from the project canvas](https://raw.githubusercontent.com/jbunke/se-docs/master/assets/graphics/extract-colors.gif)
  * [**Palettization**](https://raw.githubusercontent.com/jbunke/se-docs/master/assets/graphics/palettization.gif): Map project canvas colors to their nearest equivalent palette color
* **Export file types**
  * PNG sprite sheet
  * Separate PNGs per frame
  * Animated GIFs
  * MP4 video
* And much more...

## Scripting

*Stipple Effect* really shines when users harness the power of the scripting system.

In *Stipple Effect*, there are three main applications for scripting:
* Automation
* Previews
* Color transformations

#### Automation

Users can write and run automation scripts to automatically execute a series of program instructions.

For example, imagine there are 20 projects open in *Stipple Effect*. For each of these projects, the user wants to add a static black background layer. Instead of manually (1) adding a lowest layer to each project, (2) linking its cels, and (3) filling it with the color black, the user can write and run the following automation script once:

```js
() {
    for (p in $SE.get_projects()) {
        p.set_layer_index(0);
        p.add_layer();
        p.move_layer_down();

        ~ layer l = p.get_layer();
        l.link_cels();
        l.set_cel(0, black_bg(p));
    }
}

black_bg(project p -> image) {
    ~ int w = p.get_width();
    ~ int h = p.get_height();

    ~ image bg = new_image_of(w, h);
    bg.fill(#000000, 0, 0, w, h);
    return bg;
}
```

[*Read more about automation scripts*](/se/docs/automation-scripts)

#### Previews

*Stipple Effect* has a preview window, where the contents of the project can previewed alongside the primary workspace.

This can be used in various ways, including:
* when editing pixels at a high zoom level, users can display the project zoomed out in the preview window to see how individual pixel changes affect the project as a whole
* when editing a particular animation frame, users can play the animation in the preview window to ensure that the animation still looks smooth

On top of that, users can write preview scripts to override the content displayed by the preview window. A preview script takes the flattened project contents as input and returns an image or an array of images as output. Users can define the transformation from input to output however they want, or even ignore the input entirely and generate preview output independently.

![A preview script in action](https://raw.githubusercontent.com/jbunke/se-docs/master/assets/graphics/complex-preview.gif)

For example, this GIF showcases a preview script that takes its input from `player-head-textures` and uses the intermediate textures `head` and `head` (projects 2 and 3) to define a lookup texture relationship. The pixels in `player-head-textures` are then mapped onto a spinning head animation sprite sheet and sliced into separate frames for each direction. This array is then returned as the output and shown in the preview window.

[*Read more about preview scripts*](/se/docs/preview-scripts)

## Development
* Designed and implemented a desktop GUI application
* Designed and implemented [a scripting language](/projects/deltascript)
* Released and marketed *Stipple Effect* with no budget; currently has thousands of downloads and over 500 stars on GitHub
* Wrote comprehensive [documentation](/se/docs) for *Stipple Effect* and its [scripting API](/se/api)

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
