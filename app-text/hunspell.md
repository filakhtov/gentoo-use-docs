# app-text/hunspell

### ncurses
Pass the `--with-ui` option to the configure script. Build the curses-based user interface that provides an ability to interactively spell-check documents.

It is safe to disable the flag.

### nls
Pass the `--enable-nls` option to the configure script. Install translation files to provide an ability to translate programs messages and user interface (if available) into the different languages based on the system locale settings.

This flag should be enabled if there is a need to use tools in a non-English language.

### readline
Pass the `--with-readline` option to the configure script. Use the `libreadline` library to provide line editing capabilities, e.g. moving cursor back and forth when entering a replacement word, adding a new word to dictionary, etc.

It is safe to disable the flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libhunspell` library.

This flag should only be enabled if there is an explicit need for the static library.
