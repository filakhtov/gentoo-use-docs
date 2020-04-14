# app-text/enchant

### aspell
Pass the `--with-aspell` option to the configure script. Enable Aspell spell-checking backend that uses the `libaspell` library.

This flag should normally be disabled, even though Aspell is a bit more smarter with suggestions, but it is outdated and unmaintained.

### hunspell
Pass the `--with-hunspell` option to the configure script. Enable Hunspell (formerly Myspell) spell-checking backend that uses the `libhunspell` library.

This flag should normally be enabled, because Hunspell is widespread and well supported library.
