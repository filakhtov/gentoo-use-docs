# app-portage/gemato

### blake2
Pull the [dev-python/pyblake2](../dev-python/pyblake2.md) package as a dependency. Provide support for the BLAKE2 family of hashes using the `pyblake2` Python module.

The flag should be enabled to support BLAKE2 hashing on pre Python 3.6 environments.

### bzip2
Pull the [dev-python/bz2file](../dev-python/bz2file.md) package as a dependency. Newer Python versions 3.3+ support a BZip2 compression out of the box. Older versions provide the `bz2` module that does not handle multiple streams, so backported `bz2file` module should be used. Enable an ability to transparently decompress files in the BZip2 format.

This flag should only be enabled to support BZip2 compression algorithm while running Gemato on a pre Python 3.3 environment.

### gpg
Pull the [app-crypt/gnupg](../app-crypt/gnupg.md) package as a dependency. Provide an ability to import trust keys and verify signatures using the GnuPG. Gemato will make a direct calls to `gpg` binary, passing necessary arguments and parsing an output.

This flag is required for Portage tree verification feature.

### lzma
Pull the [dev-python/backports-lzma](../dev-python/backports-lzma.md) package as a dependency. Support transparent decompression of files compressed using the LZMA (aka XZ) algorithm. A Python version 3.3 onwards provides support for the LZMA out of the box. Older versions will use backported version of the LZMA algorithm.

This flag should be enabled if there is a need to support LZMA-compressed algorithms under a pre Python 3.3 environment.

### sha3
Pull the [dev-python/pysha3](../dev-python/pysha3.md) package as a dependency. Provide support for SHA3 family of hashes via the `pysha3` Python module.

The flag can be safely disabled.

### test
Execute the `setup.py test` command when the main build is completed. Run a test suite provided with the source code. This will extend a build time.

This flag should be normally disabled as it is mainly useful for the Gentoo team, testers and developers.

### tools
Install additional tools: `benchmark-verify.py`, `benchmark.py`, `fuzzy-hash-tester.py`, `gen-compression-tests.bash`, `gen-hash-tests.bash`, `gen-test-manifest.py`, `gen_fast_manifest.py`, `gen_fast_metamanifest.py` into the `/usr/share/gemato` directory. These tools are designed for testing and benchmarking.

It is safe to disable the flag.
