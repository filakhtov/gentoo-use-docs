# app-editors/gedit

### introspection
Pass the `--enable-introspection` option to the configure script. Generate and install the `Gedit-3.0.gir` and the `Gd-1.0.gir` GIR metadata files to provide dynamic bindings for the editor itself and the `libgd` library to languages other than C using the GObject Introspection infrastructure.

It is safe to disable the flag, however some Gedit plugins might require this.

### python
Prepare environment for the configure script to find an appropriate version of Python interpreter. Pass the `--enable-python` option to the configure script. Build support for the Python-based plugins and build some of the bundled plugins, e.g. quick open, Python console, external tools.

The flag can be safely disabled, however Python plugins won't be available.

### spell
Pass the `--enable-spell` option to the configure script. Use the gspell library to provide spell-checking features.

This flag should be enabled if there is a need for spell-checking.

### test
Start a new Xvfb session and execute the `make check` command inside of it when the main build is completed to run the test suite provided with the source code. This will extend a build time.

This flag should normally be disabled as these tests are mainly used by the developers, testers and the Gentoo team.

### vala
Prepare environment for the configure script to find an appropriate version of vala files. Pass the `--enable-vala` option to the configure script. Provide an ability to use Gedit plugins written in Vala.

This flag should be enabled if there is a need to use or develop Vala plugins.
