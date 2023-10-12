# dev-lua/lpeg

### debug
Append the `-DLPEG_DEBUG` option to the `CFLAGS` environment variable for the duration of the build. Enable runtime assertions and print additional debugging information at runtime.

This flag should only be enabled if there is a need to debug the lpeg library or scripts that use it.

### doc
Install additional documentation files: a plain text `HISTORY` file that contains the library changelog, and a few HTML files that contain information on how to use the library and some examples.

This flag should normally be disabled, because this documentation is inteded for the developers and not end users.

### test
Run the `lua test.lua` command for every enabled Lua implementation to run the test suite provided with the source code and check for regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.
