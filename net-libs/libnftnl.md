# net-libs/libnftnl

### examples
Copy the examples provided with the source code into the `/usr/share/doc/libnftnl-<version>/examples` directory. Examples include how to add, get and delete chains, rules, tables, etc.

This flag should normally be disabled, it is only useful for the developers.

### split-usr
Normally, built `libnftnl` library is installed into the `/usr/lib64` (or `/usr/lib32` on 32-bit systems) directory. When this flag is enabled, however, a copy of the library will be installed into the `/lib64` (or `/lib32`) directory to make it possible to use tools that depend on the `libnftnl` during the early boot on systems that have separate `/usr` partition, before this partition is mounted.

It is safe to disable this flag, unless the system has separate `/usr` partition.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libnftnl` library.

This flag should only be enabled if there is an explicit need for the static library.

### test
Execute the `make check` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the overall build time.

This flag should normally be disabled, because these tests are primarily useful for developers, maintainers and testers.
