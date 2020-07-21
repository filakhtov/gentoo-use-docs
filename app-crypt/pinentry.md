# app-crypt/pinentry

### caps
Pass the `--with-libcap` option to the configure script. Use the `libcap` library to lock memory via `CAP_IPC_LOCK` capability instead of the default `mlock` syscall.

This flag should only be enabled on really old kernels or systems without `mlock` support.

### emacs
Pass the `--enable-pinentry-emacs` option to the configure script. Use the Emacs client to handle passphrase input via Emacs editor.

This option should be disabled as it has security issues, e.g. it can expose recently typed keystrokes and therefore entered passphrase.

### fltk
Pass the `--enable-pinentry-fltk` option to the configure script. Build and install the `pinentry-fltk` program that uses the FLTK (DescriptionFast Light ToolKit) to display a dialog for secure PIN or passphrase entry.

This flag can be safely disabled, unless there is a need to use FLTK pinentry dialog.

### gnome-keyring
Pass the `--enable-libsecret` and the `--enable-pinentry-gnome3` options to the configure script. Provide an ability to cache an entered passphrases in a GNOME keyring providing an appropriate checkbox in UI. Build and install the `pinentry-gnome3` program - a graphical, GTK3 based dialog to allow secure entry of PINs and passphrases.

This flag should be enabled if the target system runs the GNOME3 Desktop Environment or another GNOME3 based DE, e.g. Cinnamon.

### gtk
Pass the `--enable-pinentry-gtk2` option to the configure script. Build and install a `pinentry-gtk2` program - a graphical, GTK2 based dialog to allow secure entry of PINs and passphrases.

This flag should be enabled if the target system runs a GTK2 based Desktop Environment, e.g. Xfce.

### ncurses
Pass the `--enable-pinentry-curses` and the `--enable-fallback-curses` options to the configure script. Use the `ncurses` library to display a text console based dialog for secure entry of PINs and passphrases. Fallback to this method if an X server is not available or there are no any supported graphical dialogs.

It is safe to disable the flag. It can be enabled together with other graphical dialogs to provide a reasonable console fallback.

### qt5
Pass the `--enable-pinentry-qt` option to the configure script. Build and install the `pinentry-qt` program - a graphical, QT-based dialog to allow secure entry of PINs and passphrases.

This flag should be enabled if the target system runs a KDE based Desktop Environment.

### static
Append the `-static` option to the `LDFLAGS` variable for the duration of a build. Build and install statically linked pinentry binaries.

This flag should only ever be enabled if there is a need for the static binaries.
