# Hello! This is my portfolio.

I'm Will Stach (aka hyenasky), a computer science student from Salt Lake City who is fascinated by computer architecture and system software design. This is some of the technical work I've done.

## The XR/station Project

[XR/station](https://xrarch.github.io) is a fully handmade computer platform, 100% designed and implemented by myself. It began in 2018 after I was inspired by the aesthetics of old computers like the SGI Indy, SPARCstation, and NeXTstation, and has been carried forward by my fascination with computers and a deep desire to learn everything about them.

This project has a large scope of subprojects. These subprojects are roughly divided into an "old" and "new" world, since the software half of the platform design is currently being completely rewritten.

I already got a [full toolchain and operating system](Old.md) done, but the largest parts were created with a very, very bad programming language that I created when I was 15 years old. Around March 2023, I decided to do a new self-hosted toolchain and rewrite everything using that. Here's the progress:

**Projects:**

- [x] [xremu](https://github.com/xrarch/xremu) is the emulator, written using C and the SDL library. It has support for simulating multiple CPUs in an SMP configuration. It is capable of being compiled with Emscripten to run in a web browser.
- [x] [newsdk](https://github.com/xrarch/newsdk) is a fully self-hosted development toolchain.
    - [x] [Jackal](https://github.com/xrarch/newsdk/tree/main/Jackal) is a self-hosted programming language for systems implementation. Self-hosted means all newsdk tools (including the Jackal compiler itself) are implemented in the Jackal language.
    - [x] [xrbt](https://github.com/xrarch/newsdk/tree/main/XrBuildTool) is a custom build system, supporting multithreaded builds.
    - [x] [xrasm](https://github.com/xrarch/newsdk/tree/main/XrAsm) is a retargetable assembler.
    - [x] [xrlink](https://github.com/xrarch/newsdk/tree/main/XrLink) is a retargetable linker, with support for static and dynamic linking of a custom object file format.
- [x] [a4x](https://github.com/xrarch/a4x) is the firmware, written in Jackal. It supports hot-switching to the old a3x firmware to boot "old world" operating systems.
- [ ] [MINTIA2](https://github.com/xrarch/mintia2) is the rewritten, improved operating system. It will support SMP preemptive multitasking, demand paging, dynamic linking, memory-mapped files, and other features.

**XR/station Writings:**

- [Architecture Handbook](https://raw.githubusercontent.com/xrarch/books/main/xr17032handbook/main.pdf)
- [Platform Design Handbook](https://raw.githubusercontent.com/xrarch/books/main/xrcomputerbook/main.pdf)
- [Executable Format Specification](https://raw.githubusercontent.com/xrarch/books/main/documents/xlospec/main.pdf)
- [Firmware Manual](https://raw.githubusercontent.com/xrarch/books/main/documents/a4xmanual/main.pdf)

<a href="https://github.com/xrarch/a4x"><img src="https://raw.githubusercontent.com/hyenasky/hyenasky/main/a4xfirmware.png" width="280" alt="a4x Boot Picker"></a><a href="https://github.com/xrarch/mintia"><img src="https://raw.githubusercontent.com/hyenasky/hyenasky/main/oldmintia.png" width="280" alt="Dragonfruit MINTIA"></a><a href="https://github.com/xrarch/aisix"><img src="https://raw.githubusercontent.com/hyenasky/hyenasky/main/oldaisix.png" width="280" alt="Aisix"></a>

## Booting the April 1991 Windows NT Build

In November 2023, ex-Microsoft engineer Jeff Parsons ([@jeffpar](https://github.com/jeffpar)) randomly [uploaded some disk images to GitHub](https://github.com/jeffpar/pcjs-miscdisks/commit/745b046f85939929f6b87baa8e573d2517adc657) which contained a very old Windows NT build, from April 1991, near the dawn of its development. Investigation revealed that this NT build was built for the MIPS R3000 processor, making it the only known build of Windows to run on a 32-bit-only MIPS chip.

I was recruited by the BetaWiki community and in the span of about 5 days, I was able to jerry-rig a [machine in MAME](https://github.com/hyenasky/mame-r3kjazz) for the "R3000 Jazz" internal development board that this NT build ran on, port the ARC firmware to the R3000 chip and get it to run, and successfully boot the [earliest Windows NT build](https://betawiki.net/wiki/Windows_NT_3.1_April_1991_build) currently known.

I did this work almost single-handedly except for some last minute contributions by [@substanc3-dev](https://github.com/substanc3-dev), who created a script to work around a mismatch between VirtualBox and MAME's serial emulation that was preventing the NT kernel debugger from operating.

<img src="https://raw.githubusercontent.com/hyenasky/hyenasky/main/arc3000.png" width="280" alt="First successful initialization of the R3000 ARC port"><img src="https://raw.githubusercontent.com/hyenasky/hyenasky/main/aprilntboot.png" width="280" alt="R3000 NT starts to boot over debugger console on OS/2"><img src="https://raw.githubusercontent.com/hyenasky/hyenasky/main/aprilntrunning.png" width="280" alt="Ancient NT running :)">