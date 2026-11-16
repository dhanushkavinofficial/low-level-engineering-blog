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
<img width="916" height="776" alt="image" src="https://github.com/user-attachments/assets/7f4fce5c-e7f4-42b7-9b3a-56cdd4ce3a19" />

Stage 1: Preprocessor
The preprocessor handles special instructions beginning with #.

Example:
#include <stdio.h>

#define AGE 23

int main() {
    printf("%d", AGE);
    return 0;
}


What happens?
1. #include <stdio.h> tells the preprocessor to process the standard I/O header.
2. #define AGE 23 defines a macro.
3. Macro references such as AGE are expanded.
The preprocessed output is commonly saved with the .i extension.

Important: The preprocessor does not execute your program. It prepares the source code for compilation.
Stage 2: Compilation
Now the compiler takes the preprocessed C code.

It performs several operations:
- Lexical analysis: identifies tokens.
- Syntax analysis: checks grammatical structure.
- Semantic analysis: checks meaning and types.
- Optimization: improves generated code where appropriate.
- Code generation: generates assembly instructions.
Example:
int result = 10 + 20;


The compiler can translate this into processor-specific assembly instructions.

The output is commonly a .s file.
Stage 3: Assembly
The assembler converts assembly instructions into machine-code instructions.

For example:
mov eax, 30


This is illustrative x86 assembly, not necessarily the exact output for our C example.

The assembler generates an object file:
main.o


An object file contains machine code and additional information, such as symbol and relocation information.

It is not necessarily a complete executable yet.
Stage 4: Linking
Now imagine your program uses:
printf("Hello World");


Your program refers to printf, but its implementation is provided by the C standard library.

The linker resolves external references and combines the required object code and library dependencies.

It produces the final executable.

On Windows:
main.exe


On Linux:
main


One distinction: libraries can be statically linked or dynamically linked. A dynamically linked executable can depend on shared libraries that are loaded when the program runs.
