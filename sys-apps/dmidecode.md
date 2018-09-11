# sys-apps/dmidecode

### selinux
Pull in the [sec-policy/selinux-dmidecode](../sec-policy/selinux-dmidecode.md) package as a dependency that provides SELinux policies necessary for the `dmidecode` tool to work properly under a SELinux-restricted kernel.

This flag should only ever be toggled system-wide, i.e. as part of the SELinux-enabled Portage profile.
