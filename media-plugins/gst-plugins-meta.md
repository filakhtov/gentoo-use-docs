# media-plugins/gst-plugins-meta

### a52
Pull in the [media-plugins/gst-plugins-a52dec](../media-plugins/gst-plugins-a52dec.md) package as a dependency to provide the `libgsta52dec` library from the `gst-plugins-ugly` upstream package that can be used to decode ATSC A/52 (aka AC-3) audio streams.

It is safe to disable the flag, if there is no need to decode A/52 audio that is used for digital television, DVDs, etc.

### aac
Pull in the [media-plugins/gst-plugins-faad](../media-plugins/gst-plugins-faad.md) package as a dependency to provide the `libgstfaad` library from the `gst-plugins-bad` upstream package that can be used to decode AAC audio through the FAAD (Free MPEG-2/4 AAC Decoder) library.

This flag should be enabled to provide AAC playback abilities.

### alsa
Ensure that the `alsa` flag is enabled for the [media-libs/gst-plugins-base](../media-libs/gst-plugins-base.md) package as a dependency to provide the `libgstalsa` ALSA plugin library from the `gst-plugins-base` upstream package that can used to capture and playback sounds through the ALSA subsystem and also provides an access to ALSA MIDI sequencer events.

This flag should be enabled if there is a need to play and capture audio through the ALSA subsystem, or access a MIDI sequencer.

### cdda
Pull in two additional dependencies: the [media-plugins/gst-plugins-cdparanoia](../media-plugins/gst-plugins-cdparanoia.md) package to provide the `libgstcdparanoia` library from the `gst-plugins-base` upstream package and the [media-plugins/gst-plugins-cdio](../media-plugins/gst-plugins-cdio.md) package to provide the `libgstcdio` library from the `gst-plugins-ugly` upstream package that are necessary to play Audio CDs.

It is safe to disable the flag as long as there is no need to play Audio discs.

### dts
Pull in the [media-plugins/gst-plugins-dts](../media-plugins/gst-plugins-dts.md) package as a dependency to provide the `libgstdtsdec` library from the `gst-plugins-bad` upstream package that can be used to decode DTS (DTS Coherent Acoustics) audio streams.

This flag should be enabled to support DTS audio playback, that is often used for storing surround sound on LaserDisc, DVD, BluRay media, Matroska movies, etc.

### dv
Pull in the [media-plugins/gst-plugins-dv](../media-plugins/gst-plugins-dv.md) package as a dependency to provide the `libgstdv` library from the `gst-plugins-good` upstream package that can be used to play DV (Digital Video) videos using the `libdv` library.

It is safe to disable the flag, unless there is a need to support DV video playback, that is used by most digital camera recorders, typically ones that support the IEEE-1394 (aka FireWire or i.Link) interface.

### dvb
Pull in the [media-libs/gst-plugins-bad](../media-libs/gst-plugins-bad.md) package and the [media-plugins/gst-plugins-dvb](../media-plugins/gst-plugins-dvb.md) package as dependencies to provide the `libgstdvb` library from the `gst-plugins-bad` upstream package that can be used to capture media from DVB cards and supports multiple DTV broadcasting standards, i.e. DVB-T/C/S, ATSC, ISDB-T and DTMB.

This flag should be enabled if there is a need to watch digital television through GStreamer framework.

### dvd
Pull in the following packages as dependencies:

- [media-libs/gst-plugins-ugly](../media-libs/gst-plugins-ugly.md);
- [media-plugins/gst-plugins-a52dec](../media-plugins/gst-plugins-a52dec.md) to provide the `libgsta52dec` ATSC A/52 audio decoder library;
- [media-plugins/gst-plugins-dvdread](../media-plugins/gst-plugins-dvdread.md) to provide the `libgstdvdread` library to access DVD title/chapter/angle using the `libdvdread` library;
- [media-plugins/gst-plugins-mpeg2dec](../media-plugins/gst-plugins-mpeg2dec.md) to provide the `libgstmpeg2dec` library that can decode MPEG video streams using the `libmpeg2` library;
- [media-plugins/gst-plugins-resindvd](../media-plugins/gst-plugins-resindvd.md) to provide the `libgstresindvd` library that provides DVD playback elements;

from the upstream `media-libs/gst-plugins-ugly` package to enable DVD discs playback capabilities.

This flag can be disabled if there is no need to play DVD media.

### ffmpeg
Pull in the [media-plugins/gst-plugins-libav](../media-plugins/gst-plugins-libav.md) package as a dependency to provide the `libgstlibav` library, that acts as a wrapper on top of the `libav` libraries from the FFmpeg framework and can perform encoding and decoding of a wide variety of the multimedia formats, including AAC, AC3, AMR, MPEG-4, VP6/VP7/VP8/VP9, WebP, WMA, WMV, and many more.

