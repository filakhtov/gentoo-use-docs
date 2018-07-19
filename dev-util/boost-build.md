# dev-util/boost-build

### examples
Install various example source files into a `/usr/share/doc/boost-build-<VERSION>/exmaples` directory. Examples include hello world C++ app, simple Gettext translation, minimalistic Qt3 application, etc.

This flag can be safely disabled.

### python
Patch a `engine/build.jam` build script to lock a Python version to a currently active target. Pass the `--with-python` option to the `build.sh` script. Install experimental Python scripts for build system management into a `/usr/share/boost-build` directory.

It is safe to disable the flag.

### test
Execute a `test_all.py` script provided with a source code to run test suites. This will extend a build time.

This flag should normally be disabled as it is mainly useful for the Gentoo team, testers and developers.
