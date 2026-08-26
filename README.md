# OpenLang

**OpenLang** is a simple, readable, low-level programming language designed to provide the control and performance of C/C++ while reducing difficult syntax and unnecessary language bloat.

> **Simple syntax. Low-level control. No unnecessary complexity.**

## Why OpenLang?

Low-level languages provide programmers with a high degree of control over memory, performance, and system resources. However, that control can often come with complicated syntax, verbose code, and a large number of language features.

OpenLang aims to keep the important parts of low-level programming while making code easier to read, write, and understand.

OpenLang is built around three core principles:

* **Simple** — Keep the language easy to learn and understand.
* **Low-level** — Give programmers direct control over their programs, memory, and resources.
* **Lightweight** — Avoid unnecessary language features, complexity, and runtime bloat.

## Status

OpenLang is currently **in development**.

The language, compiler, standard library, and syntax may change as development continues.

## Hello World

A basic OpenLang program looks like this:

```openlang
import std.io;

fn main() {
    println("Hello World!");
    return 0;
}
```

A program imports the functionality it needs, defines a `main` function, and executes its statements.

## Basic Syntax

OpenLang is designed to use a straightforward and readable syntax.

### Functions

Functions are declared using the `fn` keyword:

```openlang
fn add(i32: a, i32: b) {
    return a + b;
}
```

Functions can be called directly:

```openlang
let result = add(10, 20);

println(result);
```

### Variables

Variables are declared using `let`:

```openlang
let name = "OpenLang"; // requires std.string
let version = 1;
let enabled = true;
```

If you want explicit typing:

```openlang
let name: string = "OpenLang"; // requires std.string
let version: i32 = 1;
let enabled: bool = true;
```

Variable declarations are intentionally concise while remaining readable.

### Conditions

Conditional statements use a simple, familiar syntax:

```openlang
if value > 10 {
    println("Value is greater than 10");
} else {
    println("Value is 10 or less");
}
```

### Loops

Loops are designed to remain simple and readable:

```openlang
let i = 0;

while i < 10 {
    println(i);
    i += 1;
}

for i in range 0..10 {
    println(i);
}
```

### Structs

Structs can be used to define custom data types:

```openlang
struct Person {
    let: str name;
    let: i32 age;
}
```

A struct can then be used to group related data:

```openlang
let person = Person {
    name = "Alex",
    age = 25
};
```

## Memory Model

OpenLang is a low-level language where **the programmer is responsible for memory management and understanding the lifetime of allocated data**.

OpenLang does not aim to hide memory management behind a garbage collector or require a heavy runtime.

Instead, the language can provide features that **assist the programmer with memory management while preserving direct control**.

This approach is intended to provide predictable behavior without removing the programmer's ability to manage memory explicitly.

> **You control the memory. OpenLang helps you manage it.**

OpenLang takes inspiration from the memory and resource control available in C and C++, while aiming to provide a simpler programming experience.

## Standard Library

OpenLang provides a standard library for common functionality.

For example, input/output functionality can be imported with:

```openlang
import std.io;
```

A program using the I/O library can then write output:

```openlang
import std.io;

fn main() {
    println("Hello World!");
    return 0;
}
```

The standard library is currently under development and will expand as OpenLang evolves.

## Design Goals

### Readability

OpenLang code should be easy to understand without requiring programmers to work through unnecessarily complicated syntax.

### Performance

OpenLang is designed for applications where predictable performance and low-level control are important.

### Programmer Control

Programmers should be able to directly control memory and system resources rather than having important behavior hidden behind layers of abstraction.

### Minimalism

Every language feature should have a purpose. OpenLang aims to avoid unnecessary syntax, features, and complexity.

### Familiarity

OpenLang takes inspiration from established low-level languages such as C and C++, making its concepts familiar while providing a cleaner syntax.

## Roadmap

OpenLang is currently **in progress**.

Planned development includes:

* Core language implementation
* Type system
* Memory management facilities
* Functions and control flow
* Structs and user-defined types
* Standard library
* Compiler
* Documentation
* Error handling
* Development tooling

The roadmap may change as the language develops.

## License

OpenLang is released under the **MIT License**.

See [`LICENSE`](LICENSE) for the complete license text.
