# sys-libs/timezone-data

### leaps-timezone
Pass the `REDO=posix_right` variable (`REDO=posix_only` if disabled) to the `make` command. Install the "right" timezone files that are interpreted as seconds since the epoch counting leap seconds (usint TAI-10 standard) in addition to POSIX ones that ignore them.

It is safe to disable the flag, however should be enabled if "strict correctness" of time is required.

### nls
Append a `-DHAVE_GETTEXT=1` option (`-DHAVE_GETTEXT=0` when disabled) to the `CPPFLAGS` variable for a duration of the build. Append a `-lintl` option to the `LDLIBS` variable if a `libintl` library is available in the system and pass it to the make command. Provide an ability to translate programs messages into different languages based on a system locale settings.

This flag should be enabled if there is a need to use non-English language and can be disabled otherwise.

### zic-slim
Append the `-DZIC_BLOAT_DEFAULT=slim` (`fat` when the flag is disabled) option to the `CPPFLAGS` environment variable for a duration of the build. Use the `slim` TZif (Time Zone Information Format) format for `/usr/share/zoneinfo` files and change the default output format of the `zic` compiler to `slim` as well.

This flag should normally be disabled, because `slim` format breaks quite a few programs that read timezone information.
