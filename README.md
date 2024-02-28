# hello!

I'm hyenasky (aka 'will'). I'm a computer science student who is fascinated by computer architecture, and systems software design.

## Portfolio

### The XR/station Project

[XR/station](https://xrarch.github.io) is a fully handmade RISC workstation platform, 100% designed and implemented by myself. It was inspired in 2018 by old computers like the SGI Indy, SPARCstation 20, and NeXTstation, and has been carried forward by my fascination with computers and a deep desire to learn everything about them.

This project has a pretty ludicrous scope of subprojects. These subprojects are roughly divided into an "old" and "new" world, as the software half of the platform design is being completely rewritten.

#### Old World:

- [x] [MINTIA (dragonfruit)](https://github.com/xrarch/mintia) was the operating system. It supported preemptive multitasking, demand paging, dynamic linking, file mapping, and other fancy features (no SMP though, and stuck at 32 bits!).
- [x] [sdk](https://github.com/xrarch/sdk) was a development toolchain written in Lua.
    - [x] [dragonfruit](https://github.com/xrarch/sdk/tree/master/dragonfruit) was a (very crummy) systems programming language with RPN syntax.
    - [x] [asmfx](https://github.com/xrarch/sdk/tree/master/asmfx) was a retargetable assembler.
    - [x] [xoftool](https://github.com/xrarch/sdk/tree/master/xoftool) was a retargetable linker, with support for static and dynamic linking of a custom object file format.
- [x] [a3x](https://github.com/xrarch/a4x) was the old firmware, written in dragonfruit.
- [x] [aisix](https://github.com/xrarch/aisix) was an early attempt to write a UNIXy operating system. It supported preemptive multitasking.
- [x] **emu** was an early emulator written in Lua, using the Love2D framework.

I got all of that done, but unfortunately, the largest parts were created with a very, very bad programming language that I created when I was 15 years old. It unfortunately now amounts to about 150,000 lines, so rewriting it obviously isn't an option. SIKE! Around March 2023, I decided to do a new self-hosted toolchain and rewrite everything using that. Here's the progress:

#### New World:

- [x] [xremu](https://github.com/xrarch/xremu) is the emulator, written using C and the SDL library. It has support for simulating multiple CPUs in an SMP configuration. It is capable of being compiled with Emscripten to run in a web browser.
- [x] [a4x](https://github.com/xrarch/a4x) is the firmware, written in Jackal. It supports hot-switching to the old a3x firmware to boot "old world" operating systems.
- [ ] [newsdk](https://github.com/xrarch/newsdk) will be a fully self-hosted development toolchain.
    - [x] [Jackal](https://github.com/xrarch/newsdk/tree/main/Jackal) is a self-hosted programming language for systems implementation. Self-hosted means: **all** newsdk tools (including the Jackal compiler itself) are implemented in the Jackal language.
    - [ ] [xrbt](https://github.com/xrarch/newsdk/tree/main/XrBuildTool) will be a custom build system, supporting multithreaded builds.
    - [ ] [xrasm](https://github.com/xrarch/newsdk/tree/main/XrAsm) will be a retargetable assembler.
    - [ ] [xrlink](https://github.com/xrarch/newsdk/tree/main/XrLink) will be a retargetable linker, with support for static and dynamic linking of a custom object file format.
- [ ] [MINTIA (Jackal)](https://github.com/xrarch/mintia2) will be the rewritten, new and improved operating system. It will support SMP, preemptive multitasking, demand paging, dynamic linking, file mapping, and other fancy features.

### Booting the April 1991 Windows NT Build

In November 2023, ex-Microsoft engineer Jeff Parsons ([@jeffpar](https://github.com/jeffpar)) randomly [uploaded some disk images to GitHub](https://github.com/jeffpar/pcjs-miscdisks/commit/745b046f85939929f6b87baa8e573d2517adc657) which contained a very old Windows NT build, from April 1991, near the dawn of its development.

Investigation revealed that this NT build was built for the MIPS R3000 processor, making it the only known build of Windows to run on a 32-bit-only MIPS chip.

In the span of about 5 days, I was able to jerry-rig a [machine in MAME](https://github.com/hyenasky/mame-r3kjazz) for the "R3000 Jazz" internal development board that this NT build ran on, port the ARC firmware to the R3000 chip and get it to run, and successfully boot the [earliest Windows NT build](https://betawiki.net/wiki/Windows_NT_3.1_April_1991_build) currently known. I did this work almost single-handedly except for some last minute contributions by [@substanc3-dev](https://github.com/substanc3-dev), who created a script to work around a bug in VirtualBox's serial emulation that was preventing the NT kernel debugger from operating.

<img src="https://raw.githubusercontent.com/hyenasky/hyenasky/main/arc3000.png" width="280"><img src="https://raw.githubusercontent.com/hyenasky/hyenasky/main/aprilntboot.png" width="280"><img src="https://raw.githubusercontent.com/hyenasky/hyenasky/main/aprilntrunning.png" width="280">