# media-libs/alsa-lib

### alisp
Pass the `--enable-alisp` option to the configure script. Build and inastll ALSA lisp interpreter that can be used as a script language to configure alsa. Install base `alisp` configuration files: `aliases.alisp`, `sndo-mixer.alisp`, `sndop-mixer.alisp` and the `sndoc-mixer.alisp`.

This flag should only be enabled if there is a need to use Lisp language for configuration.

### debug
Pass the `--with-debug` option to the configure script. Enable runtime asserts and special debugging error handler that would print extra information at runtime when error occurs.

This flag should normally be disabled and is intended for debugging purposes.

### doc
Execute the `make doc` command to generate an API documentation using the Doxygen tool and install it into the `/usr/share/doc/alsa-lib-<VERSION>/html` directory.

It is safe to disable the flag.

### python
Pass the `--enable-python` option to the configure script. Build and install the `smixer-python` module that provides Python bindings in form of simple abstact wrapper for the mixer interface.

This flag should only be enabled if there is a need to use `smixer_python` module in Python scripts.

### thread-safety
Pass the `--enable-thread-safety` option to the configure script. Make sure that some PCM functions (e.g. `snd_pcm_avail_update`) are thread-safe and can be called concurrently from multiple threads, and all the functions that are often called during streaming are also covered as thread-safe. When enabled, thread-safe behavior also can be disabled at runtime on per application basis by setting `LIBASOUND_THREAD_SAFE` environment variable to zero.

It is recommended to enable this flag.
