---
title: WACC Compiler
description: "Second-year project for my Computing BEng at Imperial College London: Java-based compiler for a While-like language that compiles to ARM11 assembly code"
gh-link: "https://github.com/jbunke/wacc"
status: "Coursework"
start-year: 2019
end-year: 2019
index: 3
---

*This was a group project that I completed with three coursemates. My individual contributions can be assessed by looking at the [project's commit history](https://github.com/jbunke/wacc/graphs/contributors).*

## Overview
WACC is a teaching language used by Imperial College London, based on the While family of languages used by other universities. Our major project for the spring term of our second year was to fully implement a WACC compiler that compiled to ARM11 assembly code in a group of four. This consisted of a front-end and back-end component.

## Development
* Defined an ANTLR grammar for WACC
* Used ANTLR and our grammar to create a lexer, parser, and abstract syntax tree for WACC programs to be compiled
* Implemented semantic error checking
* Implemented a code generator that generated ARM11 assembly code from the syntax tree

#### Extension
* Built a command-line interface that could execute WACC code

## Technologies
#### ANTLR
The WACC grammar is implemented with ANTLR.

ANTLR is a parser generator tool that uses the rules of a user-defined [grammar](https://en.wikipedia.org/wiki/Formal_grammar) to generate code in a given target language to easily lex and parse program files that are supposed to conform with the rules of the input grammar.

#### Java
The compiler source code was written in Java.

## More information
* [Source code](https://github.com/jbunke/wacc)
