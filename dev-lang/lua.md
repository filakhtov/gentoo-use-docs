# dev-lang/lua

### deprecated
Append the `-DLUA_COMPAT_5_3` option to the `CPPFLAGS` environment variable for the duration of the build. Enable support for deprecated routines and data structures, such as `lua_pushunsigned`, `lua_tounsigned`, `__le` metamethod emulation, `lua_strlen`, `lua_objlen`, `lua_equal` and so forth.

It safe to disable the flag if there is no need to use any of the deprecated data structures.

### readline
Pass the `--with-readline` option to the `configure` script. Use the `libreadline` library to enable history and rich editing experience in the Lua REPL (Read-eval print loop) interpreter.

It is safe to disable this flag if there is no need to use interactive interpreter.
