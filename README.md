# Portfolio

I'm Will Stach (aka hyenasky), a CS student at the University of Utah who is fascinated by computer architecture and system software design. This is some of the technical work I've done in my own time.

## The XR/station Project

**XR/station** is a fully handmade computer platform, 100% designed and implemented by myself. It began in 2018, inspired by the aesthetics of old computers like the SGI Indy, SPARCstation, and NeXTstation, and has been carried forward by a fascination with computers and a deep desire to learn everything about them. There's a demo emulator on the web [here](https://xrarch.github.io). In March of 2023, I decided to create a new fully self-hosting toolchain with an improved programming language, and rewrite everything using that. Here's the progress.

**Projects:**

- [x] [xremu](https://github.com/xrarch/xremu) is the emulator, written using C and the SDL library. It has support for simulating multiple CPUs in an SMP configuration. It is capable of being compiled with Emscripten to run in a web browser.
- [x] [newsdk](https://github.com/xrarch/newsdk) is a fully self-hosted development toolchain.
    - [x] [Jackal](https://github.com/xrarch/newsdk/tree/main/Jackal) is a self-hosted programming language for systems implementation. Self-hosted means all newsdk tools (including the Jackal compiler itself) are implemented in the Jackal language.
    - [x] [xrbt](https://github.com/xrarch/newsdk/tree/main/XrBuildTool) is a custom build system, supporting multithreaded builds.
    - [x] [xrasm](https://github.com/xrarch/newsdk/tree/main/XrAsm) is a retargetable assembler.
    - [x] [xrlink](https://github.com/xrarch/newsdk/tree/main/XrLink) is a retargetable linker, with support for static and dynamic linking of a custom object file format.
- [x] [a4x](https://github.com/xrarch/a4x) is the firmware, written in Jackal.
- [ ] [MINTIA2](https://github.com/xrarch/mintia2) is my in-progress operating system. It is portable and supports SMP preemptive multitasking. It will soon support demand paging, dynamic linking, memory-mapped files, and other features, as its predecessor [MINTIA1](https://github.com/xrarch/mintia) did.

**XR/station Writings:**

- [Architecture Handbook](https://raw.githubusercontent.com/xrarch/pdfs/main/xr17032handbook.pdf)
- [Platform Design Handbook](https://raw.githubusercontent.com/xrarch/pdfs/main/xrcomputerbook.pdf)
- [Executable Format Specification](https://raw.githubusercontent.com/xrarch/pdfs/main/xlospec.pdf)
- [Firmware Manual](https://raw.githubusercontent.com/xrarch/pdfs/main/a4xmanual.pdf)

<a href="https://github.com/xrarch/a4x"><img src="https://raw.githubusercontent.com/hyenasky/hyenasky/main/a4xfirmware.png" width="280" alt="a4x Boot Picker"></a><a href="https://github.com/xrarch/mintia"><img src="https://raw.githubusercontent.com/hyenasky/hyenasky/main/oldmintia.png" width="280" alt="Dragonfruit MINTIA"></a><a href="https://github.com/xrarch/aisix"><img src="https://raw.githubusercontent.com/hyenasky/hyenasky/main/oldaisix.png" width="280" alt="Aisix"></a>

## Booting the April 1991 Windows NT Build

In November 2023, ex-Microsoft engineer Jeff Parsons ([@jeffpar](https://github.com/jeffpar)) [uploaded some disk images to GitHub](https://github.com/jeffpar/pcjs-miscdisks/commit/745b046f85939929f6b87baa8e573d2517adc657) which contained a very old Windows NT build, from April 1991, near the dawn of its development. Investigation revealed that this NT build was built for the MIPS R3000 processor, making it the only known build of Windows to run on a 32-bit-only MIPS chip.

After being recruited by the BetaWiki community, I was able to jerry-rig a [machine in MAME](https://github.com/hyenasky/mame-r3kjazz) for the "R3000 Jazz" internal development board that this NT build ran on, back-port the ARC firmware to the R3000 chip, and use it to successfully boot the [earliest Windows NT build](https://betawiki.net/wiki/Windows_NT_3.1_April_1991_build) currently known.

There were also contributions by [@substanc3-dev](https://github.com/substanc3-dev), who created a script to work around a mismatch between VirtualBox and MAME's serial emulation that was preventing the NT kernel debugger from operating.

<img src="https://raw.githubusercontent.com/hyenasky/hyenasky/main/arc3000.png" width="280" alt="First successful initialization of the R3000 ARC port"><img src="https://raw.githubusercontent.com/hyenasky/hyenasky/main/aprilntboot.png" width="280" alt="R3000 NT starts to boot over debugger console on OS/2"><img src="https://raw.githubusercontent.com/hyenasky/hyenasky/main/aprilntrunning.png" width="280" alt="Ancient NT running :)">