# app-shells/bash

### afs
Pass the `--with-afs` option to the configure script. Adjust bash internals to properly work with AFS (Andrew File System) distributed filesystem. Mainly change how permission checks are performed.

This flag should only be enabled if the target system to be running on top of AFS.

### bashlogger
Append a `-DSYSLOG_HISTORY` option to the `CPPFLAGS` variable for the duration of a build. Enable logging of every single bash command that is typed or executed into a syslog.

This flag should never be enabled on any production systems and is useful for restricted environments, e.g. honeypot servers.

### examples
Install various example Bash scripts into a `/usr/share/doc/bash-<VERSION>` directory. This includes examples of completion scripts, strtup files, array manipulations, etc.

This flag can be safely disabled.

### mem-scramble
Pass the `--enable-mem-scramble` and the `--with-bash-malloc` options to the configure script. Use custom `malloc` and `free` functions provided by the bash instead of ones provided by standard library. Overwrite allocated memory (to avoid reading maliciously crafted memory contents) and freed memory (to avoid data leakage). This is a security feature.

It is safe to disable this flag.

### net
Pass the `--enable-net-redirections` option to the configure script. Enable an input and output redirections from and to network hosts using a `/dev/tcp/<HOST>/<PORT>` and a `/dev/udp/<HOST>/<PORT>` notations.

This flag should normally be disabled, unless there is an explicit need to perform network redirection.

### nls
Does nothing when enabled, because NLS support is enabled by default. When disabled, pass the `--disable-nls` option to the configure script. Use a gettext library to provide a localization and messages translation for bash.

It is safe to disable this flag unless there is a need to use bash in a non-English language.

### plugins
Append a `-Wl,-rpath,/usr/lib64/bash` (`lib32` or `lib` for other targets) to the `LDFLAGS` variable for the duration of a build. Execute a `make` command with an `all` and an `others` targets inside of an `examples/loadables` directory. Install additional include files (headers for plugin support routines) and dynamically loadable built-ins (that are usually provided by other system packages, e.g. [sys-apps/coreutils](../sys-apps/coreutils.md)): `basename`, `cat`, `dirname`, `finfo`, `head`, `hello`, `id`, `ln`, `logname`, `mkdir`, `mypid`, `necho`, `pathchk`, `print`, `printenv`, `push`, `pushd`, `realpath`, `rmdir`, `setpgid`, `sleep`, `strftime`, `sync`, `tee`, `truefalse`, `tty`, `uname`, `unlink` and `whoami`.

This flag should normally be disabled, unless there is a need to support loadable bash plugins or use one of the loadable built-ins mentioned above.

### readline
Pass the `--enable-readline`, the `--enable-history` and the `--enable-bang-history` options to the configure script. Provide a tab-completion, history, line editing, proper colorization, screen clearing (e.g. via ctrl+l), etc features. When disabled, patch a global `bashrc` and a skeleton `.bashrc` files to disable a `histappend` option and colorization.

It is highly recommended to enable this flag, especially if bash to be used as an interactive shell.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.
