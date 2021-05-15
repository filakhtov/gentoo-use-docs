# dev-libs/libxslt

### crypt
Pass the `--with-crypto` option to the configure script. Enable a Cryptographical EXSLT (Extensions for XSLT) support for XML documents.

It is safe to disable this flag as EXSLT crypto is extremely rare.

### debug
Pass the following two options to the configure script:
- the `--with-debug` option that is enabling output of debugging information during XSLT processing;
- the `--with-mem-debug` option that is responsible for replacing a memory allocator with one that collects memory usage debugging data.

This flag should normally be disabled, unless there is a need for debugging.

### examples
Install Python code examples how to use `libxslt` into a `/usr/share/doc/libxslt-<VERSION>/python/examples` directory. Only does so if a `python` flag is enabled too.

It is safe to disable the flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libxslt` library.

The flag can safely be disabled unless there is an explicit need for statically linked libraries, e.g. for development purposes.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.
