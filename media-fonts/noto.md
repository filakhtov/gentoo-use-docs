# media-fonts/noto

### cjk
Pull in the [media-fonts/noto-cjk](../media-fonts/noto-cjk.md) package as a dependency that provides CJK (Chinese, Japanese, Korean) fonts from the Noto font family.

It is safe to disable the flag if there is no need for CJK fonts.

### X
Generate and install various files needed by the X Server to properly handle the font: `fonts.dir` - list of fonts in the directory and files they are stored in, `fonts.scale` - list of scalable fonts in the directory, `encodings.dir` - list of known encodings and the files they are stored in.

This flag should be enable if there is a need to use the font for the X Server.
