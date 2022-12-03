# x11-libs/libdrm

### valgrind
Pass the `-Dvalgrind=auto` (`disabled` if disabled) option to the meson build script. Enable additional code that prevents known false positive reports of memory access violation from the Valgrind tool.

This flag should only be enabled for debugging purposes when there is a need to run an application linked againts libdrm libraries under the Valgrind tool.
