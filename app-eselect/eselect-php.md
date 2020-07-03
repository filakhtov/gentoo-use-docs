# app-eselect/eselect-php

### apache2
Pass the `--enable-apache2` option to the configure script. Enable support for switching between different versions of `mod_php` module that is used under the Apache 2 HTTP server, i.e. updating module symlinks to the appropriate version.

This flag can be safely disabled.

### fpm
Pass the `--enable-fpm` option to the configure script. Enable support for switching between different versions of the PHP FPM binary by updating the `php-fpm` symlink to point to an appropriate version.

This flag can be safely disabled.
