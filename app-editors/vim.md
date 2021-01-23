# app-editors/vim

### acl
Pass the `--enable-acl` option to the configure script. Enable an ability to manipulate ACL permissions, e.g. copy ACL permissions from an original file onto a backup or a new file.

It is recommended to toggle this flag system-wide to avoid losing ACL permissions. It is safe to disable it if the target system doesn't have to deal with ACLs.

### cscope
Pass the `--enable-cscope` option to the configure script. If disabled, manually patch a `feature.h` to provide a dummy `FEAT_CSCOPE` macro. Enable a Cscope support to help navigate to various symbols definitions in C/C++/Java source files.

It is safe to disable this flag.

### debug
Append a `-DDEBUG` option to a `CFLAGS`, a `CXXFLAGS`, a `FFLAGS`, a `FCFLAGS` variables. Preserve debugging information while building and linking a `vim`.

This flag should normally be disabled and is only required for debugging build.

### gpm
Pass the `--enable-gpm` option to the configure script. Enable mouse support in VIM to select (via visual mode), copy and paste text.

This flag can be safely disabled.

### lua
Pass the `--enable-luainterp` and the `--with-lua-prefix=${EPREFIX}/usr` options to the configure script. Enable Lua scripting interpreter support that can be used for `.vimrc` configuration files or plugins written in Lua language or via a `:lua`, a `:luado`, etc. commands in editor.

It is safe to disable this flag if there is no need for LUA scripting support.

### minimal
Change a value of the `--with-features` option from a `huge` to a `tiny`. Ignore all other flags and disable them by default. Build a very minimalistic `vim` version.

This flag should normally be disabled, otherwise a resulting VIM binary will be very limited, e.g. no syntax highlighting, GPM support, etc.

### nls
Pass the `--enable-nls` option to the configure script. Provide support for a `:menutrans`, a `:language`, etc. commands. Use locale settings to translate program messages, e.g. errors, help texts, etc. via gettext.

It is necessary to enable the flag if there is a need to use vim in non-English languages. Otherwise, it is safe to disable.

### perl
Pass the `--enable-perlinterp` option to the configure script. Enable a built-in Perl interpreter. Provide support for a `:perldo`, a `:perl`, etc. commands and plugins written in a Perl language. Enable scripting for VIM using a Perl programming language.

This flag should be enabled if there is a need for Perl interpreter. It is safe to disable it otherwise.

### python
Pass the `--enable-python3interp` and `--with-python3-command` options to the configure script. Enable Python 3 interpreter support. Provide a `:py` and a `:python` commands and enable support for a VIM scripting using a Python programming language.

This flag should be disabled unless there is a need for Python interpreter.

### racket
Pass the `--enable-mzschemeinterp` option to the configure script. Enable a Racket interpreter (formerly MzScheme). Provide support for an `:mz`, an `:mzscheme`, an `:mzfile` and an `:mzeval` commands. Enable support for a VIM scripting with a Scheme programming language.

This flag should be normally disabled unless there is a need for a Scheme interpreter.

### ruby
Pass the `--enable-rubyinterp` option to the configure script. Enable a built-in Ruby interpreter. Provide support for a `:ruby` and a `:rub` runtime commands. Enable an ability to script VIM using a Ruby programming language.

Normally this flag should be disabled. It is only neccessary if there is a need for Ruby interpreter.

### selinux
Pass the `--enable-selinux` option to the configure script. Enable support for running under SELinux restrictions. E.g. copy a file context onto a swap file when creating it or copy a security context if creating a backup file or saving a modified file unders a different name or creating an undo file.

This flag should only ever be toggled system-wide, e.g. as part of a SELinux-enabled Portage profile as it has too many implications.

### sound
Pass the `--enable-canberra` option to the configure script. Use the `libcanberra` library to provide an ability to play custom sounds when an action is impossible or task is complete.

It is safe to disable this flag.

### tcl
Pass the `--enable-tclinterp` option to the configure script. Enable a built-in Tcl language interpreter. Provide a `:tc` and a `:tcl` runtime commands. Support VIM scripting using a Tcl scripting language.

This flag should usually be disabled unless there is an explicit need for a Tcl interpreter.

### terminal
Pass the `--enable-terminal` option to the configure script. Provide a `:terminal` and a `:term` runtime commands to run a terminal emulator inside of a VIM window.

This flag can be safely disabled unless there is a need to use terminal emulator capabilities of a VIM editor.

### vim-pager
Create `manpager.sh` script that uses VIM as a pager for viewing MAN pages. Create a `vimpager`, and a `vimmanpager` symlinks.

It is safe to disable this flag.

### X
Pass the `--with-x` option to the configure script. Enable an X11 support. Provide an ability to manipulate an X11 terminal window title and set an application icon, support for font management, integrate with clipboard, etc.

It is recommended to enable this flag if the target system to be ran with Graphical Desktop Environment. It is safe to disable otherwise.
