# sys-kernel/dracut

### debug
Pull the [dev-util/strace](../dev-util/strace.md) package as a dependency. When `strace` is installed dracut will automatically add it into the built initramfs file as part of the `03rescue` or `95debug` module.

This flag should be enabled if there is a need to debug Dracut images with strace during an early boot.

### selinux
Pull necessary dependencies to run under a SELinux-restricted kernel, including the [sec-policy/selinux-dracut](../sec-policy/selinux-dracut.md) package that contains SELinux policies for Dracut. This is necessary for the proper operation of the `98selinux` Dracut module.

This flag should only ever be toggled system-wide, e.g. as part of the SELinux-enabled Portage profile.
