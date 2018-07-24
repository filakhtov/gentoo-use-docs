# app-shells/bash-completion

### test
Prepare log file for the live tailing during test execution. Run a `make check` command using interactive `bash` shell and pipe output into the log file. Write exit status into the log file once tests are completed. Check an exit status to determine if tests are successful. Execute a test suite provided with the bash completions after the main build is completed. This will extend a build time.

This flag should normally be disabled. It is mainly useful for the Gentoo team, testers and developers.
