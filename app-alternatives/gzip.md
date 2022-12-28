# gzip

### pigz
Use the [app-arch/pigz](../app-arch/pigz.md) package as a provider for gzip. A parallel implementation of gzip.

### reference
Use the [app-arch/gzip](../app-arch/gzip.md) package as a provider for gzip. This is a standard GNU compressor reference implementation and is a default choice.

### split-usr
If the flag is enabled some of the produced libraries will be installed into the `/lib` directory, instead of the `/usr/lib` directory, so that they are available during the early boot when the `/usr` partition is not yet mounted.

This flag is necessary to boot the system that has separated `/usr` partition, but otherwise can be safely disabled.
