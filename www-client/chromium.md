# www-client/chromium

### component-build
Pass the `is_component_build=true` option to the `gn gen` command. Normally, one executable is compiled and a couple of shared libraries (depending on the platform), producing efficient runtime binary, but can take a long time to link because so much code goes into a single binary. This flag switches to a component build, where many smaller shared libraries will be generated. This speeds up link times, and means that many changes only require that the local shared library be linked rather than the full executable, but at the expense of program load-time performance.

This flag should normally be disabled, because component build isn't generally intended for use by end users and is mostly useful for developement and debugging.

### cups
Can't be used together with the `headless` flag. Pass the `use_cups=true` option to the `gn gen` command. Link against the `libcups` library to enable printing support using CUPS (Common Unix Printing System), including both, remote and local printers.

It is safe to disable the flag.

### custom-cflags
Normally, a number of different options are removed from the `CFLAGS` and `CXXFLAGS` variables by the ebuild to prevent some known issues, like running out of address space when debugging flag is enabled on the x86 architecture, or remove different SIMD flags that might break the `libvpx` library build. When this flag is enabled pass flags as is without filtering anything.

It is recommended to disable this flag to avoid build issues.

### debug
Pass the `dcheck_always_on=true` and `dcheck_is_configurable=true` options to the `gn gen` command. Enable `DCHECK()` macroses that will check various conditions in the code and can be configured to be fatal, i.e. terminate the Chrome immediately if the condition is not met. This is normally used for debugging purposes and various bot configurations and is not intended for the end users.

This flag should normally be disabled for production builds.

### gtk4
Pass the `gtk_version=4` option (instead of the `3`) option to the `gn gen` command. Build against GTK+ version 4 instead of default of version 3. Even with that, Chromium still prefers GTK version 3 at runtime, so the `--gtk-version=4` flag needs to be passed as a command line option to actually use GTK version 4.

This flag should only be enabled on systems that are running GTK+ version 4 and newer.

### hangouts
Pass the `enable_hangout_services_extension=true` option to the `gn gen` command. Enable the Google Hangouts services that provide screensharing features for the Chromium browser.

It is safe to disable the flag.

### headless
Pass the `ozone_platform="headless"`, `use_xkbcommon=false`, `use_gtk=false`, `use_glib=false`, `use_gio=false`, `use_pangocairo=false`, `use_alsa=false`, `use_libpci=false`, `use_udev=false`, `enable_print_preview=false` and `enable_remoting=false` options to the `gn gen` command. Enable support for headless Ozone platform, where any graphical output will be written into a PNG image. This platform does not support hardware acceleration and performs software rendering only. This feature can be used for automation, taking web page screenshots, etc.

This flag should normally be disabled.

### js-type-check
Pass the `enable_js_type_check=true` option to the `gn gen` command. Run a closure compiler during the build to analyze JavaScript source code of Chromium and check for syntax errors, variable references and other common JavaScript mistakes. This however will require JRE (Java Runtime Environment) to be available on the build system.

This flag can be safely disabled because such analysis is normally performed by the developers, not end users.

### kerberos
Can't be used together with the `headless` flag. Pass the `use_kerberos=true` option to the `gn gen` command. Enable support for the SPNEGO authentication mechanism (Simple and Protected GSS-API Negotiation), also known as "integrated authentication" or "negotiate authentication" to provide the concept of Single Sign-On (SSO) - having authenticated once at the start of a session, users can access network services throughout a Kerberos realm without authenticating again. Enable support for the `--auth-server-whitelist` runtime option that takes as its value a comma-separated list of permitted hostnames. Also enable the `--auth-negotiate-delegate-whitelist` runtime option to allow a network service to authenticate to other network services on users behalf.

This flag should only be enabled if there is a need for Kerberos/SPNEGO authentication.

### libcxx
Pass the `use_custom_libcxx=true` option to the `gn gen` command. Use the bundled `libc++` library provided with the Chromium source, instead of using the system `libstdc++` one. This will require LLVM compiler, as the bundled library can't be built with GCC, will extend the overall build time, but will produce a more "stable" build, as the bundled library is the way official Chromium and Chrome binaries are built by the upstream.

This flag can be safely disabled.

### lto
Only works with the Clang compiler. Pass the `use_lld=true` and `use_thin_lto=true` options to the `gn gen` command. Use the `lld` linker from the LLVM project to perform linking during the build. Perform additional link time optimization to improve runtime performance.

It is safe to disable this flag.

### official
Pass the `is_official_build=true` and `is_cfi=false` options to the `gn gen` command. First flag is responsible for a set of optimization flags that are enabled by the official Chrome builds, while the second disables CFI (Control Flow Integrity) for virtual calls, indirect calls and bad casts, because it is unsupported on GCC compiler. Enabling this flag slows down the build process but should have advantages during the runtime.

It is safe to disable this flag.

