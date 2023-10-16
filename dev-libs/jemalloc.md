# dev-libs/jemalloc

### debug
Pass the `--enable-debug` option to the configure script to enable assertions and other sanity checks, and to disable inline functions. This can aid with debugging Jemalloc itself or applications linked against it.

This flag should normally be disabled.

### lazy-lock
Pass the `--enable-lazy-lock` option to the configure script. This option enables lazy locking, which means that Jemalloc will only lock its mutexes when running in a multi-threaded context. This can improve performance in some cases, but it is fragile and can lead to deadlocks if applications do not correctly detect multi-threaded mode.

It is generally recommended to disable this option, unless you have a specific need for lazy locking and are aware of the risks involved.

### prof
Pass the `--enable-prof` option to the configure script to enable support for heap profiling and leak detection. This functionality can be controlled via `mallctl()` calls to various `prof.`, `opt.prof*` and `config.prof*` options at runtime.

This flag should normally be disabled because profiling can have significant performance impact.

### stats
Pass the `--enable-stats` option to the configure script to allow collecting memory usage statistics. This statistics contains information on system calls, current memory usage, fragmentation, etc.

This flag should normally be disabled, because it has performance overhead.

### xmalloc
Pass the `--enable-xmalloc` option to the configure script to enable abort-on-out-of-memory support. In this mode, the program will drop core (by calling `abort()`) and print a diagnostic message to the standard error output, instead of returning the failure to the caller.

It is recommended to disable this option to avoid hard crashes in applications.
