# app-editors/neovim

### lto
Pass the `-DENABLE_LTO=true` option to the cmake command. Enable LTO (Link-Time Optimization) to produce a better optimized binary that has a better performance at runtime, at the expense of compilation time.

This flag should normally be enabled. Only disable it if there is a need to debug NeoVim.

### nvimpager
Create a symlink for `nvimpager` pointing to the `less.sh` script provided by NeoVim. This script allows NeoVim to be used as a pager, providing a similar experience to the `less` command.

It is safe to disable this flag.

### test
Execute the `make test` command after the main build is completed. Run the test suite provided wit the source code to check for any regressions. This will extend the build time.

This flag should normally be disabled, because these test are primarily oriented towards the developers, maintainers and testers.
