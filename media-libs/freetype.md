# media-libs/freetype

### adobe-cff
By default the FreeType library uses the Adobe CFF (Type 1) font rasterizer instead of one developed by FreeType, so enabling this flag does nothing. Disabling it, however, will patch the `ftoption.h` file to define `CFF_CONFIG_OPTION_OLD_ENGINE` macro and therefore switch hinting engine to the old implementation for CFF fonts.

It is safe to disable the flag, however it will reduce rendering quality for Type 1 fonts.

### bindist
The ClearType LCD filtering is patented by several Microsoft patents and therefore it is not allowed to redistribute compiled package. When disabled, patch the `ftoption.h` file to define the `FT_CONFIG_OPTION_SUBPIXEL_RENDERING` macro and therefore enable the ClearType rendering technology that uses LCD subpixels to improve font rendering, however resulting built binaries can't be redistributed.

This flag should be disabled if there is a need to redistribute compiled binaries.

### brotli
Pass the `--with-brotli` option to the configure script. Enable support for WOFF 2 (Web Open Font Format version 2) fonts, which has been a W3C recommendation since early 2018 as a successor to the older WOFF format and makes use of the Brotli compression algorithm and other improvements leading to smaller font files.

This flag can be safely disabled.

### bzip2
Pass the `--with-bzip2` option to the configure script. Use the `libbz2` library to provide support for BZip2 compressed fonts. This is mainly used to parse compressed PCF (portable compiled format) fonts.

It is safe to disable the flag.

### cleartype-hinting
Patch the `ftoption.h` file to define the `TT_CONFIG_OPTION_SUBPIXEL_HINTING` macro and set its value to `2`. Enable subpixel hinting support for the TrueType driver. Use Infinality (v40) code base that was stripped to the bare minimum, all configurability removed in the name of the speed and simplicity. This mode applies minimal set of rules to all fonts indiscriminately so that modern fonts render well and legacy fonts render okay.

It is recommended to enable this flag as it is default mode for the FreeType library.

### debug
Patch the `ftoption.h` file to define the `FT_DEBUG_LEVEL_TRACE` and the `FT_DEBUG_MEMORY` macros. The former reports runtime errors by sending them to the standard output, while the latter compiles an integrated memory debugger that helps detecting simple memory errors like leaks or double deletes. Provide support for the `FT2_DEBUG_MEMORY` runtime environment variable.

This flag should only be enabled if there is a need to debug the library itself or applications linked against it.

### doc
Install additional documentation in the HTML format into the `/usr/share/doc/freetype-<VERSION>/html` directory. Also install plain text documentation with information on how to customize the compilation of the library, enable debugging features, upgrade between versions, cross-build library, troubleshoot as well as describing font formats, how rasterizer works and so on.

It is safe to disable the flag.

### fontforge
Copy header files from the FreeType library into the `/usr/include/freetype2/internal4fontforge` directory. These headers are needed by the [media-gfx/fontforge](../media-gfx/fontforge.md) package and location of the aforementioned directory is passed as a value to the `--with-freetype-src` option for the `FontForge` configure script if the `freetype-debugger` flag is enabled.

This flag should only be enabled if there is a need to build the `FreeType` package with the `freetype-debugger` option enabled.

### harfbuzz
Pass the `--with-harfbuzz` option to the configure script. Use the HarfBuzz library to improve auto-hinting of OpenType fonts. If available, many glyphs not directly addressable by a font's character map will be also hinted.

This flag should be enabled to improve OpenType fonts rendering.

### png
Pass the `--with-png` option to the configure script. Provide support for PNG compressed OpenType embedded bitmaps (also called 'sbits' for "scaler bitmaps"). One use of such bitmaps is emoji fonts.

It is safe to disable this flag, however color bitmaps support won't be available.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libfreetype` library. When disabled, remove all static archives before installing the package.

This flag should only ever be enabled if there is a need for the static library.

### svg
Only works if the `utils` flag enabled. Pass the `--with-librsvg` option to the configure script. Enable support for OpenType SVG fonts in FreeType demo programs.

This flag should normally be disabled.

### utils
Download and unpack an additional `ft2demos` source code. Use this source to build and install additional binary tools:

- `ttdebug` - a simple TTF font debugger
- `ftbench` - a set of FreeType benchmarks
- `ftdump` - a simple font dumper
- `ftvalid` - a layout table validator
- `ftlint` - a simple font tester/linter

It is safe to disable the flag.

### X
This flag only works if the `utils` flag is also enabled. Build and install the `ftdiff` tool aka FreeType Text Proofer that can display graphical font diffs with various rendering settings.

This flag can be safely disabled.
