# dev-lang/rust

### clippy
Append `clippy` to the `tools` option in the `build` section of the `config.toml` build configuration file. Build and install `clippy-driver` and `cargo-clippy` linting tool that provide a collection of lints to catch common mistakes and improve the Rust code.

It is safe to disable this flag.

### debug
Set the `optimize` option to `false`, `release-debuginfo` to `true`, `assertions` to `true` under the `llvm` section, and `optimize` to `false`, `debug` to `true`, `debug-assertions` to `true` under the `rust` section of the `config.toml` build configuration file. Produce the unoptimized, debug version of the rust toolchain, compiler and standard library, also enable LLVM, compiler and standard library assertions. This will take much more time to build the package and make it much slower to run.

This flag should only ever be enabled if there is a need to debug toolchain, standard library or compiler components of rust.

### doc
Set the `docs` and `compiler-docs` options to `true` in the `build` section of the `config.toml` build configuration file. Install standard library, facade crates and the compiler documentation, as well as the `rustdoc` tool, that allows to generate documentation from the source code.

It is safe to disable the flag.

### miri
Requires the `nightly` flag to be enabled. Append `miri` to the `tools` option in the `build` section of the `config.toml` build configuration file. Build and install the `miri` tool - an experimental interpreter for Rust's mid-level intermediate representation (MIR). It can run binaries and test suites of cargo projects and detect certain classes of undefined behavior.

This flag should normally be disabled, because `miri` is an experimental nightly feature.

### nightly
Set the `channel` option of the `rust` section to `nightly` (instead of default `stable`) in the `config.toml` build configuration file. Build and install the `nightly` unstable and experimental Rust toolchain.

It is recommended to keep this flag disabled, unless there is a need for some experimental features and even then a great deal of care has to be taken.

### parallel-compiler
Requires `nightly` flag to be enabled. Set the `parallel-compiler` to `true` in the `rust` section of the `config.toml` build configuration file. Build an experimental parallel `rustc` compiler - one that can perform typechecking, borrow-checking, or running other static analyses on crates in parallel.

This flag should normally be disabled as this feature is experimental.

### rls
Append `rls`, `analysis`, `src` to the `tools` option in the `build` section of the `config.toml` build configuration file. Build and install the RLS (Rust Language Server) component that provides IDEs, editors, and other tools with information about Rust programs, and supports `goto definition`, symbol search, reformatting, code completion as well as renaming and refactoring features.

This flag can be safely disabled.

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
