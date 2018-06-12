# dev-lang/python
### berkdb
The flag enables the `dbm`, the `_bsddb` and the dependent Python modules. The `dbm` module is linked against Oracle Berkeley DB implementation.

It is not recommended to enable the flag, because the `bsddb` modules are deprecated and no longer maintained inside of the `python` package. Up to date alternative is provided by the [dev-python/bsddb3](../dev-python/bsddb3.md) package.

### build
This flag is used by the Gentoo team for building early stage images and bootstrapping. This will ignore the [app-misc/mime-types](../app-misc/mime-types.md) package dependency.

The flag should normally be disabled.

### doc
The flag will install the Python documentation by pulling in a relevant version of the [dev-python/python-docs](../dev-python/python-docs.md) package as a dependency.

This flag can be safely disabled and is only necessary for developers who plan to develop in Python and require documentation.

### examples
Enabling this flag will install example Python code that comes together with the source code into `/usr/share/doc/python-<VERSION>/examples`.

This flag can be safely disabled. It is only necessary for developers who require exmaple files in order to learn Python.

### gdbm
The flag enables the `dbm`, the `gdbm` and the dependent Python modules. The `dbm` module is linked against the GNU dbm (aka GDBM) implementation.

It is safe to disable this flag.

### hardened
This flag replaces the `-O3` compiler optimization option with the `-O2`. The higher level of an optimization is conflicting with the stack protection features of the compiler (i.e. `-fstack-protector`, `-fstack-protector-all` or `-fstack-protector-strong` options) and results in random Python crashes.

It is recommended to enable this flag on systems that have the `-O3` optimization option set in the `CFLAGS` and/or the `CXXFLAGS`. See the [Gentoo bug #50309](https://bugs.gentoo.org/50309) for more information.

### ipv6
Passes the `--enable-ipv6` option to the configure script. This will enable IPv6 protocol support in the Python networking code.

The flag should only be enabled on systems that participate in IPv6-capable networks.

### libressl
The flag changes the SSL backend library used by the Python from the OpenSSL to the LibreSSL. This flag does nothing if the `ssl` flag is disabled.

This flag must only ever be set system-wide, because it is impossible to have both the OpenSSL and the LibreSSL installed on the same system.

### ncurses
Enables the `_curses`, the `_curses_panel` and the dependent Python modules. These modules provide an interface for portable advanced terminal handling using the `ncurses` library. They also provide window management like functionality in a terminal.

This flag is generally safe to disable. There are quite a few packages in the Portage tree that depend on it however.

### readline
This flag enables the `readline` Python module. This module influences how interactive input is handled by the Python interpreter and various built-in input related functions. Features include autocompletion and reading/writing of history files.

It is safe to disable this flag. It is recommended to leave it enabled if there is a need to deal with the Python interpreter and scripts that provide interactive input.

### sqlite
The flag enables the `_sqlite3` and the dependent Python modules. The module provides an access to an SQLite database (version 3) that is often used by Python scripts for internal data storage.

This flag is safe to disable. There is a number of packages in the Portage tree that are dependent on this flag.

### ssl
Python has an SSL support enabled by default. Disabling this flag will export the `PYTHON_DISABLE_SSL` environment variable and force a build to disable an SSL support.

This flag should be enabled as it is required by the Portage to work properly.

### test
This flag executes a test suite provided with sources after the build is completed. Running tests will extend build time.

This flag should normally be disabled.

### threads
Passes the `--with-threads` option to the configure script. It will provide a set of modules, e.g. `threading` and `multiprocessing` for the thread-based parallelism and the processes management support.

This flag should be enabled. It is forced by the base Gentoo Portage profile anyway.

### tk
Enables the `_tkinter` and the dependent Python modules. This module provides an ability to render GUIs from Python scripts using the Tcl/Tk widget toolkit.

This flag can be safely disabled.

### wide-unicode
The flag passes the `--enable-unicode=ucs4` option to the configure script. This changes internal Unicode handling from using UTF16 to UTF32 and thus supporting wider character set.

This flag is enforced by the base Gentoo Portage profile, because changing it breaks an ABI compatibility. This flag should be enabled.

### wininst
Enabling the flag will install a set of Windows binaries (`wininst-*.exe`) that are necessary to build self-extracting installers for Windows machines using, for example `python setup.py bdist_wininst`.

This flag can be safely disabled unless aforementioned behavior is required.

### xml
Enables the `_elementtree`, the `pyexpat` and the dependent Python modules. This provides an ability to handle XML files from Python scripts.

The flag is safe to disable, however there is a fair amount of packages in the Portage tree that depend on it.
