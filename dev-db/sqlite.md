# dev-db/sqlite

### debug
Pass the `--enable-debug` option to the configure script when enabled together with a `tcl`, a `test` or a `tools` flag. Without these flags append a `-DSQLITE_DEBUG` (`-DNDEBUG` if disabled) option to the `CPPFLAGS` variable for the duration of a build. Print a lot of additional information at runtime. Collect stats on memory allocation, number of calls to allocate and so forth. Enable extra `assert` statements. Provide other runtime debugging means.

This flag should normally be disabled. It is only useful for debugging SQLite library itself or as part of other applications.

### doc
Install additional documentation in an HTML format into a `/usr/share/doc/sqlite-<VERSION>/html` directory.

It is safe to disable this flag.

### icu
Append a `-DSQLITE_ENABLE_ICU` option to the `CPPFLAGS` variable for the duration of a build. Patch `Makefile.in` to append a `-licui18n` and a `-licuuc` options to the `LIBS` make variable. Use a `libicu` library to provide Unicode handling abilities. SQLite will support Unicode regular expressions with `REGEXP`, pattern matching with `LIKE`, case manipulation via `LOWER()` and `UPPER()` and so on.

This can be safely disabled, however is necessary if there is a need to deal with Unicode data inside of SQLite databases.

### readline
Pass the `--enable-readline` option to the configure script. If enabled together with a `tcl`, a `test` or a `tools` flag then also pass `--with-readline-inc=` option with a path to a readline includes directory. Provide support for an autocompletion and a history features for an `sqlite3` shell mode.

It is safe to disable this flag especially if there is no need to deal with an SQLite shell.

### secure-delete
Append a `-DSQLITE_SECURE_DELETE` option to the `CPPFLAGS` variable for the duration of a build. This changes a default value for a runtime `PRAGMA secure_delete` from `off` to `on` to enable a secure delete behavior. When enabled, SQLite will overwrite deleted content with zeroes.

In theory, this flag can increase security, however it won't properly work with journalled filesystems and SSD disks.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked `libsqlite3` library.

It is not recommended to enable this flag, unless there is an explicit need for a static library.

### tcl
Pass the `--enable-tcl` option to the configure script. Pass a `HAVE_TCL=1` variable for all invocations of a `make` command. Build and install an SQLite extension for a Tcl interpreter.

This flag should normally be disabled, unless there is a need to run or develop Tcl/Tk scripts that use SQLite databases.

### test
Pass the `--enable-tcl` option to the configure script. Execute `make test` command after the main build is complete. If `debug` flag enabled, execute `make fulltest` instead. Run a test suite provided with a source code (written primarily in Tcl) after the main build is completed. This will extend an overall build time.

The flag should normally be disabled as it is only useful for the Gentoo team, testers or developers.

### tools
Invoke `make` command with a set of targets to build SQLite tools. Build and install a `changeset`, `dbdump`, `dbhash`, `rbu`, `scrub`, `showdb`, `showjournal`, `showshm`, `showstat4`, `showwal`, `sqldiff`, `sqlite3_analyzer`, `sqlite3_checker`, `sqlite3_expert` and a `sqltclsh` commands.

This flag can be safely disabled, unless there is a need to manipulate SQLite databases directly via one of the tools provided.
