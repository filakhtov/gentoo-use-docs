# dev-python/lxml
### doc
Install additional documentation in TXT and HTML format into a `/usr/share/doc/lxml-<VERSION>/`.

This flag can be safely disabled.

### examples
Install code examples from a `samples` directory into a `/usr/share/doc/lxml-<VERSION>/examples/` directory.

It is safe to disable the flag.

### test
Execute a test suite provided with a source code after a build is complete. Additional dependencies required to run tests will be installed. This will extend build time.

This flag should normally be disabled as it is only useful for the Gentoo team, developers or testers.

### threads
The flag is actually never used.
