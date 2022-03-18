# app-crypt/gnupg

### bzip2
Pass the `--enable-bzip2` option to the configure script. Provide support for the BZip2 compression format. Support the `bzip2` value for the `--compress-algo` runtime option.

This flag can be safely disabled.

### doc
Execute the `make html` command inside of the `doc` directory in a source tree. Generate and install additional documentation in the HTML format.

It is safe to disable the flag.

### ldap
Pass the `--with-ldap` option to the configure script. Provide an ability to send and receive keys from a LDAP keyserver. Enable the `ldap://` protocol support for the `--keyserver` runtime option and the `keyserver` configuration option.

This flag should only be enabled if there is a need to interact with LDAP keyservers.

### nls
Pass the `--enable-nls` option to the configure script. Use the Gettext library to translate programs messages and an output of libraries into various languages based on system local settings.

This flag should be enabled if there is a need to use any non-English languages.

### readline
Pass the `--with-readline` option to the configure script. Use the `libreadline` library to provide line editing, command completion and history capabilities for various tools. Examples include filename completion for various prompts and command completion for `--edit-key` and `--card-edit` menus.

It is safe to disable the flag.

### selinux
Pull the [sec-policy/selinux-gpg](../sec-policy/selinux-gpg.md) package as a dependency. Installed package provides necessary SELinux policies for GnuPG to properly operate under SELinux-restricted kernel.

This flag should only ever be toggled system-wide, e.g. as part of the SELinux-enabled Portage profile.

### smartcard
Pass the `--enable-scdaemon` option to the configure script. Build and install the `scdaemon` binary - a daemon for managing smartcards.

This flag should only be enabled if there is a need to use smartcards.

### ssl
Pass the `--enable-gnutls` option to the configure script. Provide support for an HTTP and a HKP protocols over TLS using the `GnuTLS` communication library.

The flag must be enabled if there is a need to send and receive keys over TLS encrypted connections.

### tofu
Pass the `--enable-tofu` option to the configure script. Enable a TOFU (Trust on First Use) trust model. GnuPG will try to look up the identifier in its local trust database. If no identifier exists yet for the endpoint it will prompt the user to determine if the client should trust the identifier and record the trust relationship into its trust database.

It is safe to disable this flag.

### tools
Install additional tools:

- `convert-from-106` - converts public keyring and trustdb from GnuPG 1.0.6 to later formats
- `gpg-check-pattern` - check a passphrase on stdin against the patternfile
- `gpg-zip` - encrypts or signs files into an archive
- `gpgconf` - a utility to automatically and reasonably safely query and modify configuration files in the `.gnupg` home directory
- `gpgsplit` - split an OpenPGP message into packets
- `lspgpot` - extracts  the  ownertrust  values  from  PGP  keyrings  and list them in GnuPG ownertrust format
- `mail-signed-keys` - sign a key, publish to keyserver and notify key owner over an email
- `make-dns-cert` - generate DNS entries for publishing PGP keys in DNS

The flag can be safely disabled.

### usb
Only works if the `smartcard` flag is enabled. Pass the `--enable-ccid-driver` option to the configure script. Build and install the `libccid` library - a CCID (Chip Card Interface Description) driver that directly communicates with the cardreader using the `libusb` library.

This flag should be enabled if there is a need to use CCID/ICCD cards.

### user-socket
Pass the `--enable-run-gnupg-user-socket` option to the configure script. This option allows gpg-agent to use the `/run/gnupg/user/<uid>` directory for sockets, if it exists, instead of the default `/run/user/<uid>` one. This can be useful when starting a gpg-agent early and there is no `/run/user/<uid>` directory yet to avoid sockets creation in the `~/.gnupg` directory, that can lead to another agent, started later creating new socket under the `/run/user/<uid>` directory and not knowing about existing one under the `~/.gnupg`.

This flag should normally be disabled, unless there is a need to start GnuPG agent at the early stage, e.g. from the PAM stack.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.

### wks-server
Pass the `--enable-wks-tools` option to the configure script. Build and install the `gpg-wks-server` - a server-side implementation of the Web Key Service that receives requests for publication, sends confirmation requests, receives confirmations, and publishes keys.

This flag should only be enabled if there is a need to set-up WKS server.
