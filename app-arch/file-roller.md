# app-arch/file-roller

### gtk-doc
Pass the `-Dapi_docs=enabled` option to the Meson build script. Use the Gi-DocGen tool to generate API documentation and install it into the `/usr/share/gtk-doc` directory.

It is safe to disable this flag.

### introspection
Pass the `-Dintrospection=enabled` option to the Meson build script. Enable support for runtime introspection data generation for the `file-roller` binary, which is primarily used for [Tartan](https://gitlab.freedesktop.org/tartan/tartan) static analysis tool.

This flag should normally be disabled.

### nautilus
Pass the `-Dnautilus-actions=enabled` (`disabled` when the flag is disabled) option to the meson build command. Build and install Nautilus file manager plugin to integrate with file-roller. This provides context menu options for quickly creating or extracting archives.

This flag should only be enabled if the target system uses Nautilus as a file manager.
