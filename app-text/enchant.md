# app-text/enchant

### aspell
Pass the `--with-aspell` option to the configure script. Enable Aspell spell-checking backend that uses the `libaspell` library.

This flag should normally be disabled, even though Aspell is a bit more smarter with suggestions, but it is outdated and unmaintained.

### hunspell
Pass the `--with-hunspell` option to the configure script. Enable Hunspell (formerly Myspell) spell-checking backend that uses the `libhunspell` library.

This flag should normally be enabled, because Hunspell is widespread and well supported library.

### nuspell
Pass the `--with-nuspell` option to the configure script. Enable Nuspell spell-checking backend - a fast and safe spelling checker designed for languages with rich morphology and complex word compounding which supports Hunspell dictionaries.

It is safe to disable this flag.

### test
Pass the `--enable-relocatable` option to the configure script. Execute the `make check` command after the main build is completed to run the test suite provided with the source code to check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily useful for the developers, maintainers and testers.

### voikko
Pass the `--with-voikko` option to the configure script. Build and install Voikko plugin for enchant - a morphological analyzer, spelling and grammar checker, hyphenator and collection of related linguistic data for Finnish language.

This flag should only be enabled if there is a need to deal with Finnish language.
