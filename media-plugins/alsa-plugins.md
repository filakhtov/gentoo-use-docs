# media-plugins/alsa-plugins

### arcam_av
Pass the `--enable-arcamav` option to the configure script. This plugin exposes the controls for an Arcam AV amplifier (see: http://www.arcam.co.uk/) as an ALSA mixer device.

This flag should only ever be enabled if there is a need to use ARCAM amplifiers.

### debug
Debug mode is enabled by default, so this flag does nothing if enabled. When disabled, append the `-DNDEBUG` option to the `CPPFLAGS` environment variable for the duration of a build to convert runtime assertions into a no-op operations.

This flag should only be enabled if there is a need to debug the alsa plugins infrastructure or apps that use it.

### ffmpeg
Pass the `--enable-libav` option to the configure script. Build and install the `libasound_module_pcm_a52` and `libasound_module_rate_lavrate` plugins. The `libasound_module_pcm_a52` module uses the `libavcodec` library for converting an audio stream from linear S16 to compressed A52 format for output via an SPDIF output. The `libasound_module_rate_lavrate` module provides an external rate converter using the `libavresample` library that can be used by defining the rate PCM with `converter lavrate` parameter.

This flag should be enabled if there is a need to use SPDIF output or lavrate-based sample rate converter.

### jack
Pass the `--enable-jack` option to the configure script. Build and install the `libasound_module_pcm_jack` plugin to enable integration with the JACK (JACK Audio Connection Kit) subsystem for applications that use the ALSA API, providing an ability to output sound to and capture from Jack daemon.

This flag should be enabled if the target system needs to run ALSA based apps on top of the JACK.

### libsamplerate
Pass the `--enable-samplerate` option to the configure script. Build and install the `libasound_module_rate_samplerate`, `libasound_module_rate_samplerate_best`, `libasound_module_rate_samplerate_linear`, `libasound_module_rate_samplerate_medium` and `libasound_module_rate_samplerate_order` plugins to use external rate converter via the `libsamplerate` library.

It is safe to disable the flag.

### mix
Pass the `--enable-mix` option to the configure script. Build and install the `libasound_module_pcm_upmix` and `libasound_module_pcm_vdownmix` modules. The `libasound_module_pcm_upmix` module is an easy-to-use plugin for upmixing from stereo to 4 or 6-channel stream. The `libasound_module_pcm_vdownmix` plugin is a downmixer from 4-6 channels to 2-channel stereo headphone output. This plugin processes the input signals with a simple spacialization, so the output sounds like a kind of "virtual surround".

This flag should only be enabled if there is a need to upmix or downmix audio channels via ALSA.

### oss
Pass the `--enable-oss` option to the configure script. Build and install the `libasound_module_pcm_oss` and `libasound_module_ctl_oss` modules. This plugin converts the ALSA API (Advanced Linux Sound Architecture) over OSS API (Open Sound System). With this plugin, ALSA native apps can run on OSS drivers.

This flag should only ever be enabled on systems that use OSS drivers, which is deprecated and shouldn't be used unless absolutely necessary.

### pulseaudio
Pass the `--enable-pulseaudio` option to the configure script. Build and install the `libasound_module_conf_pulse`, `libasound_module_ctl_pulse` and `libasound_module_pcm_pulse` plugins to allow any program that uses the ALSA API to access a PulseAudio sound daemon. This includes playing and recording over the network and provides PCM and mixer control.

This flag should only be enabled if there is a need to access the PulseAudio server from ALSA based apps.

### speex
Build and install the `libasound_module_pcm_speex`, `libasound_module_rate_speexrate`, `libasound_module_rate_speexrate_best` and `libasound_module_rate_speexrate_medium` plugins. Provides a pre-processing of a mono stream like denoise using `libspeex` library DSP API (Digital Signal Processing API) and an external rate converter using the Speex resampler.

It is safe to disable the flag.

### usb_stream
Pass the `--enable-usbstream` option to the configure script. Build and install the `libasound_module_pcm_usb_stream` module - the plugin for `snd-usb-us122l` driver that converts PCM stream to USB specific stream.

This flag should only be enabled if there is a need to use Tascam US-122L USB Audio/MIDI devices.
