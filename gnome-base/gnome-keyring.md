# gnome-base/gnome-keyring

### pam
Pass the `--enable-pam` and the `--with-pam-dir=` (with the value of the PAM modules directory location) to the configure script. Build and install the `pam_gnome_keyring` PAM module that provides an ability to automatically unlock Gnome Keyring at login.

It is safe to disable the flag.

### selinux
Pass the `--enable-selinux` option to the configure script. Provide an ability to properly run under a SELinux-restricted kernel. Set process context during an initialization.

This flag should only ever be toggled system-wide, e.g. as part of the SELinux-enabled Portage profile.

### ssh-agent
Pass the `--enable-ssh-agent` option to the configure script. Build and install an SSH Agent that integrates with the Gnome Keyring to provide stored passphrases for SSH keys and allow using the PKCS#11 private key store.

It is safe to disable the flag, however SSH key management abilities of the Gnome keyring will be lost.

### test
Prepare a Python environment to properly run tests. Compile GSettings XML schemas necessary for running test. Start a new Xvfb session and execute the `make check` command inside of it. Run a test suite provided with the source code. This will extend a build time.

This flag should normally be disabled. It is oriented to the Gentoo team, testers and developers.
