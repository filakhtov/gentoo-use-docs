# media-video/ffmpeg

### alsa
Provide an ability to capture and playback audio via the ALSA system and enable support for the `alsa` value of the `-f` runtime option. When disabled, pass the `--disable-indev=alsa` and `--disable-outdev=alsa` options to the configure script to disable ALSA support.

This flag should be enabled if there is a need to play or record audio through ALSA devices.

### amr
Pass the `--enable-version3`, `--enable-libopencore-amrwb` and `--enable-libopencore-amrnb` options to the configure script. Use the `libopencore-amrnb` and `libopencore-amrwb` libraries to perform AMR-NB (Adaptive Multi-Rate NarrowBand) and AMR-WB (Adaptive Multi-Rate WideBand) decoding instead of FFmpeg's native implementation. Resulting libraries will be licensed under (L)GPL version 3.

This flag should normally be disabled.

### amrenc
Only works if the `encode` flag is enabled. Pass the `--enable-version3` and `--enable-libvo-amrwbenc` option to the configure script. Use the `libvo-amrwbenc` library to enable support for encoding audio in the AMR format. Resulting libraries and binaries will be licensed under the (L)GPL3 license due to the restrictions of that library.

This flag should only be enabled if there is a need to perform audio encoding in AMR format.

### appkit
Pass the `--enable-appkit` option to the configure script. Enable support for the Apple AppKit framework, that can be used to render decoded video frames using the native macOS API.

This flag should be disabled as it only works on Apple macOS systems.

### bluray
Pass the `--enable-libbluray` option to the configure script. Use the `libbluray` library to provide an ability to play Blu-ray discs and enable support for the `bluray:` protocol to do so.

This flag should only be enabled if there is a need to play Blu-ray media.

### bs2b
Pass the `--enable-libbs2b` option to the configure script. Use the `libbs2b` library to enable support for the bauer stereo to binaural transformation, which improves headphone listening of stereo audio records.

It is recommended to enable this flag if there is a need for stereophonic-to-binaural filter.

### bzip2
Pass the `--enable-bzlib` option to the configure script. Use the `libbz2` library to enable support for compressed Matroska files that use the bzip2 algorithm for content compression.

It is recommended to enable this flag if there is a need to play Matroska files.

### cdio
Requires the `gpl` flag to be enabled, due to license restrictions. Pass the `--enable-libcdio` option to the configure script. Use the `libcdio` library to provide an ability to play and extract audio tracks from Audio-CDs. Enable support for the `libcdio` format of the `-f` runtime option.

This flag should be enabled if there is a need to access Audio-CDs.

### chromaprint
Pass the `--enable-chromaprint` option to the configure script. Enable the Chromaprint fingerprinter - a muxer that feeds audio data to the `libchromaprint` library to generate a fingerprint for the provided audio data. This is part of the AcoustID project that provides complete audio identification service.

It is safe to disable the flag.

### chromium
Perform additional compilation of the `libffmpeg` library from the separate build directory, that is specifically targeted for use with the Chromium-based browser, such as Opera, Vivaldi and others. Without this flag enabled such browsers will only be able to play open codecs.

This flag should be enabled if the system uses a Chromium based browser and there is a need to play non-free codecs, such as MP3, MP4, AAC, H.264, etc.

### codec2
Pass the `--enable-libcodec2` option to the configure script. Use the `libcodec2` library to enable support for Codec2 - a voice compression codec aiming towards very low bandwiths, both for muxing and demuxing.

This flag can be safely disabled, because Codec2 is quite rare.

### cpudetection
Pass the `--enable-runtime-cpudetect` option to the configure script. Provide an ability to automatically detect and utilize CPU capabilities at runtime. This allows to run optimized multimedia processing code on different processors using the same set of binaries and libraries. This increases the resulting binary sizes.

This flag should be enabled if there is a need to run the same compiled binaries on systems with different CPUs.

### cuda
Pass the `--enable-cuda-llvm` option to the configure script. Enabling CUDA adds support for video decoding via `cuvid`, as well as zero-copy transcoding from `cuvid` to `nvenc`. LLVM (clang) will be used for CUDA code compilation.

This flag should only be enable if the target system uses modern Nvidia GPU and there is a need to use CUDA with FFMPEG.

### dav1d
Pass the `--enable-libdav1d` option to the configure script. Enable support for decoding AV1 video format using the VideoLAN's `dav1d` library, which is very small and very fast.

