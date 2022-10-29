# sys-devel/autoconf

### emacs
Pull a [app-emacs/autoconf-mode](../app-emacs/autoconf-mode.md) package as a dependency. This package contains an Emacs major mode for editing autoconf `ac` and `m4` files and provides basic syntax support.

This flag should be enabled if there is a need to use Emacs editor to modify autoconf files.

### test
Execute the `make check` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.
