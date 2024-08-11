**Old World projects:**

- [MINTIA (dragonfruit)](https://github.com/xrarch/mintia) was the operating system. It supported preemptive multitasking, demand paging, dynamic linking, memory-mapped files, and other fancy features (no SMP though, and stuck at 32 bits!). Was successfully ported to the [fox32](https://github.com/fox32-arch/fox32) architecture.
- [sdk](https://github.com/xrarch/sdk) was a development toolchain written in Lua.
    - [dragonfruit](https://github.com/xrarch/sdk/tree/master/dragonfruit) was a (very crummy) systems programming language with RPN syntax.
    - [asmfx](https://github.com/xrarch/sdk/tree/master/asmfx) was a retargetable assembler.
    - [xoftool](https://github.com/xrarch/sdk/tree/master/xoftool) was a retargetable linker, with support for static and dynamic linking of a custom object file format.
- [a3x](https://github.com/xrarch/a3x) was the old firmware, written in dragonfruit.
- [aisix](https://github.com/xrarch/aisix) was an early attempt to write a UNIXy operating system. It supported preemptive multitasking.
- **emu** was an early emulator written in Lua, using the Love2D framework.
