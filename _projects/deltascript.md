---
title: DeltaScript
description: "Lightweight scripting language skeleton designed to be easily extended for the specification and implementation of domain-specific languages"
gh-link: "https://github.com/jbunke/deltascript"
status: "In development"
start-year: 2024
end-year: 2024
index: 1
---

## Overview
*DeltaScript* is a concise, statically typed scripting language that is designed to be extended. Its extensions can define new data types, namespaces and functions, but inherit their syntax from *DeltaScript*. Thus, *DeltaScript* extensions form a family of syntactically identical [domain-specific languages](https://en.wikipedia.org/wiki/Domain-specific_language) that share an underlying standard library of primitive types and native functions.

## Example script
```js
// accepts an input color as a parameter
// returns a list of colors transformed from input in various ways
(~ color input -> color<>) {
    ~ (color -> color) color_functions = [
         ::red, ::green, ::blue, ::greyscale, ::random_color, ::white
    ];
    ~ color<> channels = new color<>;

    for (f in color_functions)
        channels.add(f.call(input));

    return channels;
}

// helper functions that transform a color
greyscale(~ color c -> color) {
    int avg = (c.r + c.g + c.b) / 3;
    return rgba(avg, avg, avg, c.a);
}

// white(), random_color() match signature of other helpers but ignore parameter
// uses the hex code color literal #ffffff - white - RGB[255, 255, 255]
white(~ color c -> color) -> #ffffff
random_color(~ color c -> color) -> rgba(rc(), rc(), rc(), 0xff)
// uses the hexadecimal integer literal 0x100 = 256
rc(-> int) -> rand(0, 0x100)

// isolate a color's RGB channels
red(~ color c -> color) -> rgba(c.r, 0, 0, c.a)
green(~ color c -> color) -> rgba(0, c.g, 0, c.a)
blue(~ color c -> color) -> rgba(0, 0, c.b, c.a)
```

## Development
* Designed and implemented a skeletal programming language grammar
* Implemented an programming language interpreter that interprets *DeltaScript* code to Java
  * Abstract syntax tree
  * Symbol table
  * Type checking
  * Syntax and semantic error checking; runtime errors safely suspend execution

## To-Do
* Write a formal language specification for *DeltaScript*

## Technologies
#### ANTLR
The *DeltaScript* grammar is implemented with ANTLR.

ANTLR is a parser generator tool that uses the rules of a user-defined [grammar](https://en.wikipedia.org/wiki/Formal_grammar) to generate code in a given target language to easily lex and parse program files that are supposed to conform with the rules of the input grammar.

#### Java
The official implementation of *DeltaScript* is an interpreter that targets Java 17.

## Use Cases
* [Stipple Effect](/projects/stipple-effect) - scripting is implemented with an extension of *DeltaScript* [**[read the API]**](/se/api)

## More information
* [GitHub repository](https://github.com/jbunke/deltascript)
* [Script examples](https://github.com/jbunke/deltascript-examples)