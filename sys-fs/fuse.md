# sys-fs/fuse

### suid
Set the `suid` bit on the `fusermount3` binary to allow non-privileged users to mount filesystems.

It is recommended to keep this flag enabled to allow non-root FUSE mounts.

### test
Pass the `-Dexamples=true` and `-Dtests=true` options to the meson build script to build the test suite provided with the source code, and execute the `python -m pytest test` command after the main build is completed to run it and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards developers, maintainers and testers.
