# sys-libs/talloc

### compat
Pass a `--enable-talloc-compat1` option to a WAF configure script. Build and install a version 1 of a `libtalloc` library that provides compatibility layer with older (1.x.x) API version of talloc library.

This flag should only be enabled if there is a need to run legacy applications that use a talloc v1 API.

### python
Prepare Python environment for building a module. When disabled, pass a `--disable-python` option to a WAF configure script. Build and install a `pytalloc` Python module that provides bindings for a `libtalloc` library.

This flag should only be enabled if there is a need to run Python scripts that use the module.
