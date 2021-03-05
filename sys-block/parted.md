# sys-block/parted

### debug
Pass the `--enable-debug` option to the configure script. Build and install libraries and binaries with assertions and produce additional output with debugging information at runtime. Note, debugging code has some bugs in it and might cause unusual issues.

This flag should only be enabled for debugging purposes.

### device-mapper
Pass the `--enable-device-mapper` option to the configure script. Use the `libdevmapper` library to properly handle device-mapper devices and partitions, including RAID arrays.

This flag should be enabled if the target system has to deal with device-mapper devices.

### nls
Pass the `--enable-nls` option to the configure script. Use the Gettext library to provide an ability to translate programs messages into various languages based on the system locale settings.

It is safe to disable the flag, unless there is a need to use parted in a non-English language.

### readline
Pass the `--with-readline` option to the configure script. Use the `libreadline` library to provide completion, history and line editing features.

It is safe to disable the flag.

### verify-sig
Download the digital signature file provided with the source code and use it to verify the integrity of the source code archive before extracting it and building the package.

It is safe to disable this flag, and it can be useful for security-oriented users.
