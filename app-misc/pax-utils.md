# app-misc/pax-utils

### caps
Pass the `-Duse_libcap=enabled` option to the meson build command. The `pspax` gains an ability to read capabilities of the processes. If disabled the `pspax` will always print `=` for a `CAPS` column for all processes.

It is safe to disable this flag.

### man
Pass the `-Dbuild_manpages=enabled` option to the meson build command. Build and install manual pages for various utils: `dumpelf`, `scanelf`, `pspax` and `scanmacho`.

This flag can be safely disabled.

### python
Pass the `-Dlddtree_implementation=python` (instead of `sh`) option to the meson build command. This will install a `lddtree.py` script instead of a `lddtree.sh`. A `lddtree.py` is backwards compatible with a `lddtree.sh` but provides some extra features.

It is safe to disable this flag.

### seccomp
Pass the `-Duse_seccomp=true` option to the meson build command. Enable syscalls filtering using a `seccomp` (secure computing mode). Kernel support is required to use the `seccomp`, however it is provided by all modern Kernels.

This is security feature and generally should be enabled.

### test
Pass the `-Dtests=true` option to the meson build command to build the test suite provided with the source code. Execute the `meson test` command to run the tests after the main build is completed and check for any regressions. This will extend the build time.

This flag should normally be disabled because these tests are mainly used by the maintainers, developers and testers.
