# dev-libs/gmime

### doc
Execute the `make html` command from the `docs/tutorial` source subdirectory. Generate tutorial in the HTML format and install it into the `/usr/share/doc/gmime-<VERSION>/tutorial` directory. Tutorial includes library description, building process, linking against the library, data structures overview, etc. When disabled, pass the `DB2HTML=` variable to the configure script to prevent docs generation.

It is safe to disable the flag.

### mono
Prepare an environment for the configure script to find an appropriate version of Mono files. Pass the `--enable-mono` option to the configure script. Build and install the `gmime-sharp.dll` Mono library to provide .NET bindings for the `libgmime` library and provide the `GMime` namespace.

This flag should only be enabled if there is a need for the Mono library.

### smime
Pass the `--enable-smime` option to the configure script. Enable experimental support for S/MIME signatures. Use the GPGme library for S/MIME signature verification, encryption, signing and decryption features.

It is safe to disable the flag.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libgmime` library.

This flag should only be enabled if there is an explicit need for the static library.

### test
Execute the `make check` command when the main build is completed to run the regression test suite provided with the source code. This will extend an overall build time.

This flag should normally be enabled as it is primarily used by the Gentoo team, developers and testers.

### vala
Prepare environment for the configure script to find an appropriate version of Vala files. Pass the `--enable-vala` option to the configure script. Generate and install the `gmime-2.6.vapi` Vala language bindings for the `libgmime` library.

It is safe to disable the flag.
