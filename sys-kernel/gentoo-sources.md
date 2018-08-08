# sys-kernel/gentoo-sources

### build
Skip pulling in a number of dependencies that are needed to build a kernel (with an intention to use externally provided versions).

This flag should normally be disabled. It is used by the Gentoo team during the bootstrap process for early stages and while building images.

### experimental
Apply additional patches to the Kernel source code before installing to enable experimental features that aren't supported by the upstream. Currently two patches are available: BFQ disk scheduler v6r2 and additional CPU optimizations for GCC.

This flag should only be enabled if there is a need to use one of the experimental features.

### symlink
Kernel sources are installed into the `/usr/src/linux-<VERSION>` directory by Portage. Enabling this flag will create a symlink from the installation directory into the `/usr/src/linux` standard path that is expected by the most tools looking for kernel sources. Symlinks can be also managed by the `eselect` tool.

This flag should be enabled if the installed kernel to be used for the target system.
