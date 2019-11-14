# media-libs/libjpeg-turbo

### java
Pass the `-DWITH_JAVA=true` (`false` when the flag is disabled) option to the CMake build command and export the `JAVACFLAGS` and `JNI_CFLAGS` environment variables with appropriate values. Build and install the `turbojpeg.jar` JAR file - Java bindings for the `libturbojpeg` library.

This flag should only be enabled if there is a need for Java bindings.

### static-libs
Pass the `-DENABLE_STATIC=true` (`false` if the flag is disabled) option to the CMake build command. Build and install a statically linked version of the `libjpeg` and `libturbojpeg` libraries.

This flag should only ever be enabled if there is a need for the static libraries.
