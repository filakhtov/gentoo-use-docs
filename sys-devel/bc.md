# sys-devel/bc

### readline
This flag overrides (disables) the `libedit`. Pass the `--with-readline` and the `--without-libedit` options to the configure script. Use the `libreadline` library to provide editing, history and autocompletion features for an interactive mode. Provide the `history` command for the interactive mode to show or change a number of history entries remembered.

This flag should be enabled if there is a need to use an interactive mode.

### libedit
Only works if the `readline` flag is disabled. Pass the `--with-readline` option to the configure script. Use the `libedit` library to provide editing, history and autocompletion features for an interactive mode. Provide the `history` command for the interactive mode to show or change a number of history entries remembered.

This flag should be enabled if there is a need to use an interactive mode.

### static
Append the `-static` flag to the `LDFLAGS` variable for a duration of the build. Install a statically linked version of the `bc` and `dc` tools.

This flag should be only enabled if there is an explicit need for the static binaries.
