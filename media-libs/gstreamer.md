# media-libs/gstreamer

### caps
Pass the `-Dptp-helper-permissions=capabilities` option to the Meson build script. Use the `libcap` library for the `gst-ptp-helper` tool to drop capabilities after binding to the privileged ports that are used to participate in the PTP (Precision Time Protocol) synchronization. When this flag is disabled, pass the `-Dptp-helper-permissions=setuid-root`, `-Dptp-helper-setuid-user=nobody`, `-Dptp-helper-setuid-group=nobody` options instead to enable setuid permissions on the `gst-ptp-helper` binary.


This flag should be enabled to improve security, otherwise the `gst-ptp-helper` binary will have `suid` bit.

### introspection
Pass the `-Dintrospection=enabled` option to the Meson build script. Generate and install the `GstController-1.0.gir`, `GstNet-1.0.gir`, `GstBase-1.0.gir`, `GstCheck-1.0.gir` and `Gst-1.0.gir` GIR metadata files to provide dynamic bindings for the `libgstreamer`, `libgstcheck`, `libgstbase`, `libgstnet` and `libgstcontroller` libraries to languages other than C using the GObject Introspection infrastructure.

It is safe to disable the flag.

### nls
Pass the `-Dnls=enabled` option to the Meson build script. Use the Gettext library to provide an ability to translate programs messages into different languages at a runtime based on system locale settings.

This flag should be enabled if there is a need to use the GStreamer tools in a non-English language.

### orc
Disable the PaX MPROTECT kernel restrictions from the `gst-plugin-scanner` and `gst-launch-1.0` binaries by setting an `m` flag on them so that GStreamer can run the ORC (Oil Runtime Compiler) accelerated code under the PaX-enabled kernel.

This flag should only be enabled for systems with a PaX-restricted kernel that have the ORC compiler available.

### test
Pass the `-Dtests=enabled` option to the Meson build script. Build the test suite provided with the source code and execute the `ninja test` command inside of the virtual Xvfb session to run it after the main build is completed. This will extend a build time.

This flag should normally be disabled as it is mainly useful for the maintainers, testers and developers.

### unwind
Pass the `-Dlibunwind=enabled` and the `-Dlibdw=enabled` options to the Meson build script. Use the `libunwind` library to enable stack traces generation and the elfutils `libdw` library to add source lines and numbers to backtraces.

This flag should only be enabled for tracing or debugging purposes.