It is safe to disable the flag.

### debug
Pass the `--enable-debug` option to the configure script. Build and install binaries and libraries with debugging symbols.

This flag should only ever be enabled for debugging purposes.

### doc
Pass the `--enable-doc` and `--enable-htmlpages` options to the configure script. Generate additional documentation in the HTML format and install into the `/usr/share/doc/ffmpeg-<VERSION>/html` directory, including description of codecs and formats, developer manual, available utils documentation and so on.

It is safe to disable the flag.

### encode
Enable media encoders, including ones that are controlled by various flags, e.g. `amrenc`, `mp3`, `openh264`, etc. When disabled, pass the `--disable-encoders` option to the configure script to completely disable encoding support, including any native encoders provided by the FFmpeg itself.

This flag should be enabled if there is a need to perform media encoding, e.g. converting between different formats.

### fdk
Pass the `--enable-libfdk-aac` option to the configure script, and if enabled together with the `gpl` flag also pass the `--enable-nonfree` option. Use the `libfdk_aac` library - the Fraunhofer FDK AAC codec library, which is the highest-quality AAC encoder available with ffmpeg. This library, however, has license incompatibilities with GPL and therefore binary package can't be redistributed if this flag is enabled.

This flag should be enabled if there is a need to encode AAC audio and redistribution of the binaries is not a concern.

### flite
Pass the `--enable-libflite` option to the configure script. Use the `libflite` text to speech engine to synthesize a voice utterance. Allow to read a text file, and synthesize the text using the standard flite voice, or read the text specified via the command line option. Also provide an ability to read a text using the `ffplay` tool.

It is safe to disable the flag if there is no need for the text-to-speech reading.

### fontconfig
Pass the `--enable-libfontconfig` option to the configure script. Use the `libfontconfig` library to enable default font fallback and the font options when drawing a text string or text from a specified file on top of a video, using the `drawtext` video filter.

This flag can be safely disabled, unless there is a need for font configuration for burning text subtitles.

### frei0r
Requires the `gpl` flag to be enabled due to licensing restrictions. Pass the `--enable-frei0r` option to the configure script. Use the `frei0r` library to provide an ability to apply various video effects to the video stream, e.g. vertigo, vignette, sobel, pixelizor and other effects. Enable support for the `frei0r` value of the `-vf` runtime option to apply these filters.

It is safe to disable the flag if there is no need to apply various effects to the video stream.

### fribidi
Pass the `--enable-libfribidi` option to the configure script. Use the `libfribidi` library to improve text rendering using the `drawtext` video filter. Enabled support for the runtime `text_shaping` option (e.g. reverse the order of right-to-left text or join Arabic characters).

This flag can be safely disabled, if there is no need to burn subtitles that require shaping.

### gcrypt
Only works when the `gmp` flag is disabled. Pass the `--enable-gcrypt` option to the configure script. Use the `libgcrypt` library to perform Diffie-Hellmann computation, required for the RTMPE (Encrypted Real-Time Messaging Protocol) and RTMPTE (Tunnelled RTMPE, aka RTMP over HTTP) streaming.

It is safe to disable the flag if the `gmp`, `openssl` or `librtmp` flags are enabled or there is no need to access streams over the RTMP(T)E protocol.

### gme
Pass the `--enable-libgme` option to the configure script. Use the `libgme` library to provide an ability to play music files from a number of vintage consoles and computer systems, including ZX Spectrum/Amstrad CPC, Nintendo Game Boy, Sega Genesis/Mega Drive and others.

This flag can be safely disabled.

### gmp
Pass the `--enable-version3` and `--enable-gmp` options to the configure script. Use the `libgmp` library to perform Diffie-Hellmann computation, required for the RTMPE (Encrypted Real-Time Messaging Protocol) and RTMPTE (Tunnelled RTMPE, aka RTMP over HTTP) streaming.

It is safe to disable the flag if the `gcrypt`, `openssl` or `librtmp` flags are enabled or there is no need to access streams over the RTMP(T)E protocol.

### gnutls
Pass the `--enable-gnutls` option to the configure script. Use the `libgnutls` library to handle encryption to provide an ability to stream media over the HTTPS protocol. Note: plain HTTP (unencrypted) connections will still work just fine if the flag is disabled.

This flag can be safely disable if the `openssl` flag is enabled or there is no need to access HTTPS streams.

