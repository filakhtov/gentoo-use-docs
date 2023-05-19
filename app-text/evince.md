# app-text/evince

### cups
Pass the `-Dgtk_unix_print=enabled` option to the meson build script. Enable support for new Gtk+ Printing API (instead of using unmaintained `libgnomeprint` library) to provide an ability to print documents and configure relevant printing settings, such as page setup, image quality etc.

It is safe to disable this flag.

### djvu
Pass the `-Ddjvu=enabled` option to the meson build script. Build and install the `libdjvudocument` library that uses the `djvulibre` library to provide an ability to view DjVu format designed primarily to store scanned documents, especially those containing a combination of text, line drawings, indexed color images, and photographs.

This flag should be enabled if there is a need to view DjVu documents.

### dvi
Pass the `-Ddvi=enabled` option to the meson build script. Build and install the `libdvidocument` that uses the TeX Live tools in order to view DVI (device independent file format) documents that are produced by the TeX typesetting program.

This flag should be enabled if there is a need to view DVI documents.

### gnome
Pass the `-Dthumbnail_cache=enabled` option to the meson build script. Use the `libgnome-desktop` library to cache generated previews of the document's first pages for fast access in the list of recently opened documents.

It is safe to disable the flag.

### gstreamer
Pass the `-Dmultimedia=enabled` option to the meson build script. Use the GStreamer library to provide an ability to play multimedia files embedded into PDF documents with built-in player.

It is safe to disable the flag.

### gtk-doc
Pass the `-Dgtk_doc=true` option to the meson build script. Use the Gtk-Doc tool to generate an API reference documentation for the `libevdocument3` library in the HTML format and install it into the `/usr/share/gtk-doc` directory.

### introspection
Pass the `-Dintrospection=true` option to the meson build script. Generate and install the `EvinceDocument-3.0.gir` and `EvinceView-3.0.gir` GIR metadata files to provide dynamic bindings for the `libevdocument3` and `libevview3` libraries to languages other than C using the GObject Introspection framework.

The flag can be safely disabled.

### keyring
Pass the `-Dkeyring=enabled` option to the meson build script. Use the `libsecret` library to integrate with the GNOME keyring daemon to store and retrieve passwords for password-protected PDF documents.

This flag should be enabled for keyring integration.

### nautilus
Pass the `-Dnautilus=true` option to the meson build script. Build the `libevince-properties-page.so` library that provides Nautilus plugin that adds a properties page to document properties dialog to show additional information for PDF and other document types, and install it into the `/usr/lib/nautilus/extensions-3.0/` directory.

It is safe to disable the flag and should only be enabled if Nautilus file manager is used.

### postscript
Pass the `-Dps=enabled` option to the meson build script. Build and install the `libpsdocument` library that uses the `libspectre` library to provide an ability to view documents in the Adobe PostScript format.

It is safe to disable the flag.

### spell
Pass the `-Dgspell=enabled` option to the meson build script. Use the gspell library to enable spell-checking capabilities. Both, a document content and annotations support is provided.

This flag can be safely disabled.

### tiff
Pass the `-Dtiff=enabled` option to the meson build script. Build and install the `libtiffdocument` library that uses the `libtiff` library and provides an ability to view multi-page TIFF documents.

It is safe to disable the flag.

### xps
Pass the `-Dxps=enabled` option to the meson build script. Build and install the `libxpsdocument` library that uses the `libgxps` library and provides an ability to view XPS (XML Paper Specification) documents, with support for both Microsoft XPS and OpenXPS formats.

The flag can be safely disabled.
