# dev-lang/python

### bluetooth
Enable support for the L2CAP, RFCOMM, HCI and SCO Bluetooth protocols in the Socket module. When disabled, export the `ac_cv_header_bluetooth_bluetooth_h=no` environment variable for the configure script to disable Bluetooth support.

This flag should be enabled if there is a need for the Bluetooth protocol.

### debug
Pass the `--with-assertions` option to the configure script. Enable runtime assertions in the Python interpreter that will check for certain conditions that always must be true and crash the program if they fail.

This flag should almost always be disabled, especially for production use.

### ensurepip
When this flag is enabled the `ensurepip` module will be installed, which can be used to bootstrap `pip` and `setuptools` using the bundled wheels. When this flag is disabled, the module will be removed from the resulting image before installation.

It is safe to disable this flag, however `venv` will only work with `--without-pip` flag.

### examples
Enabling this flag will install example Python code that comes together with the source code into `/usr/share/doc/python-<VERSION>/examples`.

This flag can be safely disabled. It is only necessary for developers who require exmaple files in order to learn Python.

### gdbm
Build and install the `dbm` module, that provides an interface to the GNU DBM library. `gdbm` objects behave like mappings (dictionaries), except that keys and values are always strings. When the flag is disabled, add the `MODULE__GDBM_STATE=disabled` and `MODULE__DBM_STATE=disabled` to the `Makefile` to prevent the module from being installed.

It is safe to disable this flag.

### libedit
Only works if the `readline` flag is enabled. This would do exactly the same as the `readline` flag, except it would use the `libedit` library under the hood instead.

This flag should only be enabled if there is a need to use `libedit` over `readline`, e.g. for license compatibility issues.

### lto
Pass the `--with-lto` option to the configure script to enable Link Time Optimization when building the package. This will produce a faster Python binary, but will extend the overall build time.

It is safe to disable this flag.

### ncurses
Enables the `_curses`, the `_curses_panel` and the dependent Python modules. These modules provide an interface for portable advanced terminal handling using the `ncurses` library. They also provide window management like functionality in a terminal. If the flag is disabled, add the `MODULE__CURSES_STATE=disabled` and `MODULE__CURSES_PANEL=disabled` to the `Makefile` to avoid installing these modules.

This flag is generally safe to disable. There are quite a few packages in the Portage tree that depend on it however.

### pgo
Pass the `--enable-optimizations` option to the configure script and export the `PROFILE_TASK` environment variable with profiler configuration. Use profiler-guided optimization when building, which results in a binary that is about 10% to 20% faster at executing the Python code, however this will increase the build time for about 20% to 40%.

It is safe to disable this flag.

### readline
This flag enables the `readline` Python module. This module influences how interactive input is handled by the Python interpreter and various built-in input related functions. Features include autocompletion and reading/writing of history files. Whe the flag is disabled, add the `MODULE_READLINE_STATE=disabled` to the `Makefile` to prevent this module from being installed.

It is safe to disable this flag. It is recommended to leave it enabled if there is a need to deal with the Python interpreter and scripts that provide interactive input.

### sqlite
The flag enables the `_sqlite3` and the dependent Python modules. The module provides an access to an SQLite database (version 3) that is often used by Python scripts for internal data storage. If the flag is disabled, add the `MODULE__SQLITE3_STATE=disabled` to the `Makefile` to avoid installing the module.

This flag is safe to disable. There is a number of packages in the Portage tree that are dependent on this flag.

### ssl
Python has an SSL support enabled by default. Disabling this flag will add the `MODULE__HASHLIB_STATE=disabled` and `MODULE__SSL_STATE=disabled` into the `Makefile` and force a build to disable an SSL support.

This flag should be enabled as it is required by the Portage to work properly.

### test
Skip some tests with known problems, by moving them out of the test directory. Execute the `make test` command after the main build is completed to run the test suite provided with the source code and check for regressions. Running tests will extend the build time.

This flag should normally be disabled, because these tests are primarily useful for the developers, testers and maintainers.

### tk
Enables the `_tkinter` and the dependent Python modules. This module provides an ability to render GUIs from Python scripts using the Tcl/Tk widget toolkit. When this flag is disabled, add the `MODULE__TKINTER_STATE=disabled` to the `Makefile` to prevent the module from being installed.

This flag can be safely disabled.

### valgrind
Pass the `--with-valgrind` option to the configure script. This would ensure that many false positive reports produced by running Python under the Valgrind profiler will be correctly supressed. It is also recommended to disable Python's custom memory allocator PyMalloc to catch even more memory leaks.

This flag should normally be disabled.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.
