# sys-apps/ripgrep

### debug
By default, the application is built in the release mode, passing the `--release` option to the `cargo build` command, to enable optimizations and improve performance. When this flag is enabled, skip the `--release` option to build in the debug mode instead.

This flag should normally be disabled.

### pcre
Pass the `--features pcre2` option to the cargo build command to enable support for the `--pcre` or `-P` runtime options, which allow using PCRE (Perl-Compatible Regular Expressions) matching via the `libpcre2` library. This is useful for advanced regular expressions, such as those with look-arounds and backreferences.

It is safe to disable this flag if there is no need to use advanced PCRE capabilities.
