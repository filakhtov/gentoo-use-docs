# app-alternatives/bzip2

### lbzip2
Use the [app-arch/lbzip2](../app-arch/lbzip2.md) package as a provider for bzip2. A multi-threaded bzip2/bunzip2 utility that employs multiple threads and an input-bound splitter even when decompressing `.bz2` files created by the standard bzip2.

### pbzip2
Use the [app-arch/pbzip2](../app-arch/pbzip2.md) package as a provider for bzip2. PBZIP2 is a parallel implementation of the bzip2 block-sorting file compressor that uses pthreads and achieves near-linear speedup on SMP machines.

### reference
Use the [app-arch/bzip2](../app-arch/bzip2.md) package as a provider for bzip2. This is a reference implementation of the Burrows-Wheeler block-sorting text compression algorithm, and Huffman coding.

### split-usr
If the flag is enabled some of the produced libraries will be installed into the `/lib` directory and binaries into the `/bin`, instead of the `/usr/lib` and `/usr/bin` directories, so that they are available during the early boot when the `/usr` partition is not yet mounted.

This flag is necessary to boot the system that has separated `/usr` partition, but otherwise can be safely disabled.
