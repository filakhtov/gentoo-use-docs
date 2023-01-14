# sys-apps/file

### bzip2
Pass the `--enable-bzlib` option to the configure script. Provide an ability to look inside of the BZip2 compressed archives using the `-z` option instead of just reporting the archive type. If the flag is disabled, trying to use `file -z` on the BZip2 compressed archive will produce the `Bad system call` message.

It is safe to disable this flag.

### lzip
Pass the `--enable-lzlib` option to the configure script. Use the `liblz` to provide an ability to look inside of the lzip compressed archives using the `-z` option instead of just reporting the archive type. If the flag is disabled, trying to use the `file -z` on the lzip compressed file will produce the `Bad system call` message.

This flag can be safely disabled.

### lzma
Pass the `--enable-xzlib` option to the configure script. Provide an ability to look inside of the XZ/LZMA compressed archives using the `-z` option instead of just reporting the archive type. If the flag is disabled, trying to use `file -z` on the LZMA compressed archive will produce the `Bad system call` message.

It is safe to disable this flag.

### python
Build and install a `magic` Python module, `libmagic` bindings for Python.

It is safe to disable this flag.

### seccomp
Pass the `--enable-libseccomp` option to the configure script. Use the `libseccomp` library to enable sandboxing using the Kernel syscall filtering mechanism to improve security and minimize the impact of the possible malicious code execution vulnerabilities.

It is recommended to enable this flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install statically linked libraries.

The flag can be safely disabled.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.

### zlib
Pass the `--enable-zlib` option to the configure script. Provide an ability to look inside of the Zlib compressed archives using the `-z` option instead of just reporting the archive type. If the flag is disabled, trying to use the `file -z` on the GZip compressed archive will produce the `Bad system call` message.

It is safe to disable this flag.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.

### zstd
Pass the `--enable-zstdlib` option to the configure script. Use the `libzstd` to provide an ability to look inside of the zstd compressed archives using the `-z` option instead of just reporting the archive type. If the flag is disabled, trying to use the `file -z` on the zstd compressed file will produce the `Bad system call` message.

This flag can be safely disabled.