### gpl
Pass the `--enable-gpl` option to the configure script. Allow to use the code licensed under the GPL license. The resulting libraries and binaries will be under the GPL restrictions.

This flag should be disabled if there is a need to use FFmpeg libraries for software with an incompatible license.

### gsm
Pass the `--enable-libgsm` option to the configure script. Use the `libgsm` decoder library that allows libavcodec to decode the GSM full rate audio codec. Да supports both the ordinary GSM and the Microsoft variant.

This flag can be safely disabled, unless there is a need to playback GSM audio.

### hardcoded-tables
Pass the `--enable-hardcoded-tables` option to the configure script. Use hardcoded codec tables that are provided at compile time, instead of generating them during the codec initialization at runtime. This will increase the size of the `libavcodec` library by approximately 15% and will save approximately ~100k CPU cycles at runtime.

It is recommended to disable this flag, because performance gain is negligible compared to encoding/decoding operation, and FFmpeg team constantly improves runtime initialization, and so this optimization has less and less impact.

### iconv
Pass the `--enable-iconv` option to the configure script. Use the `libiconv` library to perform character encoding conversion from any input character set into UTF-8 to properly display special characters. Enable support for the `-sub_charenc` runtime option to specify subtitle file charset.

This flag can be safely disabled if there is no need to handle non-UTF-8 subtitle files.

### iec61883
Pass the `--enable-libiec61883` option to the configure script. Use the `libiec61883` library to access FireWire DV/HDV input devices. Provide the `iec61883` capture device that supports capturing from a video device connected via IEEE1394 (FireWire) using the new Linux FireWire stack (aka juju), which is the default DV/HDV input method in modern Kernels.

The flag should be enabled if there is a need to access FireWire devices.

### ieee1394
Pass the `--enable-libdc1394` option to the configure script. Use the `libdc1394` and `libraw1394` libraries to provide the `IIDC1394` input device. Provide an ability to control and capture streams from IEEE-1394 based cameras that conform to the 1394-based Digital Camera Specifications (also known as the IIDC or DCAM Specifications). It also supports some USB cameras that are IIDC compliant.

This flag should only be enabled if there is a need to access IIDC/DCAM cameras.

### jack
Pass the `--enable-libjack` option to the configure script. Use the `libjack` library to provide the `JACK` input device that creates one or more JACK writable clients (one for each audio channel) that will send the acquired data to the FFmpeg input device. These clients can be used to connect JACK readable clients via usual means, for example using the `jack_connect` and `jack_disconnect` programs. When disabled, pass the `--disable-indev=jack` option to the configure script.

It is recommended to enable this flag only if there is a need to use the FFmpeg library with the JACK audio system.

### jpeg2k
Pass the `--enable-libopenjpeg` option to the configure script. Enable support for encoding and decoding Motion JPEG2000 (aka MJ2 or MJP2) video format, using the `libopenjpeg` library instead of the built-in experimental implementation with limited capabilities.

This flag should only be enabled if there is a need to deal with JPEG2000 videos.

### kvazaar
Only works when the `encode` flag is enabled. Pass the `--enable-libkvazaar` option to the configure script. Use the `libkvazaar` library to provide an ability to perform encoding in the HEVC (High Efficiency Video Coding) compressed video format, also known as H.265.

It is safe to disable the flag if there is no need to encode video in the HEVC format.

