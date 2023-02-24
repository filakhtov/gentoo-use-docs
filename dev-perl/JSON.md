# dev-perl/JSON

### examples
Install the `bench_encode.pl` and `bench_decode.pl` scripts that demonstrate how to use the library and at the same time can be used for performance benchmarking it.

This flag should normally be disabled.

### test
Execute the `make test` command after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the bulid time.

This flag should normally be disabled because these tests are primarily oriented towards the developers, maintainers and testers.

### xs
Install the additional extension library - `JSON::XS` that allows converting Perl data structures to JSON and vice versa.

It is safe to disable this flag, unless there is a need to use any of the features provided by the `JSON::XS` library.
