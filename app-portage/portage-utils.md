# app-portage/portage-utils

### libressl
Allow using the `libressl` library instead of the `openssl` library for cryptographic computations (hashing and signature verification).

This flag should only ever be toggled system-wide, because OpenSSL and LibreSSL can't be simultaneously installed on the same system.

### nls
Pass a `NLS=yes` option to the make command. Use a Gettext library to translate programs messages into various languages based on the system locale settings.

The flag should be enabled if there is a need to use any non-English languages.

### openmp
Only works if the `qmanifest` and/or `qtegrity` flag is enabled. Pass the `--enable-openmp` option to the configure script. Use the OpenMP library to perform parallel directory processing for the `qverify` and `qtegrity` applets.

This flag should be enabled to speed-up manifest generation and verification.

### qmanifest
Pass the `--enable-qmanifest` option to the configure script. Build and install the `qmanifest` applet (aka `hashgen` or `hashverify`) that is used to verify or generate thick Manifest files.

This flag can be safely disabled if there is no need to perform the manifest verification.

### qtegrity
Pass the `--enable-qtegrity` option to the configure script. Build and install the `qtegrity` (aka `integrity`) applet, that can be accessed through the `q qtegrity` and `q integrity` commands and used to verify digests of performed executables to a list of known good digests. This requires an IMA-enabled (Integrity Measurement Architecture) linux kernel, which records digests of performed executables and exports them through `securityfs`.

This flag should be enabled if there is a need to perform the IMA verification.

### static
Pass the `--enable-static` option to the configure script. Statically link all produced binaries: `q`, `qlist`, `qsearch`, etc.

This flag should only be enabled if there is a need for static binaries.
