# dev-perl/Sub-Name

### suggested
Only works if the `test` flag is enabled. Pull in the [dev-perl/Devel-CheckBin](../dev-perl/Devel-CheckBin.md) package as a dependency to find the `perlcc` executable necessary to run a regression test case for the [CPAN RT#96893](https://rt.cpan.org/Public/Bug/Display.html?id=96893).

It is safe to disable the flag.

### test
Execute the `make test` command from the source directory after the main build is completed to run the regression test suite provided with the source code. This will extend the build time.

This flag should normally be disabled, because it is mainly useful for the Gentoo team, testers and developers.
