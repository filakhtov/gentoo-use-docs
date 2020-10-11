# dev-python/jinja

### doc
Use the Sphinx tool to generate documentation in the HTML format and install it into the system. Documentation contains library installation instructions, package API reference, template designer documentation, how to use and create extensions, various integrations, tips and tricks, frequently asked questions and so forth.

It is safe to disable this flag.

### examples
Install additional example files that show how to use Jinja templates, including loops, filtering, conditions, translations and so forth.

This flag can be safely disabled.

### test
Run the `pytest` command after the main build is completed to execute the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily used by the maintainers, developers and testers.
