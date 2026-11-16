# low-level-engineering-blog
Deep dives into C, compilers, and low-level systems architecture.
Technical deep dives into C programming, compilers, memory layout, and operating system internals.

## Published Articles
1. **[Under the Hood of GCC: How a C Program Becomes an Executable](./articles/01-how-gcc-compiles-c/README.md)** — Tracing the 4-stage toolchain from `.c` source to machine binary (`-E`, `-S`, `-c`, linking).

What is GCC?
GCC

GNU Compiler Collection
C compiler available
An open-source compiler toolchain


GCC is a compiler collection that supports multiple programming languages, including:
- C
- C++
- Objective-C
- Fortran
- Ada
- Go
- D
For our C programming journey, we'll primarily use GCC.

One important distinction:
- C = Programming language.
- GCC = Compiler collection and toolchain.
- gcc = Command used to invoke the GCC driver.
