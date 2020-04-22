# dev-libs/libbytesize

### doc
Pass the `--with-gtk-doc` option to the configure script. Generate the API documentation using the Gtk-Doc tool and install it into the `/usr/share/gtk-doc/html/libbytesize-<VERSION>` directory.

It is safe to disable the flag.

### python
Pass the `--with-python3` option to the configure script. Build and install Python bindings and provide a Python `Size` class which wraps the `libbytesize` functionality and provides all the features one would expect from a numeric type in Python.

This flag can be safely disabled.

### test
Execute the `make check` command after the main build is completed. Run a test suite provided with the source code. This will extend a build time.

This flag should normally be disabled as it is mainly used by the Gentoo team, testers or developers.

### tools
Pass the `--with-tools` option to the configure script. Build and install the `bscalc` python script that can display sizes in various units, e.g. KiB, MiB, GiB, TiB, and so on.

It is safe to disable the flag.
