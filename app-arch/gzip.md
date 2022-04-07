# app-arch/gzip

### pic
Export a `DEFS` variable with a `NO_ASM` value for the configure script. Disable assembly code optimization. Build PIC (Position Independent Code) binaries.

Enabling this flag improves security, but disabling it improves performance.

### static
Append a `-static` option to the `CFLAGS`, `CXXFLAGS`, `FFLAGS`, `FCFLAGS` variables for a duration of the build. Build and install a statically linked version of the `gzip`, `gunzip`, `zcat`, `uncompress`, `gzexe`, `zcmp`, `zdiff` and other binaries.

This flag should only be enabled if there is a need for static binaries.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.
