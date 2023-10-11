# media-libs/libsamplerate

### test
Pass the `--enable-alsa`, `--enable-fftw` and `--enable-sndfile` options to the configure script. Execute the `make check` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.
