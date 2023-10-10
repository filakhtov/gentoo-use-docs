# media-gfx/exiv2

### bmff
Pass the `-DEXIV2_ENABLE_BMFF=true` option to the cmake command. Enable support for BMFF (ISO/IEC 14496-12, ISO Base Media File Format) tagged files, such as HEIC, HEIF, AVIF, CR3, JXL/bmff.

This flag can be safely disabled.

### doc
Update Doxygen config and run the `ninja doc` command to generate additional C++ API documentation in the HTML format, including class and namespace references, class hierarchy, etc and install it into the `/usr/share/doc/exiv2-<VERSION>` directory.

It is safe to disable the flag.

### examples
Install additional C++ code into the `/usr/share/doc/exiv2-<VERSION>/examples` directory that demonstrate how to use the `libexiv2` library for various use cases, including adding, modifying and deleting Exif metadata, setting Exif comment for an image, formatting Exif data in various external formats, get a single key from an Exif metadata of the image, etc.

The flag should normally be disabled, unless there is a need to access code examples.

### nls
Pass the `-DEXIV2_ENABLE_NLS=true` option to the cmake command. Use the Gettext library to support runtime translation of the programs messages based on the system locale, and generate and install translation PO files.

It is safe to disable the flag unless there is a need to use a non-English language.

### png
Pass the `-DEXIV2_ENABLE_PNG=true` option to the cmake command. Provide an ability to read and write PNG metadata defined in the section 11.3.4.2 of the [PNG specification](https://www.w3.org/TR/PNG/#11textinfo).

This flag should be enabled if there is a need to handle PNG files metadata.

### test
Pass the `-DEXIV2_BUILD_UNIT_TESTS=true` option to the cmake command. Build the `unit_tests` command and execute it after the build is completed to run the test suite provided with the source code and check for any regresions. This will extend the overall build time.

This flag should normally be disabled, because the test suite primarily oriented towards the developers, maintainers and testers, not the end users.

### webready
Pass the `-DEXIV2_ENABLE_CURL=true` and `-DEXIV2_ENABLE_WEBREADY=true` options to the cmake command. Use the `libssh` and `libcurl` libraries to enable "Web Ready" feature - support for reading and writing metadata using HTTP(S), FTP(S) and SSH protocols.

It is safe to disable the flag.

### xmp
Pass the `-DEXIV2_ENABLE_XMP=true` option to the cmake command. Also install additional documentation regarding XMP. Enable support for the XMP (Adobe's Extensible Metadata Platform) - a labeling technology that allows you to embed data about a file, known as metadata, into the file itself.

This flag should be enabled if there is a need to access XMP metadata through the `libexiv2`.
