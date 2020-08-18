# sys-apps/file

### bzip2
Pass the `--enable-bzlib` option to the configure script. Provide an ability to look inside of the BZip2 compressed archives using the `-z` option instead of just reporting the archive type. If the flag is disabled, trying to use `file -z` on the BZip2 compressed archive will produce the `Bad system call` message.

It is safe to disable this flag.

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

### zlib
Pass the `--enable-zlib` option to the configure script. Provide an ability to look inside of the Zlib compressed archives using the `-z` option instead of just reporting the archive type. If the flag is disabled, trying to use the `file -z` on the GZip compressed archive will produce the `Bad system call` message.

It is safe to disable this flag.
