# sys-devel/gettext

### acl
This flag passes `--enable-acl` option to the configure script. Various Gettext tools gain an ability to preserve ACL permissions while manipulating files.

This flag can be disabled if there is no need to deal with ACL permissions on translation files.

### cxx
Passes the `--enable-c++` option that provides C++ support and the `--enable-libasprintf` option that provides the `autosprintf` function to the configure script.

It is safe to disable this flag, unless there is a need to run or develop C++ applications with Gettext support or ones that depend on the `autosprintf` function.

### doc
Produces and installs HTML docs into the `/usr/share/doc/gettext-<VERSION>/` directory. Generates a `javadoc2` documentation if the `java` flag is also enabled.

This flag can be safely disabled unless extended documentation is necessary.

### emacs
Pulls [app-emacs/po-mode](../app-emacs/po-mode.md) package as a dependency. This provides an ability to edit Gettext `.po` files in Emacs editor.

This flag can be safely disabled. It can only be useful if there is a need to edit translation files using GNU Emacs editor.

### git
Passes the `--with-git` option to the configure script. This will use a GIT compression in the `autopoint` tool for infrastructure archive compression.

This flag is safe to disable as a build will fallback to other archive formats, e.g. xz or bzip2.

### java
The flag passes the `--enable-java` option to the configure script. This will provide runtime Java libraries `libintl.jar` and `gettext.jar`.

This flag can be safely disabled, unless there is a need to run or develop Java applications with Gettext support.

### ncurses
Passes the `--enable-curses` option to the configure script. Uses the terminfo and the termcap from the ncurses library for various tools to manipulate a terminal output.

It is safe to disable the flag if there is no need to use gettext tools directly.

### nls
This flag passes the `--enable-nls` option to the configure script. Enables translation of messages and prompts produced by various gettext tools. If disabled, `/usr/share/locale` directory will not be installed.

The flag can be disabled if there is no need for a gettext tools localization.

### openmp
The flag passes the `--enable-openmp` option to the configure script. Enables OpenMP support in `msmerge` tool to parallelize merging process across different threads.

This flag can be safely disabled. It is only necessary for developers or people who work with translation files.

### static-libs
Passes the `--enable-static` option to the configure script. This will produce statically linked tools and libraries. If disabled, all libtool files `*.la` and static libraries `*.a` will are removed before installation.

This flag should normally be disabled unless there is an explicit need for statically linked libraries.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.

### xattr
Pass the `--enable-attr` option to the configure script. Link against the `libattr` library to enable support for extended file attributes on files generated with gettext.

This flag should be toggled system-wide, otherwise there is a high chanse of losing the exented attributes when processing files with vasious tools.
