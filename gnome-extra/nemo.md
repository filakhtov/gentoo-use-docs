# gnome-extra/nemo

### exif
Pass the `-Dexif=true` option to the `meson` build script. Use the `libexif` library to read and decode an EXIF (EXchangeable Image Format) metadata tags from media files created by digital cameras, and display this information in a file properties dialog or as media columns in a table view of the files list.

This flag should be enabled if there is a need to display EXIF metadata.

### gtk-doc
Pass the `-Dgtk_doc=true` option to the `meson` build script. Use the Gtk-Doc tool to generate the Nemo Extension Reference Manual from the source code annotations in the `libnemo-extension` library source code in the HTML format and install it into the system.

It is safe to disable this flag.

### nls
Pull in a [gnome-extra/cinnamon-translations](../gnome-extra/cinnamon-translations.md) package as a dependency to provide translations for Cinnamon ecosystem.

This flag should be enabled if there is a need to run Cinnamon in a non-English language.

### selinux
Pass the `-Dselinux=true` option to the meson build script. Use the `libselinux` library to read the SELinux context information from files in the filesystem and display them in the file properties dialog.

It is safe to disable this flag.

### test
Start a new Xvfb session and execute the `meson test` command inside of it when the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

The flag should normally be disabled, as it is mainly targeted for the maintainers, testers and developers.

### tracker
Pass the `-Dgtk_doc=true` option to the `meson` build script. Integrate with Tracker search engine to provide real-time searching and browsing of file contents, full-text search for supported document types and perform advanced search queries.

It is safe to disable this flag.

### xmp
Pass a `-Dxmp=true` option to the `meson` build script. Integrate with the `libexempi` library to read an XMP (Extensible Metadata Platform) image metadata, such as location, description, subject and others, and display this information in an image file properties dialog.

This flag should be enabled if there is a need to display XMP metadata.
