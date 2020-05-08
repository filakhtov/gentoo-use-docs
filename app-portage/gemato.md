# app-portage/gemato

### gpg
Pull the [app-crypt/gnupg](../app-crypt/gnupg.md) package as a dependency. Provide an ability to import trust keys and verify signatures using the GnuPG. Gemato will make a direct calls to `gpg` binary, passing necessary arguments and parsing an output.

This flag is required for Portage tree verification feature.

### test
Execute the `setup.py test` command when the main build is completed. Run a test suite provided with the source code. This will extend a build time.

This flag should be normally disabled as it is mainly useful for the Gentoo team, testers and developers.

### tools
Install additional tools: `benchmark-verify.py`, `benchmark.py`, `fuzzy-hash-tester.py`, `gen-compression-tests.bash`, `gen-hash-tests.bash`, `gen-test-manifest.py`, `gen_fast_manifest.py`, `gen_fast_metamanifest.py` into the `/usr/share/gemato` directory. These tools are designed for testing and benchmarking.

It is safe to disable the flag.