### pgo
Only works with the Clang compiler. Pass the `use_lld=true` option to the `gn gen` command and perform the build twice: first time passing the `chrome_pgo_phase=1` option to the `gn gen` command to produce unoptimized version, then use profiler to determine various optimizations that can be performed, and finally perform a second build passing the `chrome_pgo_phase=2` option this time applying the determined optimizations and producing a final version. Enabling this flag will significantly increase the build time and slightly improve the runtime performance.

This flag can be safely disabled.

### pic
Only makes sense on the `ia32` architecture when `system-ffmpeg` flag is disabled. Pass the `--disable-asm` option to the `chromium/scripts/build_ffmpeg.py` script. Disable optimized assembly code and use the non-optimized but PIC-friendly (Position-Independent Code) code instead.

This flag should normally be disabled.

### proprietary-codecs
Pass the `proprietary_codecs=true` and the `ffmpeg_branding=Chrome` (instead of `Chromium`) option to the `gn gen` command. If the `system-ffmpeg` flag is disabled, also pass the `--branding Chrome` (instead of `Chromium`) option to the `chromium/scripts/build_ffmpeg.py` build script. Build the bundled FFmpeg library with support for proprietary codecs, e.g. MP3, etc, and make sure that the built Chromium exposes an ability to play these when requested.

This flag should normally be enabled to prevent various issues with media playback.

### pulseaudio
Can't be used together with the `headless` flag. Pass the `use_pulseaudio=true` option to the `gn gen` command. Enable the PulseAudio backend for Chromium to provide an ability to play sound via the PulseAudio server instead of the default ALSA (Advanced Linux Sound Architecture) system.

This flag should be enabled if the target system runs the PulseAudio sound system.

### screencast
Requires `wayland` flag to be enabled. Pass the `rtc_use_pipewire=true` option to the `gn gen` command. Use the PipeWire server to enable screen and audio capture in Chromium to allow screencast functionality on Wayland.

It is safe to disable this flag.

### selinux
Pull in the [sec-policy/selinux-chromium](../sec-policy/selinux-chromium.md) package as a dependency that provides SELinux policies required for Chromium to properly operate under a SELinux-restricted kernel.

This flag should only ever be toggled system-wide, i.e. as part of the SELinux-enabled Portage profile.

### suid
Run the `ninja chrome_sandbox` command during the build and install produced binary into the `/usr/bin/chrome-sandbox` location with SUID bit set. This is a special helper binary that is used to launch the zygote process, and once started it will create a new network and PID namespace, as well as `chroot()` the process to an empty directory on request.

This flag should be disabled as it is almost but not completely removed from Chromium and replaced with user namespaces sandbox.

### system-ffmpeg
Pass the `ffmpeg` and `opus` parameters to the `--system-libraries` option for the `build/linux/unbundle/replace_gn_files.py` script to replace bundled FFmpeg library with the system-wide version to link against.

It is recommended to disable this flag for maximum Chromium stability.

### system-harfbuzz
Pass the `use_system_harfbuzz=true` option to the `gn gen` command. Link against the system-wide version of the HarfBuzz text shaping library, instead of building and using the one bundled with the Chromium source code.

It is recommended to disable this flag for maximum Chromium stability.

### system-icu
Pass the `icu` parameter to the `--system-libraries` option for the `build/linux/unbundle/replace_gn_files.py` script to replace bundled ICU library with the system-wide version to link against.

It is recommended to disable this flag for maximum Chromium stability.

### system-png
Pass the `libpng` parameter to the `--system-libraries` option for the `build/linux/unbundle/replace_gn_files.py` script to replace bundled PNG library with the system-wide version to link against.

It is recommended to disable this flag for maximum Chromium stability.

### vaapi
Can't be used together with the `headless` flag. Pass the `use_vaapi=true` option to the `gn gen` command. Enable support for VA-API (Video Acceleration API) hardware accelerated video decoding using a compatible graphics adapter. Note: VA-API is not officially supported on Linux and is disabled at runtime, so it is necessary to enable it via the `enable-accelerated-video-decode` flag.

It is safe to disable this flag.

### wayland
Can't be used together with the `headless` flag. Pass the `ozone_platform_wayland=true`, `use_system_libdrm=true`, `use_system_minigbm=true`, `use_xkbcommon=true` and `ozone_platform="wayland"` options to the `gn gen` command. Enable native Wayland implementation for the Ozone platform that does not require `XWayland` or any other intermediate layers.

This flag should be enabled if the system using Wayland window server.

### widevine
Pass the `enable_widevine=true` option to the `gn gen` command. Build Google's Encrypted Media Extensions (EME) Content Decryption Module (CDM). It is used to watch premium video content such as Netflix.

It is safe to disable the flag.

### X
Pass the `ozone_platform_x11=true` option to the `gn gen` command. Enable support for running Chromium with the X Window System (aka X11, or simply X).

This flag should normally be enabled, unless headless mode is required or the system is running Wayland instead of X.
