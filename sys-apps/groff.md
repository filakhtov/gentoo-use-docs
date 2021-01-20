# sys-apps/groff

### examples
Install a variety of different example files into a `/usr/share/doc/groff-<VERSION>/examples` directory. Exmaples include some usages of formulas, various input and output formats, etc.

This flag should normally be disabled.

### uchardet
Pass the `--with-uchardet` option to the configure script. Link the `preconv` binary against the `libuchardet` library to allow automatic encoding detection of the input files.

This flag can be safely disabled if there is no need to process input files that contain code points outside of 0-127 range (in US-ASCII, ISO 8859, or Unicode).

### X
Pass the `--with-x` option to the configure script. Build and install a `gxditview` tool for displaying an intermediate output files and an `xtotroff` tool to convert X font metrics into GNU troff ones.

It is safe to disable this flag.
