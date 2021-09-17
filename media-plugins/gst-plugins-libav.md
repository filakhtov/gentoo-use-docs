# media-plugins/gst-plugins-libav

### nls
Pass the `-Dnls=enabled` option to the configure script. Use the Gettext library to provide an ability to translate programs messages into different languages based on the system locale settings.

This flag can be safely disabled, unless there is a need to use a non-English language.

### test
Pass the `-Dtests=enabled` option to the Meson build script. Build the test suite provided with the source code and execute the `ninja test` command inside of the virtual Xvfb session to run it after the main build is completed. This will extend a build time.

This flag should normally be disabled as it is mainly useful for the maintainers, testers and developers.
