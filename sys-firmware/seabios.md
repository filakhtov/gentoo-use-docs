# sys-firmware/seabios

### binary
Download and install a pre-compiled binary version of the firmware, instead of building it using the source code. Building from source is not supported by the upstream maintainer and no bug reports will be accepted by them, unless using binary or compile using recommended toolchain.

This flag should normally be enabled, unless there is an absolute need to modify the source, apply a patch or run a debugger.

### debug
Set the `CONFIG_DEBUG_LEVEL` build variable to `8` to enable a lot of diagnostic information without flooding the serial port (levels above 8 will frequently cause too much data).

This flag should only be enabled for debugging and troubleshooting, and when asking for help from upstream via their mailing list.

### seavgabios
Build (if the `binary` flag is disabled) and install `vgabios*.bin` binary firmware images - a SeaVGABIOS sub-project of the SeaBIOS project that provides an open source implementation of a 16bit X86 VGA BIOS.

This flag should be enabled if there is a need to use emulated graphics.
