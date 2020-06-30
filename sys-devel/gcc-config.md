# sys-devel/gcc-config

### native-symlinks
Pass the `USE_NATIVE_LINKS=yes` (`no` if the flag is disabled) variable to the make command. This will instruct the `gcc-config` command to create "native" (unprefixed) symlinks, such as `gcc` and `g++`, pointing to their CTARGET counterparts, such as `x86_64-pc-linux-gnu-gcc` and `x86_64-pc-linux-gnu-g++` when switching toolchain versions.

It is recommended to enable this flag, otherwise many tools might not be able to find these binaries.
