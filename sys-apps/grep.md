# sys-apps/grep

### egrep-fgrep
Remove the `egrep` and `fgrep` upstream wrappers that produce:
```
egrep: warning: egrep is obsolescent; using grep -E
```
warnings starting from GNU grep 3.8+, and instead replace them with Gentoo's own wrappers that produce no warnings, so that some old scripts that use these wrappers but don't expect any output on stderr.

It is safe to disable this flag if there is no need to rely on `egrep` or `fgrep` commands.

### nls
Pass the `--enable-nls` option to the configure script. Use a Gettext library to translate programs messages into various languages based on system locale settings.

This flag can be safely disabled unless there is a need to use a non-English language.

### pcre
Pass the `--enable-perl-regexp` option to the configure script. Export a `ac_cv_search_pcre_compile` variable with a location of a `libpcre` library for the configure script. Enable PCRE (PERL compatible regular expressions) support via the `-P` runtime option.

It is safe to disable this flag unless there is a need to use PCRE with grep.

### static
Append a `-static` option to the `LDFLAGS` option for a duration of the build. Build and install statically linked version of the `grep`, `egrep` and `fgrep` binaries.

This flag should only be enabled if there is an explicit need for the static binaries.