This flag should be enabled if there is a need to use the FFmpeg framework for decoding various media formats.

### flac
Pull in the [media-plugins/gst-plugins-flac](../media-plugins/gst-plugins-flac.md) package as a dependency to provide the `libgstflac` library from the `gst-plugins-good` upstream package, that can be used to encode and decode FLAC (Free Lossless Audio Codec) lossless audio streams and manipulate FLAC tags.

This flag should be enabled if there is a need to work with FLAC audio streams.

### http
Pull in the [media-plugins/gst-plugins-soup](../media-plugins/gst-plugins-soup.md) package as a dependency to provide the `libgstsoup` library from the `gst-plugins-good` upstream package, that can be used to receive and send multimedia streams over the HTTP protocol.

This flag should be enabled if there is a need to access HTTP media streams, for example HLS.

### jack
Pull in the [media-plugins/gst-plugins-jack](../media-plugins/gst-plugins-jack.md) package as a dependency to provide the `libgstjack` library from the `gst-plugins-good` upstream package, that can be used to capture audio from and play it through the JACK (JACK Audio Connection Kit) server.

This flag should only be enabled if there is a need to use GStreamer framework with the JACK audio server, which is normally used in professional environments.

### lame
Pull in the [media-plugins/gst-plugins-lame](../media-plugins/gst-plugins-lame.md) package as a dependency to provide the `libgstlame` library from the `gst-plugins-good` upstream package that can be used to perform high-quality MP3 audio encoding.

This flag should only be enabled if there is a need to create MP3 files.

### libass
Pull in the [media-plugins/gst-plugins-assrender](../media-plugins/gst-plugins-assrender.md) package as a dependency to provide the `libgstassrender` library from the `gst-plugins-bad` upstream package, that can be used to renders ASS (Advanced SubStation Alpha) and SSA (Sub Station Alpha) subtitles with the `libass` library.

It is safe to disable the flag.

### libvisual
Pull in the [media-plugins/gst-plugins-libvisual](../media-plugins/gst-plugins-libvisual.md) package as a dependency to provide the `libgstlibvisual` library from the `gst-plugins-base` upstream package, that can be used to create visualizations, such as jakdaw, jess, oinksie and others.

This flag should be enabled if there is a need to render music visualizations.

### modplug
Pull in the [media-libs/gst-plugins-ugly](../media-libs/gst-plugins-ugly.md) and [media-plugins/gst-plugins-modplug](../media-plugins/gst-plugins-modplug.md) packages as dependencies to provide the `libgstmodplug` library from the `gst-plugins-bad` upstream package, that can be used to decode module audio files (.MOD) using the `libmodplug` library based on the ModPlug sound engine.

This flag can be safely disabled.

### mp3
Pull in the [media-libs/gst-plugins-ugly](../media-libs/gst-plugins-ugly.md) and [media-plugins/gst-plugins-mpg123](../media-plugins/gst-plugins-mpg123.md) packages as dependencies to provide the `libgstmpg123` library from the `gst-plugins-good` upstream package, that can be used to decodes MP3 audio streams using the `mpg123` library.

This flag should be enabled to support MP3 audio playback.

### mpeg
Pull in the [media-plugins/gst-plugins-mpeg2dec](../media-plugins/gst-plugins-mpeg2dec.md) package as a dependency to provide the `libgstmpeg2dec` library from the `gst-plugins-ugly` upstream package that can be used to decode MPEG video streams using the `libmpeg2` library.

Thi flag should be enabled to support MPEG-1 and MPEG-2 video playback.

### ogg
Make sure that the `ogg` flag is enabled on the [media-libs/gst-plugins-base](../media-libs/gst-plugins-base.md) package to provide the `libgstogg` library, that can be used to access OGG content, e.g. mux and demux OGG streams, parse OGM audio, video and text headers and streams, and so on.

This flag should be enabled to support the OGG media container for audio, video, and text (subtitles) streams.

### opus
Requires the `ogg` flag to be enabled. Pull in the [media-plugins/gst-plugins-opus](../media-plugins/gst-plugins-opus.md) package as a dependency to provide the `libgstopus` library from the `gst-plugins-base` upstream package, that can be used to encode and decode audio streams from and to the Opus format.

This flag should be enabled to support Opus audio format, primarily oriented towards music streaming and transmission over the Internet, e.g. for VoIP, video conferencing, live audio, etc.

### oss
Pull in the [media-plugins/gst-plugins-oss](../media-plugins/gst-plugins-oss.md) package as a dependency to provide the `libgstossaudio` library from the `gst-plugins-good` upstream package, that is used to enable support for the OSS (Open Sound System) system and provide an ability to capture audio from and play it back to a sound card via the OSS API.

