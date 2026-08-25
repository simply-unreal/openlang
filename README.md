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
- [Functions](#functions)
- [Conditions](#conditions)

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

Basic variable syntax: `name: type = value;`

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
compiler = "Openlang"
```

By default variables are statically typed (which means after they are assigned a type it cannot be changed). However if you
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

### Functions

Basic function syntax: `fn name(parameters) return_type:`

Examples:
```
fn add(a: i32, b: i32) i64:
    return a + b

fn get_name() str:
    return "Alex"

fn is_alive(health: i32) bool:
    return health > 0
```

If you want a function that doesnt return anything:
```
fn print_name(name: str) void:
    print(name)
```

Functions also have return type inference:
```
fn do_something():
    print("Hello World!")
    // this function returns void
```

For functions that should have a default parameter value you can do this:
```
fn find_user(username: str = "admin"):
    // do user stuff
```

Functions also allow overloading
```
fn print_something(val: i32):
    print(val)

fn print_something(val: str):
    print(val)
```

If the your function might return a value you can use ? which indicates it might return a value or not:
```
fn add(value1: i32, value2: i32) i64?:
    // doesnt return a i64
```

An extremely cool feature in Openlang is multiple return values:
```
fn return_multiple_vals() i64, str:
    return 32, "Hello World!"
    // this returns 32 and "Hello World!"
```

To handle multiple return values you can do something like this:
```
i64_val: i64, str_val: str = return_multiple_vals() // i64_val = 32 and str_val = "Hello World!"
```

### Conditions

There are many different types of condition statements in Openlang such as:

- if / elif / else

- when

- match

- unless

- try / catch

The universal standard are if statements which you probably already seen from other programming languages:

```
if health > 0:
    print("Alive")
else:
    print("Dead")
```

A cool feature of if statements in Openlang is range conditions. Instead of:
```
if health >= 1 and health <= 25:
    warn()
```
You could do this:
```
if health in 1..25:
    warn()
```
Much cleaner right?

The next type of conditions in Openlang are when conditions:
```
when status:
    0:
        print("Loading")
    1:
        print("Ready")
    2:
        print ("Error")
    else:
        print("Unknown status")
```
This could replace a lot of ugly if elif chains.

If you want to use something more powerfull we have match statements:
```
match command:
    "start":
        start()
    "stop":
        stop()
    "restart":
        restart()
    _:
        print("Unknown command")
```

A more niche condition statement is the unless condition:
```
unless connected:
    connect()
```
You can use this instead of:
```
if not connected:
    connect()
```
Its basically just syntactic sugar but it can make code very readable.

The final condition statement is try / catch. You probably already know this from languages like C++ or Python:
```
try:
    file.read()
catch error:
    print(error)
```