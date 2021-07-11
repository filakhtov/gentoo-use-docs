# dev-libs/libffi

### debug
Pass the `--enable-debug` option to the configure script. Enable assertion macros that are normally no-op. Provide a special dummy function - `ffi_stop_here` for setting a breakpoint during debugging sessions to hook into significant events.

This flag should be disabled. It is only necessary for debugging purposes.

### pax-kernel
Pass the `--enable-pax_emutramp` option to the configure script. Provide an ability to run under PaX-restricted kernel. Memory pages, that contain a dynamically generated code will be marked with `PROT_EXEC` flag. This will ensure that program won't be terminated by the kernel when trying to run non-executable memory but will use "trampolines" that are safely handled by emulation in a PaX kernel (aka `EMUTRAMP`).

This flash should only be enabled on the hardened systems or systems with a PaX-protected kernel.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked `libffi` library.

It is recommended to disable the flag, unless there is an explicit need for the static library.

### test
Execute a `make check` command after the main build is completed. Run test cases provided with a source code.

This flag should normally be disabled as it is mainly useful for the Gentoo team, testers and developers.

### test-bhaible
Only makes sense if the `test` flag is enabled. Run the bhaible (Bruno Haible's) test suite, which is suitable for automation on embedded targets. It runs extremely slowly and can take hours of runtime. When this flag is disabled, entire test suite will be removed from the source tree before running tests.

It is recommended to keep this flag disabled, unless there is an explicit need to run these tests.
