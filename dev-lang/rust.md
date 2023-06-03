# dev-lang/rust

### clippy
Append `clippy` to the `tools` option in the `build` section of the `config.toml` build configuration file. Build and install `clippy-driver` and `cargo-clippy` linting tools that provide a collection of lints to catch common mistakes and improve the Rust code.

It is safe to disable this flag.

### debug
Set the `optimize` option to `false`, `release-debuginfo` to `true`, `assertions` to `true` under the `llvm` section, and `debug` to `true`, `debug-assertions` to `true`, `debug-assertions-std` to `true`, `debuginfo-level` to `2`, `debuginfo-level-rustc` to `2`, `debuginfo-level-std` to `2`, `debuginfo-level-tools` to `2` and `optimize-tests` to `false` under the `rust` section of the `config.toml` build configuration file. Produce the unoptimized, debug version of the rust toolchain, compiler and standard library, also enable LLVM, compiler and standard library assertions. This will take much more time to build the package and make it much slower to run.

This flag should only ever be enabled if there is a need to debug toolchain, standard library or compiler components of rust.

### dist
Install dist tarballs that were used for bootstrapping the Rust compiler itself.

This flag should normally be disabled.

### doc
Set the `docs` and `compiler-docs` options to `true` in the `build` section of the `config.toml` build configuration file. Install standard library, facade crates and the compiler documentation, as well as the `rustdoc` tool, that allows to generate documentation from the source code.

It is safe to disable the flag.

### llvm-libunwind
Set the `llvm-libunwind` option in the `config.toml` build configuration file to either `system` or `in-tree`, depending if the `system-llvm` flag is enabled or disabled. When this flag is disabled, set the `llvm-libunwind` option to `no`. Link against LLVM's `libunwind` library instead of the GCC one to generate backtraces on panics.

This flag can be safely disabled.

### miri
Requires the `nightly` flag to be enabled. Append `miri` to the `tools` option in the `build` section of the `config.toml` build configuration file. Build and install the `miri` tool - an experimental interpreter for Rust's mid-level intermediate representation (MIR). It can run binaries and test suites of cargo projects and detect certain classes of undefined behavior.

This flag should normally be disabled, because `miri` is an experimental nightly feature.

### nightly
Set the `channel` option of the `rust` section to `nightly` (instead of default `stable`) in the `config.toml` build configuration file. Build and install the `nightly` unstable and experimental Rust toolchain.

It is recommended to keep this flag disabled, unless there is a need for some experimental features and even then a great deal of care has to be taken.

### parallel-compiler
Requires `nightly` flag to be enabled. Set the `parallel-compiler` to `true` in the `rust` section of the `config.toml` build configuration file. Build an experimental parallel `rustc` compiler - one that can perform typechecking, borrow-checking, or running other static analyses on crates in parallel.

This flag should normally be disabled as this feature is experimental.

### profiler
Append `rust-demangler` to the `tools` option and set the `profiler` to `true` in the `build` section of the `config.toml` build configuration file. Build and install the `rust-demangler` "extended tool" that can be used to perform Rust-specific symbol demangling and build the profiler runtime that enables profiling instrumentation (and profile-guided optimization) and code coverage support.

It is safe to disable this flag.

### rust-analyzer
Append the `rust-analyzer` to the `tools` option in the `build` section of the `config.toml` build configuration file. Install the `rust-analyzer` - a modular compiler frontend for the Rust language that is used by IDEs (Integrated Development Environment) to create better support for Rust language.

It is safe to disable this flag.

### rust-src
Append the `src` to the `tools` option in the `build` section of the `config.toml` build configuration file. Install the `rust-src` tool that is used to download a tarball of the Rust source code associated with the current version of the `rustc` compiler.

It is safe to disable this flag.

### rustfmt
Append `rustfmt` to the `tools` option in the `build` section of the `config.toml` build configuration file. Install the `rustfmt` tool that is used to format Rust code according to style guidelines.

It is safe to disable the flag.

### system-bootstrap
Normally, the prebuilt stage 0 is downloaded and used to build the Rust toolchain. When this flag is enabled, the Rust toolchaing will be built completely from scratch, including the stage 0 build. This will extend the build time.

This flag should normally be disabled.

### system-llvm
Set the `link-shared` option to `true` in the `llvm` section, `lld` option to `false` in the `rust` section and set the `llvm-config` option of the target specific section to point to the system `llvm-config` binary in the `config.toml` build configuration file. Use the system installed version of the LLVM compiler and linker, instead of using ones provided by the Rust package, as well as link against shared LLVM system libraries, instead of using static linkage.

It is recommended to disable this flag, simply because an LLVM version provided with Rust includes many patches, which system version would not have and thus can cause variety of compilation issues.

### test
Execute the `x.py test` script when the main build is completed to run the test suite provided with the source code and check for any regressions in the compiler code. This will extend the overall build time.

This flag should normally be disabled, because these tests are primarily oriented towards the maintainers, developers and testers.

### verify-sig
Perform signature verification of the upstream source code archive before extracting it and building the package.

It is safe to disable this flag.

### wasm
Append the `wasm32-unknown-unknown` to the `target` option in the `llvm` section of the `config.toml` build configuration file, also set `lld` option in the `rust` section to `true`, but only if the `system-llvm` flag is disabled, and additionally, append a new `target.wasm32-unknown-unknown` target section and set the `linker` option to `rust-lld` (or `lld` if the `system-llvm` flag is enabled). Enable support for compiling code that can be executed in the Wasm (WebAssembly) virtual machine.

This flag should only be enabled if there is a need to produce WebAssembly binaries.
