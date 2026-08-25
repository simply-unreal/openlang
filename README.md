# Openlang

## Table of Contents

### Roadmap
- [Phase 1 - Core Language](#phase-1---core-language)
- [Phase 2 - Low-Level Features](#phase-2---low-level-features)
- [Phase 3 - Compiler](#phase-3---compiler)
- [Phase 4 - Standard Library](#phase-4---standard-library)
- [Phase 5 - Tooling](#phase-5---tooling)
- [Phase 6 - First Stable Release](#phase-6---first-stable-release)
- [Long-Term Ideas](#long-term-ideas)
- [Goal](#goal)

### Core Philosophy
- [Core Philosophy](#core-philosophy)

### Syntax
- [Variables](#variables)

## Core Philosophy

- Indentation defines blocks

- No `{}` required

- No semicolons

- Types are explicit when useful

- Openlang should hide syntactic complexity not what the program is doing

- Low level features should look simple

- Avoid symbols like `->` `*` `&`

- Avoid unnecessary keywords and punctuation

## Roadmap

### Phase 1 - Core Language

- Design basic syntax

- Variables and constants

- Basic type system

- Numbers, strings, booleans

- Operators

- if / else

- while and for loops

- Functions

- Comments

### Phase 2 - Low Level Features

- Pointers

- Memory allocation

- References

- Arrays

- Structs

- Manual memory management

- Basic type system

- Primitive types (int, float, char, etc.)

### Phase 3 - Compiler

- Lexer

- Parser

- Abstract Syntax Tree

- Type checking

- Code generation

- Executable generation

- Basic compiler errors

### Phase 4 - Standard Library

- File I/O

- Console I/O

- Strings

- Memory utilities

- Basic collections

- Math functions

### Phase 5 - Tooling

- OpenLang CLI

- Package/module system

- Formatter

- REPL

- Debugging support

- Editor/VS Code support

### Phase 6 - First Stable Release

- Documentation

- Example programs

- Standard library cleanup

- Compiler optimization

- Cross-platform support

- OpenLang 1.0

### Long Term Ideas

- Generics

- Concurrency

- Better optimization

- C interoperability

- Custom memory allocators

### Goal
> Python like readability with C like control over the machine.

## Syntax

### Variables
Basic variable: `name: type = value;`

Examples:
```
age: i32 = 20
active: bool = true
letter: char = 'A'
```

Openlang allows for type inference:
```
age = 20
letter = 'A'
```

By default variables are statically typed which means after they are assigned a type it cannot be changed. However if you
do want dynamically typed variables (which means the type can change after its assigned) you can use the dynamic keyword.
Examples:
```
dynamic age: i32 = 20
dynamic active = true
```
> NOTE: Dynamic typed variables will take up more memory than static typed variables as they have to store there type
alongside the value they hold

But what if you want a variable to not change? Well you can use the const keyword for that.
Examples:
```
const age = 20;
const dynamic num: i32 = 31;
```
