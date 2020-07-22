# x11-libs/libdrm

### libkms
Pass the `-Dlibkms=true` (`false` when disabled) option to the meson build script. Build and install the `libkms` library that contains API functions for kernel mode setting abstraction.

It is generally safe to disable the flag.

### valgrind
Pass the `-Dvalgrind=auto` (`false` if disabled) option to the meson build script. Enable additional code that prevents known false positive reports of memory access violation from the Valgrind tool.

This flag should only be enabled for debugging purposes when there is a need to run an application linked againts libdrm libraries under the Valgrind tool.
