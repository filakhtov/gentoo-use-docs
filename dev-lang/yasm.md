# dev-lang/yasm

### nls
Pass the `--enable-nls` option to the configure script. Use the Gettext library to provide an ability to translate programs messages at runtime into various languages based on the system locale settings.

This flag should be enabled if there is a need to use Yasm in a non-English language.

### python
Prepare environment for configure script to find an appropriate Python version. Pass the `--enable-python` and the `--enable-python-bindings` options to the configure script. Run a Python scripts to generate the assembly code description files in C++. Build and install the `yasm` Python module that provides Python bindings for the `libyasm` library.

It is safe to disable the flag,