This flag should normally be disabled, unless the target system uses OSS (which is deprecated by the Kernel maintainers).

### pulseaudio
Pull in the [media-plugins/gst-plugins-pulse](../media-plugins/gst-plugins-pulse.md) package as a dependency to provide the `libgstpulseaudio` library from the `gst-plugins-good` upstream package, that allows to play audio through and capture from the PulseAudio sound server.

This flag should be enabled if the target system runs PulseAudio as a primary sound system.

### taglib
Pull in the [media-plugins/gst-plugins-taglib](../media-plugins/gst-plugins-taglib.md) package as a dependency to provide the `libgsttaglib` library from the `gst-plugins-good` upstream package that can be used to add ID3v2 tags to MP3 files and APEv2 tags to Monekey Audio files using the `taglib` library.

This flag should be enabled if there is a need to add or edit tags through GStreamer framework (or any players that use it).

### theora
Requires the `ogg` flag to be enabled. Make sure that the `theora` flag is enabled for the [media-libs/gst-plugins-base](../media-libs/gst-plugins-base.md) package to provide the `libgsttheora` library, that can be used to parse raw Theora-encoded streams, encode raw YUV video to a Theora stream and decode it back.

This flag should be enabled to support Theora video playback.

### v4l
Pull in the [media-plugins/gst-plugins-v4l2](../media-plugins/gst-plugins-v4l2.md) package as a dependency to provide the `libgstvideo4linux2` library from the `gst-plugins-good` upstream package, that can be used to capture frames from a Video4Linux2 device, display frames on it and control a Video4Linux2 radio device.

This flag should be enabled to support multimedia devices accessible through the Video4Linux2 API.

### vaapi
Pull in the [media-plugins/gst-plugins-vaapi](../media-plugins/gst-plugins-vaapi.md) package to provide the `libgstvaapi` library, that can be used to perform hardware accelerated video decoding and post-processing through the VA-API (Video Acceleration API), including H.264, H.265, MPEG-2, VP8, etc.

This flag should be enabled on supported hardware to perform accelerated video decoding and improve performance.

### vcd
Pull in two additional dependencies: the [media-plugins/gst-plugins-mplex](../media-plugins/gst-plugins-mplex.md) package to provide the `libgstmplex` library from the `gst-plugins-bad` upstream package - a high-quality MPEG, DVD, SVCD, VCD video and audio multiplexer, and the [media-plugins/gst-plugins-mpeg2dec](../media-plugins/gst-plugins-mpeg2dec.md) package to provide the `libgstmpeg2dec` library from the `gst-plugins-ugly` upstream package - a MPEG-1 and MPEG-2 video decoder, that can be used to play VCD (Video CD, aka Compact Disc Digital Video).

This flag should be normally disabled, unless there is a need to play VCD discs.

### vorbis
Requires the `ogg` flag to be enabled. Ensure that the `vorbis` flag is enabled on the [media-libs/gst-plugins-base](../media-libs/gst-plugins-base.md) package to provide the `libgstvorbis` library, that can be used to parse raw Vorbis streams, encode float audio streams into Vorbis format, decode them back, and manipulate tags of Vorbis streams.

This flag should be enabled if there is a need to play or create Vorbis compressed audio streams.

### vpx
Pull in the [media-plugins/gst-plugins-vpx](../media-plugins/gst-plugins-vpx.md) package as a dependency to provide the `libgstvpx` library from the `gst-plugins-good` upstream package, that can be used to encode and decode VP8 and VP9 video streams.

This flag should be enabled to support creating and playing VP8 and VP9 video streams, that are popular streaming formats amongst internet streaming services, such as YouTube, Netflix and others.

### wavpack
Pull in the [media-plugins/gst-plugins-wavpack](../media-plugins/gst-plugins-wavpack.md) package as a dependency to provide the `libgstwavpack` library, that can be used encode and decode Wavpack audio data, both lossless and lossy.

This flag should be enabled if there is a need to creat and play the WavPack audio format.

### X
Ensure that the `X` flag is enabled for the [media-libs/gst-plugins-base](../media-libs/gst-plugins-base.md) package to provide the `libgstximagesink` library, that can render video frames to a drawable (XWindow) area on a local or remote display, the `libgstxvimagesink` library - a video output plugin that is using the Xv extension and the `libgstshm` library that can use shared memory to efficiently send and receive data using the X Server SHM (shared memory extension).

This flag should be enabled if the target system runs X window server.

### x264
Pull in the [media-plugins/gst-plugins-x264](../media-plugins/gst-plugins-x264.md) package as a dependency to provide the `libgstx264` library from the `gst-plugins-ugly` upstream pacakge, that can be used to encode H.264 video streams.

This flag should only be enabled if there is a need to produce H.264 videos.
