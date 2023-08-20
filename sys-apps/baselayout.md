# sys-apps/baselayout

### build
Execute a `make layout-usrmerge` command to install directories and some device nodes. If the `split-usr` flag is enabled then execute the `make layout` instead.

This flag is primarily used for building early images and stages and should not be enabled on the actual running system.

### split-usr
This flag ensures that the `/bin` and `/usr/bin` directories are separate. When disabled, baselayout will create symlink between these directories so that everything is installed into one single directory.

This flag should be enabled.
