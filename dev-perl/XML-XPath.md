# dev-perl/XML-XPath

### examples
Install an additional `xpath` Perl script that provides an example on how to utilize the module and allows to make XPath queries to any XML document.

This flag should normally be disabled, unless an example is required or there is a need to use the `xpath` script itself.

### test
Remove tests that perform XPath matching on JSON and YAML files. Execute the `make test` command when the main build is completed to run the regression suite provided with the source code to check for any regressions. This will extend the overall build time.

This flag should normally be disabled as it makes the build slower and the tests that are executed primarily oriented towards the package maintainers, developers and testers.
