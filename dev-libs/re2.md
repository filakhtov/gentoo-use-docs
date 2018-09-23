# dev-libs/re2

### icu
Patch the `Makefile` file to uncomment the `LDICU=` and the `CCICU=` variables. Use the `libicu` library to provide full Unicode properties support that allows to lookup a character by category, block, script, etc and not just by its name.

It is safe to disable the flag, unless there is a need to use advanced Unicode properties for lookup.
