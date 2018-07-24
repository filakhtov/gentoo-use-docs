# sys-apps/miscfiles

### minimal
Remove `words` and `extra.words` files from `/usr/share/dict` directory. Compress all other dictionary files using a Gzip format. Symlink a `words` fitle to a `web2.gz` and an `extra.words` to a `web2a.gz`, also symlink `connectives` and `propernames` onto their compressed versions. Remove `/usr/share/misc` directory from an installation. This will minimize the space occupied by the package.

This flag should be disabled. It can be useful to save space on an embedded system.
