# gnome-extra/cjs

### cairo
Pass the `--with-cairo` option to the configure script. Integrate with the Cairo graphics library to provide an ability to produce 2d graphics, load, manipulate, display and draw images, render text and so on, using the JavaScript language.

This flag should be enabled if there is a need to run Cjs scripts that draw images using the Cairo library.

### examples
Install additional code examples written in the JavaScript language into the `/usr/share/doc/cjs-<VERSION>/examples` directory. Examples show how to create Gtk+ window with simple button, render a scene using Clutter, access translations using Gettext and so on.

It is safe to disable the flag.

### gtk
Pass the `--with-gtk` option to the configure script. Enable support for the GTK+ toolkit to generate user interfaces, create windows and dialogs using the JavaScript language and integrate with the GTK+ mainloop and provide an ability to emit and receive signals, handle events, etc.

This flag should be enabled if there are any apps that use Cjs to create GTK+ GUIs.

### test
Start a new Xvfb session and execute the `make check` command inside of it when the main build is completed. Run the test suite provided with the source code. This will extend a build time.

This flag should normally be disabled as it is primarily used by the Gentoo team, testers and developers.
