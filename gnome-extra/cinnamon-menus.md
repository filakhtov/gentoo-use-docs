# gnome-extra/cinnamon-menus

### debug
Pass the `-Denable_debug=true` option to the meson build script. Pass the `-DG_ENABLE_DEBUG` option to the compiler to define the `G_ENABLE_DEBUG` macro that will perform runtime checking to print out different types of debugging information when running. When this flag is disabled, append the `-DG_DISABLE_ASSERT`, `-DG_DISABLE_CHECKS` and `-DG_DISABLE_CAST_CHECKS` options to the compiler invocations to disable runtime assertions and various checks that will terminate the program if defined conditions are violated.

This flag should only be enabled for debugging purposes, because it can cause abnormal program terminations.

### gtk-doc
Pass the `-Denable_docs=true` option to the meson build script. Use the Gtk-Doc tool to generate the API documentation from the source code annotation and install it into the system.

It is safe to disable this flag.
