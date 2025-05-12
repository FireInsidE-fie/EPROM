---
tags: []
---
A program which reads compiled languages source files and translates them into machine code to be executed.
Usually starts by preprocessing, followed by compilation and then linking of [[Object File]]s.

> [!ERROR] Portability
> The resulting executable programs coming from a compiler are very rarely portable from platform to platform!
> Since they are written directly in machine code targeting the architecture it was compiled on, it cannot easily switch computers and still function!
> For example, compiling a program under [[macOS]] would result in an executable impossible to run natively on [[Windows]], for example.

# Examples of compilers
- [[gcc]]
- [[clang]]
- The Rust Compiler (?)
- ...