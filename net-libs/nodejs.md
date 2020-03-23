# net-libs/nodejs

### debug
Patch the `tools/install.py` script to change install path, remove optimisations and override buildtype. Pass the `--debug` option to the configure script.

### doc
Patch docs to remove Google fonts references and make them offline readable. Install developers, collaborators, releasing and API documentation into the `/usr/share/doc/nodejs-<VERSION>/html` directory.

It is safe to disable the flag.

### icu
Pass the `--with-intl=system-icu` option (`none` when the flag is disabled) to the configure script. Use the `libicu` library to enable features that make it easier to write internationalized programs, e.g. locale-sensitive or Unicode-aware functions in the ECMAScript Language Specification, locale-sensitive methods like `String.prototype.localeCompare()` and `Date.prototype.toLocaleString()`, the WHATWG URL parser's internationalized domain names (IDNs) support, RegExp Unicode Property Escapes.

It is safe to disable the flag.

### inspector
Enable support for the runtime `--inspect` switch for the `node` command to listen via WebSockets for diagnostic commands as defined by the Inspector Protocol. Inspector also includes an HTTP endpoint to serve metadata about the debuggee, including its WebSocket URL, UUID, and Chrome DevTools URL. When disabled, pass the `--without-inspector` option to the configure script.

It is safe to disable the flag.

### npm
Build and install an `npm` tool - a package manager for Node.js modules. When disabled, pass the `--without-npm` option to the configure script to not build the NPM.

It is safe to disable the flag.

### snapshot
Pass the `--with-snapshot` option to the configure script. Use V8's startup snapshots to speed up Node.js early boostrap process, and instead of creating V8 objects from scratch - deserialize the object graph from previously serialized state and thus significantly speed up starting (up to two orders of magnitude).

It is recommended to enable this flag to improve startup performance.

### system-ssl
Requires the `ssl` flag to be enabled. Pass the `--shared-openssl` and `--openssl-use-def-ca-store` options to the configure script. Link against the system shared OpenSSL library, instead of statically linking to the embedded copy, and switch to use system OpenSSL supplied CA (Certificate Authority) store instead of compiled-in Mozilla CA copy.

It is recommended to enable this flag.

### systemtap
Pass the `--with-dtrace` option to the configure script. Provide an ability to profile Node.js applications to figure out where a program spends its time using the `DTrace` tracing framework.

This flag should only be enabled if there is a need to perform profiling.

### ssl
Pass the `--shared-openssl` option to the configure script. Build and install a number of additional Node modules: the `tls` module that provides an implementation of the TLS (Transport Layer Security) and SSL (Secure Socket Layer) protocols that is built on top of OpenSSL; the `crypto` module that provides cryptographic functionality that includes a set of wrappers for OpenSSL's hash, HMAC, cipher, decipher, sign, and verify functions. Also, enable OpenSSL related CLI (Command-Line Interface) runtime options. When disabled, pass the `--without-ssl` option to the configure script.

It is recommended to enable this flag, otherwise cryptographical functionality, including HTTPS won't be available.

### test
Execute the `cctest` command from the `out/Release` directory (or `out/Debug` if the `debug` flag is enabled), followed by the `tools/test.py` script when the main build is completed. Run the regression test suite provided with the source code. This will extend a build time.

This flag should normally be disabled. It is mainly useful for the Gentoo team, developers and testers.
