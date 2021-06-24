JIT-asm
=======

*rusini's fast and simple run-time "assembler" and relocating loader for building up "object code" (kind of relocatable machine code), which is emitted by a JIT
compiler code generator, and eventually loading it into target address as executable segment*

The principal beneficiary of this library is to be the upcoming JIT compiler for the [MANOOL](https://manool.org) programming language.

Although called "assembler", it does not pretend to support coding with assembly mnemonics, which is beyond the scope of this subproject. The point is that it
allows you to use symbolic addresses (AKA labels) and multiple assembly sections (corresponding to `.text` and `.rodata` sections in System V ABI) during the
course of incremental code emission, which is suitable for implementing efficient one-pass (tree-walking) code generators.

#### Sample piece of code using the API

You can find an example demostrating most facilities of the library in [test.cc](test.cc).

#### Building the code in the repository

    g++ -{w,std=c++17} -{O3,s} {jit-asm,test}.cc
