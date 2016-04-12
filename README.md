DCPU Emulator & Assembler
=========================

This is an emulator/debugger and a (buggy) assembler for the techcompliant DCPU (formerly notch's in 0x10^c).

Supported hardware
------------------

* DCPU;
* CPU-Control (IACM);
* Clock;
* Keyboard;
* LEM1802;
* EDC;
* M35FD.

Planned hardware
----------------

Everything planned by [Paul](https://github.com/paultech/TC-Specs).

How to build
------------

* Import with IntelliJ idea;
* Install org.lwjgl:lwjgl:3.0.0b from Maven;
* Download and add the 3.0.0b LWJGL natives from [the LWJGL downloads page](https://www.lwjgl.org/download);
* Enjoy!

Usage
-----

```
java -jar DCPU-Toolchain.jar assemble <input file> <output file> [--little-endian] [--disable-shortLiterals]
java -jar DCPU-Toolchain.jar run <file> [--assemble] [--debugger] [--little-endian] [--clock] [--keyboard] [--lem1802] [--edc] [--M35FD=/path/to/file] [--M525HD=/path/to/file] [--console]

Options:
  --little-endian          Treat files as little endian instead of big endian by default.
  --disable-shortLiterals  Disables optimization of short literals (-1 -> 30) to be included in the opcode instead of the next word.
  --assemble               The specified input file is assembly instead of binary and must be assembled at runtime.
  --debugger               Enable the debugger interface.
  --clock                  Adds a clock device.
  --keyboard               Adds a keyboard device.
  --lem1802                Adds a LEM1802 device.
  --edc                    Adds an EDC device.
  --M35FD=path/to/file     Adds an M35FD device with a floppy stored in path/to/file.
  --M525HD=path/to/file    Adds an M525HD device with a hard disk stored in path/to/file.
  --console                Makes the LEM1802s and keyboard work with stdin/stdout. Only works with consoles that support ANSI escape codes (i.e. not cmd, but cygwin does). Flags that would otherwise spawn a window are disabled.
```

Screenshot
----------

![Screenshot of DCPU-Toolchain](https://raw.githubusercontent.com/azertyfun/DCPU-Toolchain/master/res/screenshot.png)
