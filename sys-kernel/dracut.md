# sys-kernel/dracut

### selinux
Pull necessary dependencies to run under a SELinux-restricted kernel, including the [sec-policy/selinux-dracut](../sec-policy/selinux-dracut.md) package that contains SELinux policies for Dracut. This is necessary for the proper operation of the `98selinux` Dracut module.

This flag should only ever be toggled system-wide, e.g. as part of the SELinux-enabled Portage profile.

### test
Execute the `make check` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend overall build time.

This flag should normally be disabled, as these tests are primarily useful for the maintainers, developers and testers.
