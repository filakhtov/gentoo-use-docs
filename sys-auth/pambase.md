# sys-auth/pambase

### caps
Pass the `--caps` option to the `pambase.py` build script. Add the `pam_cap` module as an `optional` component into the `auth` interface for `system-auth` stack.

This flag can be safely disabled, unless there is a need to set the inheritable capabilities for users based on the `/etc/security/capability.conf` configuration file.

### debug
Pass the `--debug` option to the `pambase.py` build script. Append `debug` argument to various PAM modules (e.g. `pam_access`, `pam_env`, `pam_unix`, etc) that support it allowing them to display debugging information as they are processed.

This flag is useful for debugging issues with PAM. It should normally be disabled.

### elogind
Can't be used together with the `systemd` flag. Pass the `--elogind` option to the `pambase.py` build script. Add a `pam_elogind` module as an `optional` into a `session` interface for `system-auth` stack.

This flag should be enabled if there is a need for a SystemD logind manager without a SystemD itself, e.g. for running GNOME with OpenRC. It should be disabled in all other cases.

### gnome-keyring
Pass the `--gnome-keyring` option to the `pambase.py` build script. Add a `pam_gnome_keyring` module as an `optional` into an `auth`, a `password` and a `session` interfaces for a `system-login` stack.

This flag should be enabled if there is a desire to use a GNOME Keyring and automatically unlock it at log-in. Otherwise this flag can be safely disabled.

### homed
Pass the `--homed` option to the `pambase.py` build script. Add the `pam_systemd_home` module into the `auth` interface of the `system-auth` stack and into the `session` interface of the `system-session` stack.

This flag should only be enabled for system that use the `systemd-homed` service for managing human user accounts.

### minimal
Pass the `--minimal` option to the `pambase.py` build script. Disable non-essential PAM modules: `pam_motd`, `pam_mail`, `pam_lastlog`, `pam_tally` (or `pam_tally2`) from the `system-login` stack.

It is safe to enable this flag and skip aforementioned modules, but some of them add nice additional security measures, mainly `pam_tally` to count failed logins and deny further attempts and `pam_lastlog` to display last successful login info.

### mktemp
Pass the `--mktemp` option to the `pambase.py` build script. Add the `pam_mktemp` module as an `optional` to a `session` interface of a `system-auth` and a `system-services` stacks.

This flag can be safely disabled, however it is a nice additional security feature that provides every user with their own, private `/tmp` space.

### nullok
Pass the `--nullok` option to the `pambase.py` build script. Append a `nullok` argument to a `pam_unix` module for an `auth` and a `password` interfaces of a `system-auth` stack.

This flag should be enabled if there is a need for auto-login functionality, e.g. with a display manager. Otherwise it is recommended to disable this flag to improve security.

### pam_krb5
Pass the `--krb5` option to the `pambase.py` build script. Add the `pam_krb5` module to an `auth`, an `account`, a `password` and a `session` interfaces of the `system-auth` stack and to a `session` interface of the `system-session` stack using an extended Linux-PAM syntax so that Kerberos authentication is performed first falling back to local `pam_unix` if failed.

This flag should only be enabled if there is a need to use Kerberos user authentication. It should be disabled otherwise.

### pam_ssh
Pass the `--pam-ssh` option to the `pambase.py` build script. Add the `pam_ssh` module to an `auth` interface as a `sufficient` and `session` interface as an `optional` for the `system-auth` stack.

This flag is necessary if there is a need to verify user identity by asking for an SSH passphrase for one of the user's private keys. This flag should normally be disabled.

### passwdqc
Can't be used together with `pwquality` flag. Pass the `--passwdqc` option to the `pambase.py` build script. Add the `pam_passwdqc` module as a `required` component of a `password` interface for the `system-auth` stack.

This flag should be enabled if there is a desire to use a `libpasswdqc` library. Otherwise it should be disabled.

### pwhistory
Pass the `--pwhistory` option to the `pambase.py` build script. Add the `pam_pwhistory` module as a `required` component of the `password` interface of the `system-auth` stack. This module saves the last passwords for each user in order to force password change history and keep the user from alternating between the same password too frequently.

It is safe to disable this flag, but should be considered by security-conscious users.

### pwquality
Pass the `--pwquality` option to the `pambase.py` build script. Add the `pam_pwquality` module as a `required` component of the `password` interface of the `system-auth` stack. This module provides password strength-checking against a set of rules and dictionaries of commonly used passwords.

This flag can be safely disabled, but should be considered by security-conscious users.

### securetty
Pass the `--securetty` option to the `pambase.py` build script. Add a `pam_securetty` module as a `required` component of an `auth` interface for the `login` stack.

This flag should be enabled if it is necessary to restrict root login to certain terminals. It should be disabled otherwise.

### selinux
Pass the `--selinux` option to `pambase.py` build script. Add a `pam_selinux` module as a `required` component of a `session` interface with different arguments for the `system-login` stack.

This flag should only ever be toggled system-wide, e.g. as part of a SELinux enabled Portage profile as it has a lot of implications.

### sha512
Pass the `--sha512` option to `pambase.py` build script. Replace a `md5` option with a `sha512` option for a `pam_unix` module that is used in `password` interface of a `system-auth` stack.

It is recommended to enable this flag to improve hashing algorithm.

### systemd
Pass the `--systemd` option to `pambase.py` build script. Add a `pam_systemd` module as an `optional` component of a `session` interface of a system-auth stack.

This flag should be toggled system-wide, e.g. as part of a SystemD-enabled Portage profile.

### yescrypt
Pass the `--yescrypt` option to the `pambase.py` build script. Switch `pam_unix` module to use yescrypt KDF (password-based key derivation function) for storing passwords instead of MD5.

It is recommended to enable this flag to improve password storage encryption, but can cause compatibility issues with older systems.
