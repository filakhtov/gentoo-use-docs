# sys-libs/tdb

### python
Does nothing when enabled, because Python bindings are enabled by default. If disabled, pass a `--disable-python` option to a WAF configure script. Build and install a `tdb` Python module that provides an ability to read from and write to TDB database files.

This flag should only be enabled if there is a need to access TDB databases from Python scripts.
