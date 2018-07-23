# sys-apps/less

### pcre
Pass the `--with-regex=pcre` (`posix` when disabled) option to the configure script. Use `libpcre` library to handle regular expressions and provide support for the PCRE (Perl-Compatible Regular Expressions) syntax while searching for patterns.

It is safe to disable the flag.

### unicode
Export a `ac_cv_lib_ncursesw_initscr=yes` (`no` if disabled) and `ac_cv_lib_ncurses_initscr=no` (`yes` when enabled) variables for the configure script. Use a "wide" version of the ncurses library for proper unicode character set handling.

This flag should be enabled if there is a need to deal with Unicode characters, e.g. from Japanese language.
