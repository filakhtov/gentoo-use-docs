# sci-libs/fftw

### doc
Install additional documentation in an HTML and PDF formats into the `/usr/share/doc/fftw-<VERSION>` directory. Documentation includes F.A.Q., detailed description of the library and examples of how to use it, etc.

It is safe to disable the flag.

### fortran
Pass the `--enable-fortran` option to the configure script. Build special wrapper functions that allow Fortran programs to call FFTW subroutines.

This flag should only be enabled if there is a need to use the FFTW library in Fortran programs.

### mpi
Pass the `--enable-mpi` option to the configure script. Build and install the `libfftw3_mpi`, `libfftw3l_mpi` and `libfftw3f_mpi` libraries that use the MPI (Message-Passing Interface) library to perform parallel transforms for distributed-memory systems. This is especially useful when you are transforming arrays so large that they do not fit into the memory of a single processor or machine.

This flag should normally be disabled and should only be enabled if there is a need for massive computations.

### openmp
Pass the `--enable-openmp` option to the configure script. Build and install the `libfftw3_omp`, `libfftw3f_omp` and `libfftw3l_omp` libraries to enable support for multi-threading computations using OpenMP compiler directives in order to induce parallelism rather than spawning its own threads directly

This flag should be enabled if the target system has multiple cores or processors and there is a need to perform heavy transformations that would benefit from parallelization.

### test
For each library variant build execute the `make smallcheck` command from the `tests` source subdirectory. Run a test suite provided with the source code and check for regressions. This will increase the build time.

This flag should normally be disabled as it is mainly used by the developers, testers or maintainers.

### threads
Pass the `--enable-threads` option to the configure script. Build and install the `libfftw3_threads`, `libfftw3l_threads` and `libfftw3f_threads` libraries which provides a simple interface to parallel transforms for SMP (Symmetric MultiProcessing) systems.

This flag should be enabled on SMP systems to achieve parallelization.

### zbus
Pass the `--enable-mips-zbus-timer` option to the configure script. Enable support for the MIPS ZBus hardware cycle-counter that is used by the FFTW’s planner to execute and time different possible FFT algorithms in order to pick the fastest plan for a given problem.

This flag should be enabled on MIPS platform only.
