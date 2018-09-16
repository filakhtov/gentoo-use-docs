# x11-apps/mesa-progs

### egl
Execute the `make eglinfo` command from the `src/egl/opengl` source subirectory, `make libeglut_x11.la` command from the `src/egl/eglut/` source subdirectory and then finally `make eglgears_x11` command from the `src/egl/opengl` source subdirectory. Build and install the `eglinfo` tool - a utility for displaying information about a platform's EGL support, and the `eglgears_x11` tool - an EGL version of the infamous "gears" GL demo that displays a set of rotating gears and prints out the frame rate at regular intervals..

This flag should be enabled if there is a need to test and obtain information about EGL backend.

### gles2
Only works if the `egl` flag is enabled. Execute the `make es2_info` command from the `src/egl/opengles2` source subirectory and the `make es2gears_x11` command from the `src/egl/opengles2` source subirectory. Build and install the `es2_info` tool to shows information about the supported OpenGL ES extensions, and the `es2gears_x11` tool - a port of the "gears" demo to GLES2 that displays a set of rotating gears and prints out the frame rate at regular intervals.

This flag should be enabled if there is a need to test and obtain information about OpenGL ES 2.0, primarily on the embedded systems.
