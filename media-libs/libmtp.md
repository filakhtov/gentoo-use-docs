# media-libs/libmtp

### crypt
Pass a `--enable-mtpz` option to a configure script. Enable support for a MTPZ protocol, which is a ZUNE-specific extension to MTP. Before any copy operation, MPTZ sends an encrypted challenge to the computer, which must respond by decrypting the challenge message with a key and sending a proper reply.

This flag should be enabled if there is a need to transfer files to Microsoft Zune media player.

### doc
Pass a `--enable-doxygen` option to a configure script. Use a Doxygen tool to generate an API documentation out of the source code and included annotations.

It is safe to disable the flag.

### examples
Install example files showing how to use a `libmtp` library into the `/usr/share/doc/libmtp-<VERSION>/examples` directory. Examples are available in C language and include a variety of usages: sending album arts, deleting file off a device, detect a device and fetch its capabilities, list files on a device, etc.

This flag can be safely disabled.

### static-libs
Pass a `--enable-static` option to a configure script. Build and install a statically linked version of the `libmtp` library.

This flag should only ever be enabled if there is an explicit need for the static library.
