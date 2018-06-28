# dev-python/pyxattr
### doc
Execute a `make doc` to build HTML documentation and install it into a `/usr/share/doc/pyxattr-<VERSION>/html` directory. Pull in a [dev-python/sphinx](sphinx.md) package for generating docs.

It is safe to disable this flag unless package documentation is needed.

### test
Execute a test suite provided with a source code during a build. Pull in a [dev-python/nose](nose.md) package necessary for executing tests. This will extend a build time.

This flag should normally disabled as it is mostly useful for the Gentoo team, developers or testers.
