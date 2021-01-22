# app-misc/screen

### debug
Append the `-DDEBUG` option to the `CPPFLAGS` environment variable for the duration of the build. Produce additional debugging output at runtime. Redefine some macros to simplify running the screen under a debugger.

This flag should only be enabled if there is a need to debug the screen.

### multiuser
Set the `suid` bit, the `root` group on the `/usr/bin/screen` binary and set permissions to `0755` inside of the `tmpfiles.d` config instead of the default `sgid` bit with the `utmp` group and the `0775` mode. Enable the multiuser support for the screen tool.

This flag should be enabled if there is a need to share the screen session between different users, however this can lead to security issues.

### nethack
Nethack messages are enabled by default so this flag does nothing when enabled. When disabled, append the `-DNONETHACK` option to the `CPPFLAGS` environment variable for the duration of a bulid. Change the kind of error messages used by screen to resemble the `nethack` game messages from 1980s.

It is safe to disable the flag.

### pam
Pass the `--enable-pam` option to the configure script. Use the PAM (pluggable authentication module) infrastructure for authentication using the user's system password instead of asking for a locking password, encrypting it using `crypt`, storing in the memory and then manually comparing to the input provided when trying to unlock. Install PAM configuration file to provide this functionality.

It is recommended to enable the flag to benefit from a security improvement provided by the PAM.

### selinux
Pull in the [sec-policy/selinux-screen](../sec-policy/selinux-screen.md) package as a dependency. Install SELinux policies to allow sceen to properly run under SELinux-restricted kernel.

This flag should only ever be toggled system-wide, e.g. as part of a SELinux-enabled Portage profile.
