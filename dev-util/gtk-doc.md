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
