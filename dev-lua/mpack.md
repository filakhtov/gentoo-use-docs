# dev-lua/mpack

### test
For every active Lua implementation run the `busted --lua="<lua_interpreter>" test.lua` command after the main build is completed. Execute the test suite provided with the source code using the `busted` framework to check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.
