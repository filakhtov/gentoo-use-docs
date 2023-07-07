# dev-python/jaraco-text

### cli
Install additional dependencies that are required for running the CLI scripts: `strip-prefix.py` and `show-newlines.py`.

It is safe to disable this flag.

### test
Execute the `python -m unittest` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.
