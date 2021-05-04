# dev-libs/libgit2

### examples
Install the `examples` directory from the source tree into the `/usr/share/doc/libgit-2-<VERSION>/examples` directory. These examples are a mixture of basic emulation of core Git command line functions and simple snippets demonstrating libgit2 API usage.

It is safe to disable the flag.

### gssapi
Pass the `-DUSE_GSSAPI=ON` option to the CMake build command. Link against the `libgssapi` library to enable support for GSSAPI (Generic Security Service Application Program Interface), Kerberos and SPNEGO (Simple and Protected GSSAPI Negotiation Mechanism) authentication mechanisms for non-standard HTTP authentication.

This flag should normally be disabled, unless there is a need to use GSSAPI/SPNEGO protocols.

### ssh
Pass the `-DUSE_SSH=ON` option to the CMake build command. Link agains the `LibSSH2` library to provide support for GIT over SSH (Secure Shell) transport protocol.

It is safe to disable the flag if there is no need to access GIT repositories over SSH.

### test
Execute the `ctest -R offline` command after the main build is completed to run the test suite provided with the source code and check for regressions. This will extend the build time.

This flag should normally be disabled, as these tests are primarily oriented towards developers, testers and maintainers.

### threads
Pass the `-DTHREADSAFE=ON` option to the CMake build command. Build the `libgit2` library with, somewhat limited, multi-threading support, e.g. unless otherwise specified in the documentation, objects cannot be safely accessed by multiple threads simultaneously, because most data structures do not guard against concurrent access themselves.

It is recommended to enable this flag.

### trace
Pass the `-DENABLE_TRACE=ON` option to the CMake build command. Enables tracing support, i.e. provide the `git_trace_set` function that can be used by the consuming application to set the desired level of tracing and provide a callback function to be executed when an interesting event is occurring.

This flag should normally be disabled.
