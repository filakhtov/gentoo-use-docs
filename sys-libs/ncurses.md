# sys-libs/ncurses

### ada
Enables `--with-ada` configure option. This will instruct make to build and install bindings and expample program for Ada95 programming language.

It is not usual to find a program written in Ada in general, let alone the one that is using ncurses, so for the average user it is safe to disable this flag.

### cxx
Enables `--with-cxx` and `--with-cxx-binding` configure options.

`--with-cxx` is a historical artifact. For in-depth details see `curses.h.in` source file of ncurses. In short, this header declares `bool` data type, because X/Open and SVr4 did that decision long-long ago and it is still around to preserve compatibility and interoperability.

This however, posesses a problem when C++ compiler is used to build ncurses library, because C++ defines its own data type for `bool`. Enabling `--with-cxx` will disable `bool` declaration in final `curses.h` and built-in `bool` data type will be used instead.

`--with-cxx-binding` option enables compilation of C++ ncurses binding and associated example program. These bindings provide a number of classes that simplify writing ncurses-based programs in C++. There is a wide variety of C++ tools that depend on these classes.

It is recommended to keep this flag enabled.

### debug
Enables `--with-debug` configure option. This will build a set of ncurses libraries that include debugging symbols. These libraries are usually prefixed with `_g`, e.g. `libncurses_g.a` or `libpanel_g.a`.

This flag is normally not required, unless debugging/development to be done against ncurses.

### doc
This flag simply instructs ebuild to install a copy of HTML documentation that comes with ncurses into subdirectory of `/usr/share/doc`. Minimum amount of documentation (e.g. README, intro, TO-DO) is still installed if this flag is disabled.

It is safe to disable this flag, unless development against ncurses library to be done and documentation is required to assist in doing so.

### gpm
This flag enables `--with-gpm` configure option. GPM stands for **G**eneral **P**urpose **M**ouse and is a daemon that provides mouse support for virtual consoles. Normally GPM enables just copy-paste behavior, but ncurses can use it for navigating menus, selecting options and so on.

This flag is recommended for users who plan to use mouse in their virtual consoles (command line, not usual Graphical Interface).

### minimal
This flag will instruct ebuild to exclude contents of `/usr/share/terminfo` from installation into the target system. This directory contains a database of terminal capabilities, that provides information on what escape sequences and control characters to send to terminal in order to move cursor, erase part of the screen, scroll, change mode, color, blinking, etc.

It is generally safe to enable this flag and thus remove `terminfo` directory, because ncurses comes with minimal database installed into `/etc/terminfo` and unless it is planned to use terminal that is not a regular screen it should have no effect whatsoever.

### profile
Enables `--with-profile` configure option. This is similar to `debug` flag and will build profiled libraries with `_p` prefix, e.g. `libncurses_p.a`. These libraries are built with `-pg` flag in order to enable collection of profiling information during runtime.

This flag has performance and size overhead and unless profiling of the ncurses library itself or applications dependent on it is planned this USE flag should be disabled.

### static-libs
This flag will instruct ebuild to preserve statically linked libraries. Normally, these libraries are removed by ebuild.

This is not an option that is normally needed by regular user and is mostly oriented for development purposes.

### test
This USE flag tells configure to enable `--with-tests` option and execute regression test suite that comes together with ncurses during build phase.

This will take extra build time and output is not something that is easily understood or can be act upon by regular user, so this flag should be normally disabled.

### threads
Enables `--with-pthread` configure option and `ncursest` Makefile target. This will build thread-safe version of the curses library. Thread implementation is based on pthread (POSIX threads). This flag should be enabled if library to be used to compile threaded applications. There are no packages in portage tree that explicitly require threaded ncurses, so it can be safely disabled by most users.

This flag can be combined with `unicode` and this will produce `ncursestw` library - wide, threaded variant.

### tinfo
This flag enables `--with-termlib` flag and instructs build to produce separate low-level `tinfo` library that is otherwise embedded into ncurses library. This flag can be safely disabled unless you explicitly require `tinfo` library or install one of the portage packages that require it as a dependency (e.g. [nvidia-cuda-toolkit](../dev-util/nvidia-cuda-toolkit), [android-ndk](../dev-util/android-ndk), [android-studio](../dev-util/android-studio), etc).

This flag can be combined with `unicode` and this will produce `tinfow` library with "wide" character set support.

### trace
This will enable `trace` configure option. This will add `-DTRACE` option to `CFLAGS` and add `trace()` function to all models of ncurses. Enabling trace will make your application creating trace files during runtime.

Normally tracing information is included only in debug libraries, however it is sometimes desirable to include tracing information into normal shared library. Enable this flag to achieve that.

This flag should normally be disabled.

### unicode
This flag enables `ncursesw` Makefile target. W in `ncursesw` stands for "wide" and resulting library will be able to handle Unicode character sets.

Normally users want to keep this flag enabled, because popular programs like `less`, `more` and `dmesg` will happily use "wide" version of ncurses! However it can be disabled if the target system is only ever dealing with English language.
