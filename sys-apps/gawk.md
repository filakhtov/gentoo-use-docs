# sys-apps/gawk

### forced-sandbox
Patch the `main.c` file to enable the `--sandbox` runtime option by default. This will disable `system()` function, input and output redirections and dynamic extensions support. This is usually used by maintainers when building systems that integrate code scripts from a variety of sources, and it's not easy to make sure everyone uses the `--sandbox` flag all the time.

This flag should normally be disabled, otherwise it will break scripts that rely on disabled functionality.

### mpfr
Pass the `--with-mpfr` option to the configure script. Use a `gmp` and `mpfr` libraries to handle an arbitrary precicion arithmetic on numbers. Provide an `-M` (aka `--bignum`) runtime option support.

It is safe to disable the flag.

### nls
Pass the `--enable-nls` option to the configure script. Use a Gettext library to provide an ability to translate programs messages into various languages based on the system locale.

This flag can be safely disabled unless there is a need for a non-English language.

### readline
Pass the `--with-readline` option to the configure script. Enable completion and history support via a `libreadline` library. Support command names, source file names, non-numeric command arguments and variable names completion.

It is safe to disable the flag.
