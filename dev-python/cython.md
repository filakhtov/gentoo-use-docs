# dev-python/cython

### debug
Append the `-UNDEBUG` option to the `CXXFLAGS` environment variable for the duration of the build (`-DNDEBUG` if the flag is disabled). Enable additional assertions in the C code that will fail and terminate the program if the condition is violated. This is useful for development and debugging purposes.

This flag should normally be disabled.

### doc
Use the Sphinx documentation generator to build the documentation in the HTML format and install it into the system. Documentation includes information on how to build and install Cython, some tutorials, like calling C functions, profiling, working with NumPy, etc as well as a user guide with language basics, extension types, interfacing with external C code and so forth.

This flag can be safely disabled.

### emacs
Insatll Emacs major mode for editing Cython files.

This flag should only be enabled if there is a need to edit Cython files with the Emacs editor.

### test
Execute the `runtests.py` script after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily used by the developers, maintainers and testers.
