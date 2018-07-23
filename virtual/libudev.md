# virtual/libudev

### static-libs
Install a version of Udev that can provide statically linked libraries which at this moment in time is only eudev.

This flag should only ever be enabled if there is a need for the Udev static libraries.

### systemd
Use a Udev component provided by the SystemD instead of standalone Udev or eudev.

This flag should only be enabled system-wide, e.g. as part of the SystemD-enabled Portage profile.
