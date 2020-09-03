# app-shells/bash-completion

### eselect
Apply the patch to enable selective completion blacklisting support for Bash. Install an eselect module that provides an ability to enable and disable Bash completions using the aforementioned blacklist feature.

This flag should normally be disabled, unless there is a desire to selectively disable completion scripts.

### test
Execute the `make check` command after the main build is completed to run the test suite provided with the source code and check for any regression. This will extend the build time.

This flag should normally be disabled. It is mainly useful for the maintainers, testers and developers.
