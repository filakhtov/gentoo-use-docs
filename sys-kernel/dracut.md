# sys-kernel/dracut

### selinux
Pull necessary dependencies to run under a SELinux-restricted kernel, including the [sec-policy/selinux-dracut](../sec-policy/selinux-dracut.md) package that contains SELinux policies for Dracut. This is necessary for the proper operation of the `98selinux` Dracut module.

This flag should only ever be toggled system-wide, e.g. as part of the SELinux-enabled Portage profile.
