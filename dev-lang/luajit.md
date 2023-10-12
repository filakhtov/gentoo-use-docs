# dev-lang/luajit

### lua52compat
Pass the `XCFLAGS=-DLUAJIT_ENABLE_LUA52COMPAT` option to the make command. Enable some of the Lua 5.2 features that are supported by the LuaJIT, but are incompatible with Lua 5.1 (such as `__pairs` or `os.execute()` return values). This does not provide a full Lua 5.2 compatibility.

This flag should normally be disabled, as it enables breaking changes and can cause unexpected issues.

### static-libs
Pass the `BUILDMODE=mixed` (instead of `dynamic`) to the make command. Build and install a statically linked version of the `libluajit-5.1` library.

This flag should only ever be enabled if there is a need for the static library.
