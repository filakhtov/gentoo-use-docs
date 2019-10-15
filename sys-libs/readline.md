# sys-libs/readline

### split-usr
If the flag is enabled some of the produced libraries will be installed into the `/lib` directory, instead of the `/usr/lib` directory, so that they are available during the early boot when the `/usr` partition is not yet mounted.

This flag is necessary to boot the system that has separated `/usr` partition, but otherwise can be safely disabled.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked versions of `libhistory` and `libreadline` libraries.

This flag should only be enabled if there is a need for the static libraries.

### unicode
When enabled ensure that the `unicode` flag is enabled for the [sys-libs/ncurses](../sys-libs/ncurses.md) package and use the `libncursesw` (wide unicode version) instead of `libncurses`.

It is recommended to enable this flag to properly support characters from multibyte encodings, however it can be safely disabled if there is no need to use languages other than English.

### utils
Run a configure script from `examples/rlfe` directory followed by the `make` command. Build and install an `rlfe` binary (ReadLine Front-End) that can execute an interactive program and let readline handle input line editing.

This flag should be enabled if there is a need to use the Readline Front-End.
