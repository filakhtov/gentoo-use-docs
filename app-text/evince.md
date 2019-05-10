# app-text/evince

### djvu
Pass the `--enable-djvu` option to the configure script. Build and install the `libdjvudocument` library that uses the `djvulibre` library to provide an ability to view DjVu format designed primarily to store scanned documents, especially those containing a combination of text, line drawings, indexed color images, and photographs.

This flag should be enabled if there is a need to view DjVu documents.

### dvi
Pass the `--enable-dvi` option to the configure script. Build and install the `libdvidocument` that uses the TeX Live tools in order to view DVI (device independent file format) documents that are produced by the TeX typesetting program.

This flag should be enabled if there is a need to view DVI documents.

### gnome
Pass the `--enable-libgnome-desktop` option to the configure script. Use the `libgnome-desktop` library to cache generated previews of the document's first pages for fast access in the list of recently opened documents.

It is safe to disable the flag.

### gnome-keyring
Pass the `--with-keyring` option to the configure script. Use the `libsecret` library to integrate with the GNOME keyring daemon to store and retrieve passwords for password-protected PDF documents.

This flag should be enabled for keyring integration.

### gstreamer
Pass the `--enable-multimedia` option to the configure script. Use the GStreamer library to provide an ability to play multimedia files embedded into PDF documents with built-in player.

It is safe to disable the flag.

### introspection
Pass the `--enable-introspection` option to the configure script. Generate and install the `EvinceDocument-3.0.gir` and `EvinceView-3.0.gir` GIR metadata files to provide dynamic bindings for the `libevdocument3` and `libevview3` libraries to languages other than C using the GObject Introspection framework.

The flag can be safely disabled.

### nautilus
Pass the `--enable-nautilus` option to the configure script. Build the `libevince-properties-page.so` library that provides Nautilus plugin that adds a properties page to document properties dialog to show additional information for PDF and other document types, and install it into the `/usr/lib/nautilus/extensions-3.0/` directory.

It is safe to disable the flag and should only be enabled if Nautilus file manager is used.

### nsplugin
Pass the `--enable-browser-plugin` option to the configure script. Build and install the `libevbrowserplugin` library that provides NPAPI (Netscape Plugin Application Programming Interface) plugin for displaying PDF documents inside of the browser. This extension can be used by the number of browsers, such as Basilisk, GNOME Web, Midori, Konqueror, etc. It is not supported by modern versions of Opera, Firefox or Chromium/Chrome.

This flag can be safely disabled.

### postscript
Pass the `--enable-ps` option to the configure script. Build and install the `libpsdocument` library that uses the `libspectre` library to provide an ability to view documents in the Adobe PostScript format.

It is safe to disable the flag.

### spell
Pass the `--with-gspell` option to the configure script. Use the gspell library to enable spell-checking capabilities. Both, a document content and annotations support is provided.

This flag can be safely disabled.

### t1lib
Only makes sense when the `dvi` flag is enabled. Pass the `--enable-t1lib` option to the configure script. Link the `libdvidocument` library against the `t1lib` library to provide support for the scalable Adobe Type 1 (aka PostScript Type 1) fonts to improve font rendering quality.

It is recommended to enable this flag, otherwise rendered fonts in DVI document might look poorly.

### tiff
Pass the `--enable-tiff` option to the configure script. Build and install the `libtiffdocument` library that uses the `libtiff` library and provides an ability to view multi-page TIFF documents.

It is safe to disable the flag.

### xps
Pass the `--enable-xps` option to the configure script. Build and install the `libxpsdocument` library that uses the `libgxps` library and provides an ability to view XPS (XML Paper Specification) documents, with support for both Microsoft XPS and OpenXPS formats.

The flag can be safely disabled.
