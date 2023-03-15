# media-libs/openh264

### plugin
Execute the `make plugin` command after the main build is completed. Build and install the `gmpopenh264` and the `libgmpopenh264` libraries that provides a plugin for browsers supporting the Netscape plugin architecture to encode a stream into the H.264 codec, e.g. for video calls.

This flag should be enabled if there is a need for such a plugin, e.g. for the Firefox browser.

### test
Execute the `make test` command after the main build is completed to run the test suite provided with the source code and check for regression. This will extend the build time.

This flag should normally be disabled because these tests are mainly tailored towards the developers, testers and maintainers.

### utils
Install the `h264enc` and the `h264dec` utilities and rename them to `openh264enc` and `openh264dec` accordingly to avoid collision with the [media-video/h264enc](../media-video/h264enc.md) package.

It is safe to disable the flag.
