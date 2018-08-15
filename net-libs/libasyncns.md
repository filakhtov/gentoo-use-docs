# net-libs/libasyncns

### debug
Debug mode is enabled by default, so enabling this flag does nothing. When disabled, append the `-DNDEBUG` option to the `CPPFLAGS` environment variable for the duration of a build and therefore disable runtime assertions.

This flag should only be enabled if there is a need to debug the library itself or an application linked against it.

### doc
Execute the `doxygen` command using the config provided with the source code to generate an API documentation in an HTML format out of sources and annotations and install it into the `/usr/share/doc/libasyncns-<VERSION>/apidocs` directory.

It is safe to disable the flag.
