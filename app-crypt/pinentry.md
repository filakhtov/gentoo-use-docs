# app-crypt/pinentry

### caps
Pass the `--with-libcap` option to the configure script. Use the `libcap` library to lock memory via `CAP_IPC_LOCK` capability instead of the default `mlock` syscall.

This flag should only be enabled on really old kernels or systems without `mlock` support.

### efl
Pass the `--enable-pinentry-efl` option to the configure script. Build and install the `pinentry-efl` binary - an Enlightenment Foundation Libraries-based graphical dialog for secure passphrase and PIN entry.

This flag should only be enabled if the system to be running the Enlightenment desktop environment.

### emacs
Pass the `--enable-pinentry-emacs` option to the configure script. Use the Emacs client to handle passphrase input via Emacs editor.

This option should be disabled as it has security issues, e.g. it can expose recently typed keystrokes and therefore entered passphrase.

### gtk
Pass the `--enable-pinentry-gnome3` option to the configure script. Build and install the `pinentry-gnome3` program - a graphical, GTK3 based dialog to allow secure entry of PINs and passphrases.

This flag should be enabled if the target system runs a GTK2 based Desktop Environment, e.g. Xfce.

### keyring
Pass the `--enable-libsecret` option to the configure script. Provide an ability to cache an entered passphrases in a GNOME keyring providing an appropriate checkbox in UI.

This flag should be enabled if the target system runs the GNOME3 Desktop Environment or another GNOME3 based DE, e.g. Cinnamon.

### ncurses
Pass the `--enable-pinentry-curses` and the `--enable-fallback-curses` options to the configure script. Use the `ncurses` library to display a text console based dialog for secure entry of PINs and passphrases. Fallback to this method if an X server is not available or there are no any supported graphical dialogs.

It is safe to disable the flag. It can be enabled together with other graphical dialogs to provide a reasonable console fallback.

### qt5
Pass the `--enable-pinentry-qt` option to the configure script. Build and install the `pinentry-qt` program - a graphical, QT-based dialog to allow secure entry of PINs and passphrases.

This flag should be enabled if the target system runs a KDE based Desktop Environment.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.

### wayland
Pass the `--enable-wayland` option to the configure script. Enable support for native Qt password prompting dialog under Wayland.

This flag should only be enabled if the target system uses Qt on top of Wayland.

### X
Pass the `--with-x` and `--enable-qtx11extras` options to the configure script. Enable support for native Qt passphrase prompting dialog under the X11 server.

This flag should only be enabled if the target system uses Qt on top of X11 server.
