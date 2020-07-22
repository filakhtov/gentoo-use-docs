# dev-python/testtools

### doc
Use the Sphinx tool to generate documentation in the HTML format and install it into the system. Documentation contains description of the `testtools`, why it is useful, how to write and run tests and so forth.

It is safe to disable this flag.

### test
Execute the `python -m unittest discover` command for each active Python implementation after the main build is completed to run the test suite provided with the source code and check for any regressions.

This flag should normally be disabled, because these tests are primarily used by the developers, maintainers and testers.
