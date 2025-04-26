Clang is part of the [[LLVM]] project and as such, directly integrates it into its compilation system.

The most notable difference between [[gcc]] and clang is the IR, or Intermediate Representation ; this allows [[LLVM]] to perform heavy optimizations on the code being compiled. The process is basically like this :

compiler (clang, zig, ...) generates IR code -> LLVM takes in the IR and optimizes it -> the appropriate backend (in the case of clang, C) generates optimized machine code from the IR`

Another notable difference is that clang is more user friendly and can easily cross-compile to multiple targets. It's LLVM backend ensures that many platforms can be used as targets.