# net-misc/radvd

### selinux
Pull in the [sec-policy/selinux-radvd](../sec-policy/selinux-radvd.md) package as a dependency which provides SELinux policies for `radvd` daemon to properly run under the SELinux-enabled kernels.

This flag should only be ever toggled system-wide, using the appropriate Portage profiles.

### test
Pass the `--with-check` option to the configure script. Execute the `make check` command when the main build is completed to run the regression suite provided with the source code using the check - a C unit testing framework. This will extend the build time.

This flag should normally be disabled, as these test are primarily oriented towards developers, testers and maintainers.
