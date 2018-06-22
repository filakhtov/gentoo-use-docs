# dev-lang/perl
### berkdb
Pass the `-Ui_ndbm`, the `-Ui_gdbm` and the `-Di_db` options to the configure script. Pass the `-Di_ndbm` instead of the `-Ui_ndbm` if [sys-libs/db](../sys-libs/db.md) package is of version 1.x. However, if a `gdbm` flag is also enabled pass the `-Di_ndbm`, the `-Di_gdbm` and the `-Di_db` options instead.

Enable support for DBM database using a Berkeley DB implementation. Only a DBM is supported if the `berkdb` flag enabled alone. If `gdbm` flag is also enabled, then NDBM and GDBM formats are also supported.

It is safe to disable this flag.

### debug
Changing this flag will require rebuilding all installed Perl modules. Append a `-debug` prefix to an installation paths. Add a `-g` option to a CFLAGS variable to enable debug mode. Pass a `-DDEBUGGING` option to the configure script. Add an ability to collect and display a lot of debugging information at runtime.

This flag should normally be disabled.

### doc
Build and install an HTML documentation into a `/usr/share/doc/perl-<VERSION>/html` directory. It is mainly a developer oriented documentation.

The flag can be safely disabled.

### gdbm
Adjust a `Makefile.PL` to append a `gdbm` library include path. Pass the `-Ui_db`, the `-Ui_ndbm` and the `-Di_gdbm` options to the configure script. However, if `berkdb` flag also enabled pass the `-Di_db`, the `-Di_ndbm` and the `-Di_gdbm` options instead.

Enable support for GDBM database if enabled alone. If enabled together with a `berkdb` flag it will also provide a support for DBM and NDBM formats.

It is safe to disable the flag.

### ithreads
Changing this flag will require rebuilding all installed Perl modules. Append a `-mutli` and a `-thread` prefixes to an installation paths. Pass `-Dusethreads` option to the configure script. Enable an ithreads (interpreter threads) support.

It is recommended to disable the flag as interpreter threads are quite heavy-weight and aren't popular amongst a Perl community.
