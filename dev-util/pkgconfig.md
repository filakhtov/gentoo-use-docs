# dev-util/pkgconfig
### hardened
Replace `-O2` and `-O3` compiler optimization flags with `-O1` but only on `ppc64` architecture. Does not do anything for other platforms.

This flag can be safely disabled.

### internal-glib
Pass the `--with-internal-glib` option to the configure script. Use glib sources provided together with the `pkg-config` package to build a glib library needed for `pkg-config` compilation. This is necessary to break a circular dependency between these two packages.

It is safe to disable this flag. It should be enabled if building the `pkg-config` for the first time and a `glib` is not yet installed onto the target system. It can also be disabled if there is no desire to have a system version of a `glib` but the `pkg-config` package is required.
