# sys-fs/cryptsetup

### argon2
Pass the `--enable-libargon2` and `--with-luks2-pbkdf=pbkdf2` options to the configure script. Use the `libargon2` library to provide an ability to use the Argon2 key derivation function for PBKDF (Password-Based Key Derivation Function) available in LUKS2 header format.

This flag should only be enabled if there is a need to use Argon2 key derivation algorithm.

### gcrypt
Pull a [dev-libs/libgcrypt](../dev-libs/libgcrypt.md) package as a dependency. Pass the `--with-crypto_backend=gcrypt` option to the configure script. Use a libgcrypt library as an encryption and a decryption backend. A Libgcrypt built with threads can't be used while statically linking (`static` flag, see [Gentoo bug #496612](https://bugs.gentoo.org/496612)).

This flag should normally be disabled because gcrypt performs very slow (even slower than Kernel) according to benchmarks.

### kernel
Pass the `--with-crypto_backend=kernel` option to the configure script. Use Kernel routines as a cryptographic backend. This backend is very slow according to various benchmarks and usually is not recommended.

This flag should be disabled unless the target system is an embedded system and provides no userspace cryptographic libraries.

### nettle
Pass the `--with-crypto_backend=nettle` option to the configure script. Use a Nettle library as a backend for an encryption and a decryption operations. This is a fastest backend according to benchmarks. It does not support `whirlpool` hash function.

It is recommended to enable this flag due to performance benefits it brings.

### nls
Pass the `--enable-nls` option to the configure script. Enable localization support using gettext and install translation files.

This flag should be enabled if there is a need to display cryptsetup error messages or help texts in languages other than English, otherwise it is safe to disable.

### openssl
Pass the `--with-crypto_backend=openssl` option to the configure script. Use OpenSSL library as a backend for an encryption and a decryption operations.

This flag should be enabled if there is no desire to use `nettle` or there is a need to use `whirlpool` hash function.

OpenSSL performs around 20% to 40% slower than Nettle according to benchmarks.

### pwquality
Pass the `--enable-pwquality` option to the configure script. Enable a decryption passphrase complexity/quality checking using pwquality library.

It is safe to disable this flag but it can be used to improve passphrase security.

### reencrypt
Pass the `--enable-cryptsetup-reencrypt` option to the configure script. Build and install a `cryptsetup-reencrypt` tool for offline LUKS device re-encryption (change encryption parameters which otherwise require full on-disk data change).

It is safe to disable this flag unless there is a need to re-encrypt LUKS devices.

### ssh
Pass the `--enable-ssh-token` option to the configure script. Build and install the `cryptsetup-ssh` experimental cryptsetup plugin for unlocking LUKS2 devices with token connected to an SSH server.

It is safe to disable this flag.

### static
Pass the `--enable-static-cryptsetup` option to the configure script. Build and install statically linked binaries, e.g. a `cryptsetup`, a `veritysetup` and etc.

This flag should normally be disabled unless there is an explicit need for static binaries.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked `libcryptsetup` library. When this flag is disabled, pass the `--enable-external-tokens` option to the configure script to enable loading of plugins for external LUKS2 tokens.

This flag should be normally disabled unless there is an explicit requirement for a static library.

### test
Execute the `make check` command after the main build is completed to run the test suite provided with the source code and check for regressions. This will extend overall build time.

This flag should normally by disabled, because these tests are primarily oriented towards the developers, maintainers and testers.

### udev
Pass the `--enable-udev` option to the configure script. Use a `libdevmapper`'s udev synchronisation to prevent DM and UDEV getting out of sync and leading to e.g. inaccessible device nodes.

It is recommended do enable this flag.

### urandom
When disabled pass the `--enable-dev-random` option to the configure script to use the `/dev/random` for cryptographically secure random number generation. When enabled - use a `/dev/urandom` instead.

This flag should normally be enabled, because `/dev/urandom` is a preferred source of cryptographic randomness on modern UNIX-like systems. It should only be disabled on platforms and systems that have issues with `urandom`.
