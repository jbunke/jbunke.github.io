---
title: Why I've spent six months making a pixel art editor from scratch
tags: ["software", "stipple-effect", "pixel-art", "game-dev"]
excerpt_separator: <!-- more -->
---
*Adapted from [the original Reddit post](https://www.reddit.com/r/gamedev/comments/1cy48fo/why_ive_spent_six_months_making_a_pixel_art/)*

Hello everyone! My name is Jordan and I am the developer of [_Stipple Effect_](/projects/stipple-effect), a pixel art editor with animation capabilities that I have been developing on my own for the past six months! I figured now is the right time to share what I've been working on!

<!-- more -->

## Why?

You might be asking yourself why I would go through all this effort when there is plenty of state-of-the-art software available at various price points depending on one's budget.

I develop games as a solo indie dev in my spare time. It is something that I would like to keep doing and potentially take more seriously in the future. I have a couple of game ideas that I've been toying with for several years - since high school, in fact - that are both hugely ambitious. As I began to contemplate if, when and how I could commit to these projects, my focus shifted to the tech stack and workflow I would need in order to develop these games on my own in as short a time span as possible without cutting corners on my creative process and the game's technical implementation details. A key part of that tech stack was a lightweight, flexible, powerful art program that could do a lot more than what I was using at the time.

One of those game ideas is a procedurally generated RPG codenamed _Citizen_. Every facet of worldbuilding in _Citizen_ is procedurally generated rather than hardcoded. This extends far beyond the geography of game worlds to the cultures that inhabit the world, their attire, their languages, and even their weapons, values and philosophies.

Thus, most art assets in the game will be lookup textures that will be modified according to the various generation algorithms at runtime. Iterating on the creation of such assets in traditional art software would be very slow and painstaking, as one would have to build the game or at least run a simulation of the system that incorporated the relevant lookup texture to see the in-game render.

The problem is captured very well by [this video](https://www.youtube.com/watch?v=HsOKwUwL1bE).

That is where _Stipple Effect_ comes in.

## Scripting in _Stipple Effect_

There are three types of scripts in Stipple Effect:

* Automation scripts
* Preview scripts
* Color scripts

Automation scripts take no parameters and return nothing. They merely execute a series of instructions, usually operating on the project(s) that are active in the program. The scripting API is very feature-rich; almost anything that can be accomplished in the editor can be automated via scripting.

![A preview script in action](https://raw.githubusercontent.com/jbunke/se-docs/master/assets/graphics/complex-preview.gif)

Preview scripts, like the above example, can be applied to the preview window to modify the preview of the active project. In the above example, the project contents are being mapped onto an animation of the character swiveling in place so that he can be viewed from all angles.

Color scripts allow for the transformation of the colors of a user-defined scope of pixels in the project. For example, they can be used to turn the entire project greyscale, or to isolate the R (red) color channel of the current selection.
