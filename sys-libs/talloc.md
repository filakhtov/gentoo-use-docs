# sys-libs/talloc

### compat
Pass a `--enable-talloc-compat1` option to a WAF configure script. Build and install a version 1 of a `libtalloc` library that provides compatibility layer with older (1.x.x) API version of talloc library.

This flag should only be enabled if there is a need to run legacy applications that use a talloc v1 API.

### python
Prepare Python environment for building a module. When disabled, pass a `--disable-python` option to a WAF configure script. Build and install a `pytalloc` Python module that provides bindings for a `libtalloc` library.

This flag should only be enabled if there is a need to run Python scripts that use the module.

### valgrind
Pull in [dev-util/valgrind](../dev-util/valgrind.md) package as a dependency. It is a build-time only automagic dependency, i.e. will be only activated is Valgrind profiler is installed at a build time. Enable additional code to support running under the Valgrind profile without reporting false positives.

This flag should normally be disabled.
