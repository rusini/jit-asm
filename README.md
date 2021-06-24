JIT-asm
=======

*rusini's fast and simple run-time "assembler" and relocating loader for building up object code (kind of relocatable machine code), which is emitted by a JIT
compiler code generator, and eventually loading it into target address as executable segment*

The principal user of this library is to be the upcoming JIT compiler for the MANOOL programming language (https://manool.org).

Although called "assembler", it does not pretend to support coding with assembly mnemonics, which is beyond the scope of the subproject. The point is that it
supports using symbolic addresses (AKA labels) and multiple assembly sections (corresponding to `.text` and `.rodata` sections in System V ABI), which is
suitable for implementing efficient one-pass (tree-walking) code generators.
