---
title: DeltaScript
description: "Lightweight scripting language skeleton designed to be easily extended for the specification and implementation of domain-specific languages"
gh-link: "https://github.com/jbunke/deltascript"
status: "In development"
start-year: 2024
end-year: 2025
index: 1
---

## Overview

<!-- TODO - rewrite -->

*DeltaScript* is a concise, statically typed scripting language that is designed to be extended. Its extensions can define new data types, namespaces and functions, but inherit their syntax from *DeltaScript*. Thus, *DeltaScript* extensions form a family of syntactically identical [domain-specific languages](https://en.wikipedia.org/wiki/Domain-specific_language) that share an underlying standard library of primitive types and native functions.

## Example script

```js
// accepts an input "input" color as a parameter
// returns a list of colors transformed from input in various ways
(~ color input -> color<>) {
    ~ (color -> color)[] color_functions = [
         c -> rgba(c.r, 0, 0, c.a),     // isolate red channel
         c -> rgba(0, c.g, 0, c.a),     // isolate green channel
         ::iso_blue,                    // reference to function "iso_blue"
         c -> {
            int avg = (c.r + c.g + c.b) / 3;
            return rgba(avg, avg, avg, c.a);
         },                             // greyscale of color
         c -> rgb(rc(), rc(), rc()),    // random opaque color
         c -> #ffffff                   // the color white
    ];
    ~ color<> channels = <>;            // initializes an empty list of colors

    // iterates through the (color -> color) functions in color_functions
    // calls each function with "input" as input and appends its
    //   return value to "channels"
    for (f in color_functions)
        channels.add(f.call(input));

    return channels;
}

// helper function to isolate the blue channel of a color
iso_blue(~ color c -> color) -> rgba(0, 0, c.b, c.a)

// helper function to generate a random color channel value
// uses the hexadecimal integer literal 0x100 (= 256)
rc(-> int) -> rand(0, 0x100)
```

## Development

<!-- TODO - link for when statement to an article or updated gist -->

* Designed and implemented a programming language grammar in Extended Backus-Naur Form that supports extensions to the language
* Implemented an programming language interpreter that interprets *DeltaScript* code to Java, including:
  * Abstract syntax tree
  * Symbol table
  * Type checking
  * Syntax and semantic error checking; runtime errors safely terminate execution
* Designed and implemented advanced language features:
  * Functional types
  * "when" statement: a more powerful version of the conventional switch statement that supports pattern matching
* Published a [formal language specification](https://github.com/jbunke/deltascript/blob/master/docs/lang-spec.md) and [standard library](https://github.com/jbunke/deltascript/blob/master/docs/std-lib.md)

<!-- TODO - implement a language server and list it here -->

## Technologies

#### ANTLR
The *DeltaScript* grammar is implemented with ANTLR.

ANTLR is a parser generator tool that uses the rules of a user-defined [grammar](https://en.wikipedia.org/wiki/Formal_grammar) to generate code in a given target language to easily lex and parse program files that are supposed to conform with the rules of the input grammar.

#### Java
The official implementation of *DeltaScript* is an interpreter that targets Java 17.

## Use Cases
* [*Stipple Effect*](/projects/stipple-effect) - scripting is implemented with an extension of *DeltaScript* [**[read the API specification]**](https://stipple-effect.github.io/api)

## More information
* [GitHub repository](https://github.com/jbunke/deltascript)
* [Script examples](https://github.com/jbunke/deltascript-examples)