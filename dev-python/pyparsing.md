# dev-python/pyparsing

### examples
Install various example scripts into the `/usr/share/doc/pyparsing-<VERSION>/exmaples` directory. Examples include a wide range of different use cases, from simple "hello world" parsing to some very advanced use cases, such as parsing a chemical formula and calculate molecular weight or interactive linear algebra parser.

This flag can be safely disabled.

### test
Execute the `pytest` tool after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.
