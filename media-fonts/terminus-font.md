# media-fonts/terminus-font

### a-like-o
Apply a patch to change the lowercase letter `A` that it looks like Latin `alpha`.

It is safe to disable the flag.

### center-tilde
Apply a patch to change `~` tilde to be displayed at the middle height of the line instead of normal top position.

It is safe to disable the flag.

### distinct-l
Apply a patch to change the lowercase letter `L` to be distinct from digit `1`.

It is safe to disable the flag.

### otf
Execute the `make otb` command to combine BDF (Glyph Bitmap Distribution Format) files provided by the package into a single OTB (OpenType Bitmap) font and execute the `make install-otb` command to install it into the system.

It is safe to disable this flag.

### pcf-8bit
Execute the `make pcf-8bit` command to build fonts in the PCF (Portable Compiled Format) for various encodings, then the `make install-pcf` command to install them.

This flag should be enabled if there is a need for the PCF fonts, e.g. for use with the X Server.

### pcf-unicode
Execute the `make pcf` command to build fonts in the PCF (Portable Compiled Format) with unicode support, then the `make install-pcf` command to install them.

This flag should normally be enabled, unless the target system uses non-Unicode locale settings.

### psf
Execute the `make psf psf-vgaw` to build fonts in PSF (PC Screen Font) format, then the `make install-psf install-psf-vgaw install-psf-ref` to install them. Install PSF fonts that are used by the Linux Kernel for console characters into the `/usr/share/consolefonts` directory.

This flag should be enabled if terminus font to be used for console.

### quote
Apply a patch to change the quote `"` to render as double arrows, e.g. `<<`.

It is safe to disable the flag.

### ru-dv
Apply a patch to change the Russian `d` and `v` letters rendering to the proper cyrillic version.

It is safe to disable the flag.

### ru-g
Apply a patch to change the Russian `g` letter to look like upside down letter `s` instead of `r`.

It is safe to disable the flag.

### ru-i
Apply a patch to change the Russian `i` letter to look like mirrored letter `N` instead of `u`.

It is safe to disable the flag.

### ru-k
Apply a patch to change the Russian `k` letter to look like smaller version of english capital `K`.

It is safe to disable the flag.

### X
Generate and install various files needed by the X Server to properly handle the font: `fonts.dir` - list of fonts in the directory and files they are stored in, `fonts.scale` - list of scalable fonts in the directory, `encodings.dir` - list of known encodings and the files they are stored in.

This flag should be enabled if there is a need to use the font for X Server.
