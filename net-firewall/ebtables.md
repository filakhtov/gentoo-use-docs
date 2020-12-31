# net-firewall/ebtables

### perl
By default, the `ebtables-legacy-save` Perl script is installed by this package, so nothing will happen when this flag is enabled. If disabled, the ebuild script will modify the `Makefile` file to remove the `sbin_SCRIPTS` variable and prevent the aforementioned script from being installed.

It is safe to disable this flag.

### static
Pass the `--enable-static` option to the configure script. Run the `make static ebtables-legacy.8` command, instead of just `make`, to compile only the statically linked version of the `ebtables` binary and its man page, and install them into the system. Init scripts, `ebtablesd`, `ebtablesu` and other binaries and scripts also won't be installed.

This flag should normally be disabled, as it is only useful in rare embedded scenarios.
