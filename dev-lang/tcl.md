# dev-lang/tcl

### debug
Pass the `--enable-symbols` option to the configure script. Build Tcl with debugging symbols.

This flag should normally be disabled.

### threads
Pass the `--enable-threads` option to the configure script. Enable support for multi-threading in Tcl. The thread extension creates threads that contain Tcl interpreters, and it lets you send scripts to those threads for evaluation. Additionally, it provides script-level access to basic thread synchronization primitives, like mutexes and condition variables.

It is safe to disable this flag if multithreading is not required.
