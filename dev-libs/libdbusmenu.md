# dev-libs/libdbusmenu

### debug
Pass the `--enable-massivedebugging` option to the configure script. Print additional debugging statements at runtime. This will produce a lot of additional output, so be wary.

This flag should normally be disabled.

### gtk
Pass the `--enable-gtk` option and append `2` to the `--with-gtk=` option and pass them to the configure script. Build and install the `libdbusmenu-gtk` library that uses GTK+ version 2.x for generating menus and their items.

It is safe to disable this flag.

### gtk3
Pass the `--enable-gtk` option and append `3` to the `--with-gtk=` option and pass them to the configure script. Build and install the `libdbusmenu-gtk3` library that uses GTK+ version 3.x for generating menus and their items.

This flag can be safely disabled.

### introspection
Pass the `--enable-introspection` and `--enable-vala` options to the configure script. Generate the `Dbusmenu-0.4.gir` GIR repository file to  dynamic bindings for the `libdbusmenu` library to languages other than C using the GObject Introspection framework, which is mainly used by the  `Dbusmenu-0.4.vapi` Vala language bindings that also will be installed.

It is safe to disable this flag.

### test
Pass the `--enable-tests` option to the configure script. Build the tests provided with the source code and run `make check` command after the main build is completed to execute them and check for any regressions. If the `gtk` or `gtk3` flag is enabled also start a new Xvfb session and execute the `make check` command with a specific set of tests related to GTK+ code. This will extend the build time.

This flag should normally be disabled, because these tests are primarily useful for the library developers, maintainers and testers.
