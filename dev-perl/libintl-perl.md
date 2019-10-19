# dev-perl/libintl-perl

### examples
Install additional example files from the `sample` subdirectory of the source tree. The example demonstrates one way to complete internationalization process for a Perl package. The example focuses on the packaging process, i.e. on the things that needs to be done to maintain an internationalized Perl package, so that users the package will benefit from translations provided.

This flag should normally be disabled.

### minimal
When enabled, the [dev-perl/File-ShareDir](../dev-perl/File-ShareDir.md) dependency won't be installed and message catalogs will only be searched in the standard include path, instead of checking the Perl-specific shared directory for `locale` and `LocaleData` directories.

This flag should be disabled if there is a need to load message catalogs from shared directory.
