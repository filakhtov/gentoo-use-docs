# dev-util/gtk-doc

### debug
Pass the `--enable-debug` option to the configure script. Produce a lot of debug output during runtime, while parsing source code and generating documentation.

This flag should normally be disabled.

### doc
Install additional documentation and template `Makefile.am` file that can be used to integrate Gtk-Doc into a project to the `/usr/share/doc/gtk-doc-<VERSION>` directory.

It is safe to disable the flag.

### emacs
Compile and install the `gtk-doc.el` Emacs file to provide an ability to quickly pull up or update documentation header for functions.

It is safe to disable this flag.

### highlight
Pass the `--with-highlight=source-highlight` option to the configure script. Use the GNU source-highlight tool for syntax highlighting of examples provided in the generated documentation.

The flag can be safely disabled.

### test
Execute the `make check` command after the main build is completed to run the test suite provided with the source code and check for regressions. This will extend overall build time.

This flag should normally be disabled, because it is primarily oriented towards `gtk-doc` developers, testers and maintainers.

### vim
Only works with if the `highlight` flag is enabled. Change the value of `--with-highlight=` option to `vim`. Use vim editor to provide syntax highlighting instead of source-highlight. See `hightligh` flag for more details.

It is safe to disable this flag.
