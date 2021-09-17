# media-plugins/gst-plugins-libmms

### test
Pass the `-Dtests=enabled` option to the Meson build script. Build the test suite provided with the source code and execute the `ninja test` command inside of the virtual Xvfb session to run it after the main build is completed. This will extend a build time.

This flag should normally be disabled as it is mainly useful for the maintainers, testers and developers.
