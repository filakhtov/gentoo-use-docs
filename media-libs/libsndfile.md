# media-libs/libsndfile

### alsa
Pass the `--enable-alsa` option to the configure script. Build and install the `sndfile-play` tool to play the specified sound file using ALSA.

This flag can be safely disabled.

### minimal
This flag does nothing if enabled. When enabled, pass the `--enable-external-libs` option to the configure script. Enable optional linking against the `libogg`, `libFLAC` and `libvorbis` libraries if they are available in the target system to support Ogg, FLAC and Vorbis audio formats accordingly.

It is safe to disable the flag.

### sqlite
Pass the `--enable-sqlite` option to the configure script. Build additional regression tests that use SQLite3 to store test data.

This flag should normally be disabled, and should only be enabled with the `test` flag, if regression tests are needed.

### test
Prepare Python environment for running tests. Execute the `make check` command, to run a test suite provided with the source code, after the main build is completed. This will extend a build time.

This flag should normally be disabled as it is mainly used by the testers, developers or the Gentoo team.
