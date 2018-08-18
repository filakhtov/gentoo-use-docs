# media-plugins/alsa-plugins

### debug
Debug mode is enabled by default, so this flag does nothing if enabled. When disabled, append the `-DNDEBUG` option to the `CPPFLAGS` environment variable for the duration of a build to convert runtime assertions into a no-op operations.

This flag should only be enabled if there is a need to debug the alsa plugins infrastructure or apps that use it.

### ffmpeg
Pass the `--enable-avcodec` option to the configure script. Build and install the `libasound_module_pcm_a52` plugin that uses the `libavcodec` library for converting an audio stream from linear S16 to compressed A52 format for output via an SPDIF output.

This flag should be enabled if there is a need to use SPDIF output.

### jack
Pass the `--enable-jack` option to the configure script. Build and install the `libasound_module_pcm_jack` plugin to enable integration with the JACK (JACK Audio Connection Kit) subsystem for applications that use the ALSA API, providing an ability to output sound to and capture from Jack daemon.

This flag should be enabled if the target system needs to run ALSA based apps on top of the JACK.

### libav
Only works if the `ffmpeg` flag is also enabled. Provide an ability to use the Libav library instead of FFmpeg one for the SPDIF format compression. See the `ffmpeg` flag.

This option should only be toggled system-wide, because the FFmpeg and Libav libraries can not be installed at the same time.

### libsamplerate
Pass the `--enable-samplerate` option to the configure script. Build and install the `libasound_module_rate_samplerate`, `libasound_module_rate_samplerate_best`, `libasound_module_rate_samplerate_linear`, `libasound_module_rate_samplerate_medium` and `libasound_module_rate_samplerate_order` plugins to use external rate converter via the `libsamplerate` library.

It is safe to disable the flag.

### pulseaudio
Pass the `--enable-pulseaudio` option to the configure script. Build and install the `libasound_module_conf_pulse`, `libasound_module_ctl_pulse` and `libasound_module_pcm_pulse` plugins to allow any program that uses the ALSA API to access a PulseAudio sound daemon. This includes playing and recording over the network and provides PCM and mixer control.

This flag should only be enabled if there is a need to access the PulseAudio server from ALSA based apps.

### speex
Build and install the `libasound_module_pcm_speex`, `libasound_module_rate_speexrate`, `libasound_module_rate_speexrate_best` and `libasound_module_rate_speexrate_medium` plugins. Provides a pre-processing of a mono stream like denoise using `libspeex` library DSP API (Digital Signal Processing API) and an external rate converter using the Speex resampler.

It is safe to disable the flag.
