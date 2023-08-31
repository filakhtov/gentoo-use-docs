# virtual/libudev

### eudev
Use the `eudev` as a Udev implementation for the system.

This flag should only be enabled system-wide, otherwise it will create all sorts of conflicts and problems.

### sticky-tags
Enable support for sticky tags API (i.e. tags that can only be added, but never removed). This flag is incompatible with `eudev`, because eudev doesn't support sticky tags.

It is safe to disable this flag, but certain packages depend on sticky tags features and will require it to be enabled.

### systemd
Use a Udev component provided by the SystemD instead of standalone Udev or eudev.

This flag should only be enabled system-wide, e.g. as part of the SystemD-enabled Portage profile.
