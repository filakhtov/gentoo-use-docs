# app-arch/gcab

### introspection
Pass the `--enable-introspection` option to the configure script. Generate and install the `GCab-1.0.gir` GIR metadata file to provide dynamic bindings for the `libgcab` library to languages other than C using the GObject Introspection infrastructure.

It is safe to disable the flag.

### vala
Generate and install the `libgcab-1.0.vapi` Vala language bindings for the `libgcab` library. When disabled, pass the `VAPIGEN=no` option to the configure script to disable Vala bindings generation.

The flag can be safely disabled.
