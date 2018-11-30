# media-libs/fdk-aac

### examples
Pass the `--enable-example` option to the configure script. Build and install the `aac-enc` example tool - a very basic command-line interface encoding utility, that can encode to AAC from the WAV format. Note: it is installed under the `fdk-aac-enc` name to avoid naming collisions with other packages.

It is safe to disable the flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libfdk-aac` library.

This flag should only be enabled if there is an explicit need for the static library.
