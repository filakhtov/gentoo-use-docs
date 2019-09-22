# sys-libs/gdbm

### berkdb
Passes the `--enable-libgdbm-compat` option to the configure script. Builds `libgdbm_compat` - a compatibility layer which provides UNIX-like dbm API.

It is recommended to keep this flag enabled so applications that can utilize Berkeley DB API are able to use GNU dbm instead.

### exporter
The flag passes the `--enable-gdbm-export` option to the configure script. Build and install `gdbmexport` tool that can convert gdbm database from old format into the new flat format.

This flag can be safely disabled, unless there is a need to convert GNU dbm databases from old format.

### nls
Passes the `--enable-nls` option to the configure script. Enables a support to display program messages in a different language.

It is safe to disable the flag, unless non-English language is desired, e.g. for help texts and command prompts.

### readline
This flag passes the `--with-readline` option to the configure script. Provides an ability to edit an input line in an interactive mode of `gdbmtool` tool.

It is safe to disable the flag.

### static-libs
Passes the `--enable-static` option to the configure script. This will produce statically linked libraries. If disabled, `.la` files will be removed from build tree before a package is installed.

It is recommended to disable this flag unless there is an explicit need for static GNU dbm libraries, e.g. for development purposes.
