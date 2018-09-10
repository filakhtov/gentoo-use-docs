# dev-python/numpy

### doc
Download additional documentation in the HTML format and install it into the `/usr/share/doc/numpy-<VERSION>/html` directory. Documentation provides a complete NumPy manual which includes user guide, reference, developer guide and so forth.

It is safe to disable the flag.

### lapack
Append the `--libs-only-other cblas lapack` options to the `LDFLAGS` environment variable for a duration of the build and set an appropriate Fortran compiler. Create the `site.cfg` site configuration file and set BLAS (Basic Linear Algebra Subprograms) and LAPACK (Linear Algebra PACKage) paths. Integrate with Fortran BLAS and LAPACK libraries to perform efficient linear algebra computations, making NumPy a decent alternative to MATLAB.

This flag should be enabled if there is a need to perform linear algebra calculations.

### test
For every active Python implementation execute the test command to run a test suite provided with the source code after the main build is completed. This will extend a build time.

This flag is only useful for the testers, developers or the Gentoo team and should be normally disabled.
