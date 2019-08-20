# media-libs/opus

### custom-modes
Pass the `--enable-custom-modes` option to the configure script. Enable support for Opus custom modes, that allows for sampling rates other than 8, 12, 16, 24, or 48 kHz and frame sizes other than multiples of 2.5 ms. This requires additional out-of-band signalling that Opus does not normally require and disables many of Opus' coding modes. Also, because it is an optional part of the specification, using Opus Custom may lead to compatibility problems.

It is recommended to keep this flag disabled, unless there is a very specific need to support custom modes.

### doc
Pass the `--enable-doc` option to the configure script. Use the Doxygen tool to generate the API documentation in the HTML format from annotated sources.

This flag should normally be disabled, because a produced documentation is developer centric.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libopus` library.

This flag should be disabled, unless there is a specific need for the static library.
