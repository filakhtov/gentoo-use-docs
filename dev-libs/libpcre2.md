# dev-libs/libpcre2

### bzip2
Pass the `--enable-pcre2grep-libbz2` option to the configure script. Link the `pcre2grep` tool against the `libbz2` library to handle files compressed with BZip2 algorithm.

This flag should be enabled if there is a need to search for patterns in BZip2 archives.

### jit
Pass the `--enable-jit` and the `--enable-pcre2grep-jit` options to the configure script. Enable Just-In-Time compiling support for both the `libpcre2` library and the `pcre2grep` tool for faster matching.

It is recommended to enable this flag if platform supports the JIT compilation.

### libedit
Pass the `--enable-pcre2test-libedit` option to the configure script. Link the `pcre2test` against the `libedit` library. Read terminal input using the `libedit` library to provide line editing and history facilities.

This flag can be safely disabled.

### pcre16
Pass the `--enable-pcre2-16` option to the configure script. Build and install a library for 16-bit characters support. It is recommended to enable `unicode` flag together with this flag to support `UTF-16` encoding.

This flag can be safely disabled.

### pcre32
Pass the `--enable-pcre2-32` option to the configure script. Build and install a library for 32-bit characters support. It is recommended to enable `unicode` flag together with this flag to support `UTF-32` encoding.

This flag can be safely disabled.

### readline
Pass the `--enable-pcre2test-libreadline` option to the configure script. Link the `pcre2test` binary against the `libreadline` library to allow reading terminal input using the `libreadline` library and provide line editing and history facilities.

This flag can be safely disabled.

### recursion-limit
Pass the `--with-match-limit-depth=8192` option (instead of `MATCH_LIMIT`) to the configure script. Normally, recursive matching is done up until the maximum amount of stack (or heap) is used. Enabling this option will limit recursion to `8192` calls.

This option should normally be enabled to cut execution early and save resources unless there is a specific need to deal with a recursive pattern matching that can hit this limit.

### split-usr
If the flag is enabled some of the produced libraries will be installed into the `/lib` directory, instead of the `/usr/lib` directory, so that they are available during the early boot when the `/usr` partition is not yet mounted.

This flag is necessary to boot the system that has separated `/usr` partition, but otherwise can be safely disabled.

### static-libs
Pass the `--enable-static` option to the configure script.

### unicode
Pass the `--enable-unicode` option to the configure script. Enable support for Unicode and UTF encodings. As well as supporting UTF strings, Unicode support includes support for the \P, \p, and \X sequences that recognize Unicode character properties, but only the basic two-letter properties such as Lu are supported.

It is recommended to enable this flag as Unicode character set is everywhere nowadays.

### zlib
Pass the `--enable-pcre2grep-libz` option to the configure script. Link the `pcre2grep` tool against the `libz` library to handle files compressed with zlib algorithm.

This flag should be enabled if there is a need to search for patterns in zlib compressed data.
