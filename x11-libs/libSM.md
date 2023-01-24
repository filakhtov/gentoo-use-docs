# x11-libs/libSM

### doc
Pass the `--enable-docs` and the `--with-xmlto` options to the configure script. Generate and install additional documentation into a `/usr/share/doc/libSM-<VERSION>` directory.

This flag can be safely disabled.

### uuid
Pass the `--with-libuuid` option to the configure script. When disabled, export an `ac_cv_func_uuid_create=no` variable for the configure script. Use a `UUID` to generate a globally unique client ID instead of using a `gethostbyname()` call that might result in DNS timeout and failure.

This flag should be enabled if there is a need to connect from the remote network clients. It is safe to disable otherwise.
