# app-arch/gzip

### pic
Export a `DEFS` variable with a `NO_ASM` value for the configure script. Disable assembly code optimization. Build PIC (Position Independent Code) binaries.

Enabling this flag improves security, but disabling it improves performance.

### static
Append a `-static` option to the `CFLAGS`, `CXXFLAGS`, `FFLAGS`, `FCFLAGS` variables for a duration of the build. Build and install statically linked binaries.

This flag should only be enabled if there is a need for static binaries.
