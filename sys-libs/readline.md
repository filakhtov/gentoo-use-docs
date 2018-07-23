# sys-libs/readline

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked versions of `libhistory` and `libreadline` libraries.

This flag should only be enabled if there is a need for the static libraries.

### utils
Run a configure script from `examples/rlfe` directory followed by the `make` command. Build and install an `rlfe` binary (ReadLine Front-End) that can execute an interactive program and let readline handle input line editing.

This flag should be enabled if there is a need to use the Readline Front-End.
