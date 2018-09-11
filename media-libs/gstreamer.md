# media-libs/gstreamer

### caps
Pass the `--with-ptp-helper-permissions=capabilities` option to the configure script. Use the `libcap` library for the `gst-ptp-helper` tool to drop capabilities after binding to the privileged ports that are used to participate in the PTP (Precision Time Protocol) synchronization.

This flag should be enabled to improve security, otherwise the `gst-ptp-helper` binary will have `suid` bit.

### introspection
Pass the `--enable-introspection` option to the configure script. Generate and install the `GstController-1.0.gir`, `GstNet-1.0.gir`, `GstBase-1.0.gir`, `GstCheck-1.0.gir` and `Gst-1.0.gir` GIR metadata files to provide dynamic bindings for the `libgstreamer`, `libgstcheck`, `libgstbase`, `libgstnet` and `libgstcontroller` libraries to languages other than C using the GObject Introspection infrastructure.

It is safe to disable the flag.

### nls
Pass the `--enable-nls` option to the configure script. Use the Gettext library to provide an ability to translate programs messages into different languages at a runtime based on system locale settings.

This flag should be enabled if there is a need to use the GStreamer tools in a non-English language.

### orc
Disable the PaX MPROTECT kernel restrictions from the `gst-plugin-scanner` and `gst-launch-1.0` binaries by setting an `m` flag on them so that GStreamer can run the ORC (Oil Runtime Compiler) accelerated code under the PaX-enabled kernel.

This flag should only be enabled for systems with a PaX-restricted kernel that have the ORC compiler available.

### test
Pass the `--enable-tests` option to the configure script. Build the test suite provided with the source code and execute the `make check` command to run it after the main build is completed. This will extend a build time.

This flag should normally be disabled as it is mainly useful for the Gentoo team, testers or developers.

### unwind
Pass the `--with-unwind` and the `--with-dw` options to the configure script. Use the `libunwind` library to enable stack traces generation and the elfutils `libdw` library to add source lines and numbers to backtraces.

This flag should only be enabled for tracing or debugging purposes.