### ladspa
Pass the `--enable-ladspa` option to the configure script. Provide an ability to use LADSPA (Linux Audio Developer's Simple Plugin API) based plugins to apply audio filters and audio signal processing effects.

This flag should normally be disabled, unless there is a need to use LADSPA plugins.

### libaom
Pass the `--enable-libaom` option to the configure script. Use the `libaom` library - an AOMedia video encoder for the AV1 video codec. `libaom` can save about 30% bitrate compared to VP9 and H.265 / HEVC, and about 50% over H.264, while retaining the same visual quality.

This flag should be enabled if there is a need to create AV1 videos.

### libaribb24
Pass the `--enable-libaribb24` option to the configure script. Enable support for decoding ARIB STD-B24 (The Association of Radio Industries and Businesses STD-B24) subtitles using the `aribb24` library.

This flag can be safely disabled and is only useful for Japanese-language broadcasting with ARIB STD-B24 subtitles.

### libass
Pass the `--enable-libass` option to the configure script. Provide an ability to burn subtitles (draw subtitles on top of input video, aka hardsubs) using the `libass` library. Enable two additional filters: `subtitles` - a full featured subtitle drawing one, and `ass` - a filter that only supports ASS (Advanced Substation Alpha) subtitles files.

It is safe to disable the flag if there is no need to burn subtitles.

### libcaca
Pass the `--enable-libcaca` option to the configure script. Use the `libcaca` library to enable the `CACA` output device. This device provides an ability to convert frames of a video to a text approximation of the image, then write the text to a screen via stdout. The output can be accessed via the `caca` value of the `-f` option.

This flag should normally be disabled.

### libdrm
Pass the `--enable-libdrm` option to the configure script. Use the `libdrm` library to provide an ability to perform screen recording by encoding KMS scanout planes, allowing to capture both graphical and virtual terminal output, including Wayland, and allow to pass decoded frames directly to a DRM plane, to avoid unnecessary object copying for supported platforms.

This flag should be enabled on supported platforms that benefit from DRM hardware acceleration, including ARM Mali and RockChip, or if there is a need to use the `kmsgrab` input device for screen capturing.

### libilbc
Pass the `--enable-libilbc` option to the configure script. Use the `libilbc` library to allow to decode the Internet Low Bitrate Codec (iLBC) audio codec - a free narrowband voice codec that was developed by Global IP Solutions, and is used in many Voice over IP (VoIP) and streaming audio applications.

It is safe to disable the flag unless there is a need to use software that requires iLBC decoding using the FFmpeg library.

### librtmp
Pass the `--enable-librtmp` option to the configure script. Use the `librtmp` library to provide support for the Real-Time Messaging Protocol (RTMP) and its variants. Provides most client functions and a few server functions needed to support RTMP, RTMP tunneled in HTTP (RTMPT), encrypted RTMP (RTMPE), RTMP over SSL/TLS (RTMPS) and tunneled variants of these encrypted types (RTMPTE, RTMPTS). Enabling this flag will replace the native RTMP protocol implementation.

This flag should be enabled if there is a need to stream any RTMP protocol variations through FFmpeg library.

### libsoxr
Pass the `--enable-libsoxr` option to the configure script. Provide support for high-quality audio resampling using the `libsoxr` - a SoX Resampler library. To invoke FFmpeg with the SoX Resampler, the option `-af aresample=resampler=soxr` should be given.

It is safe to disable the flag, unless there is a need to perform audio resampling, in which case it is recommended.

### libtesseract
Pass the `--enable-libtesseract` option to the configure script. Enable support for OCR (Optical Character Recognition) filter that allows extracting text out of video (or image) frames.

This flag should normally be disabled.

### libv4l
Requires the `v4l` flag to be enabled. Pass the `--enable-libv4l2` option to the configure script. Build the FFmpeg library with v4l-utils support. Provide an ability to use the `libv4l2` userspace library to add support for a wider range of the video capture devices. Enable the `-use_libv4l2` runtime option to use this library.

This flag should be enabled if it is desired to use the userspace `libv4l2` library, instead of direct kernel calls.

### libxml2
Pass the `--enable-libxml2` option to the configure script. Use the `libxml2` library to support the XML parsing, necessary for demuxing DASH (Dynamic Adaptive Streaming over HTTP) content,  an adaptive bitrate streaming technique that enables high quality streaming of media content that works by breaking the content into a sequence of small HTTP-based file segments.

This flag can be safely disabled, unless there is a need to grab DASH streams, such as live broadcasts, movies, etc.

### lv2
Pass the `--enable-lv2` option to the configure script. Enable support for the LV2 (LADSPA Version 2) plugins, providing an ability to load any LADSPA (Linux Audio Developer's Simple Plugin API) v2 plugin at runtime using the `lv2` command-line option.

This flag should normally be disabled, unless there is a need to load and use LV2 plugins.

### lzma
Pass the `--enable-lzma` option to the configure script. Use the `liblzma` library to provide the LZMA compression support in the TIFF decoder. This can be useful when converting a sequence of TIFF images into a video file and source images are LZMA-compressed.

It is safe to disable the flag.

### mipsdspr1
Pass the `--enable-mipsdsp` option to the configure script. Use the assembly code that utilizes the MIPS DSP ASE (revision 1) optimization extension on the supported platforms to accelerate a large range of audio and video computations.

It is highly recommended to enable this flag on supported MIPS platforms, otherwise it is completely safe to disable.

### mipsdspr2
Pass the `--enable-mipsdspr2` option to the configure script. Use the assembly code that utilizes the MIPS DSP ASE (revision 2) optimization extension on the supported platforms to accelerate a large range of audio and video computations. Revision 2 of the ASE was introduced in the second half of 2006, adds extra instructions to the original ASE, and is otherwise backwards-compatible with it.

It is highly recommended to enable this flag on supported MIPS platforms, otherwise it is completely safe to disable.

### mipsfpu
Pass the `--enable-mipsfpu` option to the configure script. Enable the assembler code that can utilize the MIPS Floating Point instructions to perform floating point operations using hardware acceleration (instead of software emulation) when performing media encoding and decoding with floating point codecs.

This flag is recommended for MIPS platforms with the FPU coprocessor, and otherwise can be safely disabled.

### mmal
Pass the `--enable-mmal` option to the configure script. Enable Broadcom Multi-Media Abstraction Layer (MMAL) for hardware decoding of the H.264, VC-1, MPEG-2, MPEG-4 codecs on supported Broadcom CPUs, e.g. on the Raspberry Pi platform.

It is recommended to enable the flag on supported Broadcom platforms, and can otherwise be safely disabled.

### modplug
Pass the `--enable-libmodplug` option to the configure script. Use the `libmodplug` library to provide an ability to play Module Files, originating from the MOD file format on Amiga systems used in the late 1980s.

This flag can be safely disabled.

### mp3
Requires the `encode` flag to be enabled. Pass the `--enable-libmp3lame` option to the configure script. Use the `libmp3lame` encoding library to create MP3 audio files (since FFmpeg has no native MP3 encoder). It supports VBR, CBR and ABR encodings.

This flag should be enabled to support MP3 encoding.

### network
Pass the `--enable-network` option to the configure script. Enable support for network media streaming. Provide a wide range of network protocols, such as TCP, UDP, HTTP, RTSP, MMS and others. Also enable additional capabilities, e.g. name to IP resolution for SDP, an option to set buffer size for the `librtmp` streaming library.

This flag should be enabled to support networking features.

### openal
Pass the `--enable-openal` option to the configure script. Enable the OpenAL input device, that provides an ability to capture audio stream on all systems with a working OpenAL 1.1 implementation.

This flag can be safely disabled, unless there is a need to perform audio capturing using the OpenAL API.

### opencl
Pass the `--enable-opencl` option to the configure script. Enable OpenCL-based filters that utilize the OpenCL API in order to offload more operations to the GPU, making the CPU less busy. The OpenCL implementation can also interoperate with other GPU APIs to avoid redundant copies between GPU and CPU memory, further improving the performance, however this requires a combination of supported GPU and video processing API.

This flag can be enabled on platforms with compatible GPUs, however CPU-based OpenCL implementations might be slower than using native FFmpeg filters directly.

### opengl
Pass the `--enable-opengl` option to the configure script. Enable support for the OpenGL output device that allows to render to an OpenGL context, that may be provided by an application, and when the `sdl` flag is enabled, then SDL window can be created by the FFmpeg itself.

The flag should be enabled if there is a need to output to an OpenGL context.

### openh264
Only works when the `encode` flag is enabled. Pass the `--enable-libopenh264` option to the configure script. Use the Cisco's `libopenh264` library to support H.264/MPEG-4 AVC video encoding. This encoder supports Constant Rate Factor (CRF), Two-Pass ABR and Lossless H.264 modes, and additionally Constant Bit Rate (CBR), constrained encoding (VBV, aka maximum bit rate) and Low Latency modes can be simulated by tweaking parameters.

This flag should be enabled if there is a need to perform H.264 video encoding, primarily oriented for web streaming, however the `x264` flag might be a better option for general purpose, as it relies on older library with more features.

### openssl
Pass the `--enable-openssl` option to the configure script, and if the `gpl` flag is also enabled, additionally pass the `--enable-nonfree` option. Use the OpenSSL library to perform Diffie-Hellmann computation, required for the RTMPE (Encrypted Real-Time Messaging Protocol) and RTMPTE (Tunnelled RTMPE, aka RTMP over HTTP) streaming and for encryption handling for the HTTPS protocol.

It is safe to disable the flag if there is no need to handle the HTTPS or RTMP(T)E protocols, or if alternative implementations are enabled, via the `gmp`, `gcrypt`, `librtmp` or `gnutls` flags.

### opus
Pass the `--enable-libopus` option to the configure script. Use the `libopus` library to provide an ability to perform encoding and decoding audio data using the Opus Interactive Audio Codec.

This flag should be enabled to support the OPUS audio format.

### oss
Enable the `oss` input and output devices to allow audio capture and playback via the Open Sound System (OSS) Linux API. When disabled, pass the `--disable-indev=oss` and `--disable-outdev=oss` options to the configure script to disable these devices.

This flag should normally be disabled as OSS is deprecated by the kernel authors.

### pic
Pass the `--enable-pic` and the `--disable-asm` options to the configure script. Enable position-independent code (PIC) when building libraries and binaries. Disable all assembly optimization code (because it is incompatible with PIC).

It is recommended to enable this flag to improve security, e.g. on hardened systems.

### postproc
Requires the `gpl` flag to be enabled due to license restrictions. Pass the `--enable-postproc` option to the configure script. Enable support for additional postprocessing filters via the `libpostproc` library, such as `hdeblock` - a horizontal deblocking filter, `dering` - a deringing filter, `linblenddeint` - a linear blend deinterlacer and others.

This flag should be enabled if there is a need to use postprocessing filters and must be disabled if FFmpeg to be used with non-GPL compatible software.

### pulseaudio
Pass the `--enable-libpulse` option to the configure script. Enable the `pulse` input device to capture audio through hardware devices connected to the PulseAudio server, as well as the output devices to perform playback.

This flag should be enabled if the target system uses the PulseAudio sound server.

### rav1e
Only works when the `encode` flag is enabled. Pass the `--enable-librav1e` option to the configure script. Provide an ability to create (encode) files in the AV1 format using the `librav1e` library - the fastest and safest AV1 encoder that is suitable for cases where the reference encoder library (`libaom`) is too slow.

This flag can be safely disabled.

### rubberband
Pass the `--enable-librubberband` option to the configure script. Enable the `rubberband` audio filter that uses the `librubberband` library to allow to change the tempo and pitch of an audio recording independently of one another.

It is safe to disable the flag, unless the `ruberband` filter is required.

### samba
Requires the `gpl` flag to be enabled due to licensing restrictions. Pass the `--enable-libsmbclient` and `--enable-version3` options to the configure script. Use the `libsmbclient` library to provide an ability to access media files on the SMB and CIFS network resources via the `smb://` protocol.

This flag can be safely disabled, unless there is a need to access Samba shares.

### schroedinger
Pass the `--enable-libschroedinger` option to the configure script. Provide an ability to encode and decode the Dirac video compression format using the `libschroedinger` library.

It is safe to disable the flag if there is no need to handle Dirac videos.

### sdl
Pass the `--enable-ffplay` and `--enable-sdl2` options to the configure script. When disabled, pass the `--disable-outdev=sdl` option to the configure script. Build and install the `ffplay` media player. Also build the SDL (Simple DirectMedia Layer) output device that allows to show a video stream in an SDL window.

This flag should be enabled if there is a need for the `ffplay` player or an `sdl` output device.

### snappy
Only works when the `encode` flag is enabled. Pass the `--enable-libsnappy` option to the configure. Use the `libsnappy` compression library to provide an ability to encode video using the HAP family of video codecs, which perform decompression using a computer's graphics hardware.

The flag can be safely disabled, unless there is a need to encode videos using the HAP format.

### sndio
Provide an ability to capture and playback audio via the sndio audio and MIDI framework and enable support for the `sndio` value of the `-f` runtime option. When disabled, pass the `--disable-indev=sndio` and `--disable-outdev=sndio` options to the configure script to disable sndio support.

This flag should normally be disabled, because sndio has originated from UNIX and there are other ways to access audio hardware on Linux systems.

### speex
Pass the `--enable-libspeex` option to the configure script. Use the `libspeex` library to enable encoding and decoding audio in the Speex format - patent-free audio compression format designed for speech, which is commonly used for VoIP applications, speech recorders, FLV files, etc. The SRT encrypts video streams, recovers from severe packet loss and dynamically adapts to changing network conditions.

This flag should be enabled if there is a need to encode or play speex audio.

### srt
Pass the `--enable-libsrt` option to the configure script. Use the `libsrt` library to enable support for the (Secure Reliable Transport) - a UDP-based open source transport techonology that optimizes streaming performance across unpredictable networks.

The flag can be safely disabled, unless there is a need to access SRT streams.

### ssh
Pass the `--enable-libssh` option to the configure script. Use the `libssh` library to enable support for the SFTP (SSH File Transfer Protocol) protocol and allow to read from or write to remote resources.

It is safe to disable the flag, unless there is a need to access files over the SFTP protocol.

### static-libs
Pass the `--enable-static` option to the configure script. Build and install a statically linked version of the `libavcodec`, `libpostproc`, `libavdevice` and other libraries.

This flag should only be enabled if there is an explicit need for the static libraries.

### svg
Pass the `--enable-librsvg` option to the configure script. Use the `librsvg` library to provide support for the SVG image rasterization, i.e. converting from vectorized to rasterized image format.

This flag can be safely disabled, and is not normally necessary.

### test
Configure the `LD_LIBRARY_PATH` environment variable and execute the `make fate` command when the main build is completed. Run the regression test suite provided with the source code. This will extend the build time.

This flag should normally be disabled as it is primarily useful for the Gentoo team, testers and developers.

### theora
Only works when the `encode` flag is enabled. Pass the `--enable-libtheora` option to the configure script. Provide an ability to create files in the Theora video format using the `libtheora` library.

This flag should only be enabled if there is a need to perform Theora encoding, because modern alternatives like VP9 can provide better quality (see the `vpx` flag).

### threads
Pass the `--enable-pthreads` option to the configure script. Use the `libpthread` library to perform speed-up encoding by utilizing multiple threads. When disabled, the following message will be displayed at runtime:
> Warning: not compiled with thread support, using thread emulation

It is recommended to enable this flag on any modern multi-core system.

### truetype
Pass the `--enable-libfreetype` option to the configure script. Enable the `drawtext` filter that uses the `libfreetype` library to draw a text string or text from a specified file on top of a video, usually used for burning subtitles (aka hardsubs). Also see the `fribidi` and `fontconfig` flags that improve this filter.

It is safe to disable the flag, unless there is a need for the `drawtext` filter.

### twolame
Requires the `encode` flag to be enabled. Pass the `--enable-libtwolame` option to the configure script. Use the `libtwolame` library to provide an ability to encode audio in the MP2 (aka MPEG-1 Audio Layer II or MPEG-2 Audio Layer II) lossy compression format defined by the ISO/IEC 11172-3 standard.

The flag can be safely disabled, unless there is a specific need to encode audio in the MP2 format.

### v4l
When disabled, pass the `--disable-indev=v4l2` and `--disable-outdev=v4l2` options to the configure script. Enable support for the Video4Linux2 input and output video devices, that can be accessed via the `v4l2` option (or `video4linux2` alias). The input device is used to grab a video input from a the video device, such as a USB webcamera. The output device is used to produce a video stream in the Video 4 Linux format and can help to emulate capturing devices, e.g. via the `v4l2loopback` kernel module.

This flag should only be enabled if there is a need to capture video from Video 4 Linux devices or create a stream compatible with this format.

### vaapi
Pass the `--enable-vaapi` option to the configure script. Use the `libVA` library to enable support for the VA-API (Video Acceleration API). The API provides an ability to use a GPU to accelerate video encoding and decoding to offload processing from the CPU. VA-API is supported by Intel GPUs (via QuickSync), ATI/AMD GPUs (via UVD/VCE) and NVIDIA GPUs (with Nouveau driver only). Depending on hardware, it supports a wide range of different formats, including H.264, MPEG-2, MPEG-4, VC-1, H.265 and others.

It is highly recommended to enable this flag to accelerate video processing on supported platforms.

### vdpau
Pass the `--enable-vdpau` option to the configure script. Use the `libvdpau` library to enable support for VDPAU (​Video Decode and Presentation API for Unix), that is used for accelerated decoding, post-processing, compositing, and displaying compressed or uncompressed video streams on NVIDIA and ATI/AMD GPUs. Note: VDPAU is not suitable for encoding, is not updated since 2015, requires special code in the application to use it, and has support for only a limited number of the formats: H.264, MPEG-1/2/4, and VC-1.

This flag should be enabled on systems with old NVIDIA GPUs, and for newer cards `cuda` should be used instead.

### vidstab
Pass the `--enable-libvidstab` option to the configure script. Use the `vid.stab` library to enable support for the `vidstabdetect` video filter to analyze shaky and unstable videos and apply compensatory transformations using the `vidstabtransform` video stabilization filter.

It is safe to disable this flag if there is no need to perform video stabilization.

### vorbis
Pass the `--enable-libvorbis` option to the configure script. Use the external `libvorbis` library for encoding and decoding audio in the Vorbis format, instead of built-in experimental implementation. This will produce much higher quality when encoding.

It is recommended to enable this flag if there is a need to encode or decode the Vorbis audio format.

### vpx
Pass the `--enable-libvpx` option to the configure script. Use the `libvpx` library to enable support for decoding and encoding VP8 and VP9 video compression formats. Provides two video codecs - `libvpx` and `libvpx-v9` for VP8 and VP9 formats respectively.

This flag should be enabled if there is a need to create WebM media format.

### vulkan
Pass the `--enable-vulkan` option to the configure script. Enable support for Vulkan API to offload video processing to the GPU and also enable support for AMD AMF (Advanced Media Framework)/VCE (Video Coding Engine) encoder.

This flag should be enabled on systems that have compatible AMD GPU to enable hardware-accelerated decoding.

### webp
Requires the `encode` flag to be enabled. Pass the `--enable-libwebp` option to the configure script. Use the `libwebp` library to provide an ability to encode images in WebP format, create animated WebP sequences, including converting any supported video format into a WebP animation and extracting video frames in the WebP format.

This flag should only be enabled if there is a need to create WebP images or animations.

### X
Pass the `--enable-xlib`, `--enable-libxcb`, `--enable-libxcb-shm` and `--enable-libxcb-xfixes` options to the configure script. Provide support for video playback and capturing within X11 server. Enable the X11 video input device (aka `x11grab`) that uses the `libX11`, `libXext` and `libXfixes` libraries to allow to capture a region of an X11 display. Enable the XVideo output device (`xv` runtime option) that uses the `libXv` library to allow to play a video stream in an X Server window.

It is safe to disable the flag.

### x264
Requires the `gpl` flag to be enabled due to the licensing restrictions and only works if the `encode` flag is enabled. Pass the `--enable-libx264` option to the configure script. Use the `libx264` library to provide an ability to encode videos in the H.264 (aka MPEG-4 Part 10 or MPEG-4 AVC) format.

This flag should be enabled to support H.264 encoding, however it is recommended to use its successor, the H.265 codec (see the `x265` flag) instead if the target media permits.

### x265
Only works when the `encode` flag is enabled and requires the `gpl` flag to be enabled due to the licensing restrictions. Pass the `--enable-libx265` option to the configure script. Use the `libx265` library to provide an ability to perform video encoding in the HEVC (High Efficiency Video Coding, aka H.265 or MPEG-H Part 2) format.

It is recommended to enable this flag to perform high-quality video encoding, however not all the devices, especially older ones, are able to play it yet, let alone hardware acceleration.

This flag should be enabled if there is a need to perform screen recording.

### xvid
Requires the `gpl` flag to be enabled due to the licensing restrictions and only works if the `encode` flag is enabled. Pass the `--enable-libxvid` option to the configure script. Use the `libxvid` library to provide an ability to encode video in the Xvid (aka DivX, MPEG-4 or MPEG-4 Part 2) format, that was widely used befor adoption of H.264.

This flag should normally be disabled, unless there is a specific need to perform MPEG-4 encoding, and modern alternatives, such as H.264 (`x264` flag), HEVC (`x265` flag), or VP8/VP9 (`vpx` flag) should be used instead.

### zeromq
Pass the `--enable-libzmq` option to the configure script. Provide an ability to receive commands sent through a `libzmq` client, and forward them to active filters. This allows to change filter options on-the-fly while FFmpeg is running and even do so over the network. Provides two pass-through filters: `zmq` for video formats and `azmq` for audio.

This flag should normally be disabled.

### zimg
Pass the `--enable-libzimg` option to the configure script. Enable the `zscale` video filter that allows to scale (resize) the input video, using the `libzimg` library. If the input image format is different from the format requested by the next filter, the zscale filter will convert the input to the requested format.

This flag should be enabled if there is a need to perform video scaling with the `zscale` filter.

### zlib
Pass the `--enable-zlib` option to the configure script. This flag is required by the `cws2fws` tool. Enable support for the DEFLATE compression on various stream formats, such as Matroska.

It is recommended to enable this flag, unless there is absolutely no need to access Zlib compressed media.

### zvbi
Pass the `--enable-zvbi` option to the configure script. Use the `libzvbi` library to provide an ability to decode DVB teletext pages and DVB teletext subtitles.

It is safe to disable the flag, unless there is a need to support DVB teletext.
