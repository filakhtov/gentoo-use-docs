# sys-apps/dtc

### static-libs
A statically linked version of the `libfdt` library is built and installed by default, so this flag does nothing when enabled. If disabled, the library will be removed before installation.

This flag should only be enabled if there is an explicit need for the static library.

### yaml
Use the `libyaml` library to enable support for device tree encoded in YAML format. When this flag is disabled, pass the `NO_YAML=1` variable to the `make` build command to disable it.

It is safe to disable this flag.
