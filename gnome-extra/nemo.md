# gnome-extra/nemo

### exif
Pass a `--enable-libexif` option to a configure script. Use a `libexif` library to read and decode an EXIF (EXchangeable Image Format) metadata tags from media files created by digital cameras, and display this information in a file properties dialog or as media columns in a table view of the files list.

This flag should be enabled if there is a need to display EXIF metadata.

### introspection
Pass a `--enable-introspection` option to a configure script. Generate and install a `Nemo-3.0.gir` GIR metadata file to provide dynamic bindings for a `libnemo-extension` library to languages other than C using a GObject Introspection infrastructure.

It is safe to disable the flag.

### nls
Pull in a [gnome-extra/cinnamon-translations](../gnome-extra/cinnamon-translations.md) package as a dependency to provide translations for Cinnamon ecosystem.

This flag should be enabled if there is a need to run Cinnamon in a non-English language.

### packagekit
This flag should be disabled as it does nothing.

### test
Start a new Xvfb session and execute the `make check` command inside of it when the main build is completed. Run a test suite provided with the source code. This will extend a build time.

The flag should normally be disabled. It is mainly targeted for the Gentoo team, testers and developers.

### tracker
Pass a `--enable-tracker` option to a configure script. Integrate Nemo's file searching feature with Tracker indexing tool to provide an ability to lookup files using their contents and metadata, such as the artist of a song or the author of a document.

This flag should be enabled if there is a need to use Tracker features for searching.

### xmp
Pass a `--enable-xmp` option to a configure script. Integrate with a `libexempi` library to read an XMP (Extensible Metadata Platform) image metadata, such as location, description, subject and others, and display this information in an image file properties dialog.

This flag should be enabled if there is a need to display XMP metadata.
