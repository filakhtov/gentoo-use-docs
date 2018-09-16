# media-libs/glew

### doc
Install additional documentation in the HTML format into the `/usr/share/doc/glew-<VERSION>/html` directory. Documentation contains information on how to build and use the library, and also external links to source code, issues, etc.

It is safe to disable the flag.

### static-libs
A statically linked version of the `libGLEW` library is built by default, so nothing is done if the flag is enabled. When disabled, patch the `Makefile` to prevent building it.

This flag should only be enabled if there is an explicit need for the static library.
