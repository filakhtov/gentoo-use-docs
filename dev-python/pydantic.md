# dev-python/pydantic

### native-extensions
Pull in the [dev-python/cython](../dev-python/cython.md) dependency and use it to build extensions for native C modules.

This flag should be enabled if there is a need to use Pydantic with the native Python modules.

### test
Execute the `pytest` tool after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.
