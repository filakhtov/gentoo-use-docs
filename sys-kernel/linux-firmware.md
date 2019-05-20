# sys-kernel/linux-firmware

### redistributable
Install non-free (but redistributable) firmware files, e.g. AMD GPU and Intel wireless network adapters firmware.

This flag should be disabled, unless there is a need for such firmware files.

### savedconfig
When enabled, only firmware files that are listed in the `/etc/portage/savedconfig/sys-kernel/linux-firmware` file will be installed into the target system.

This flag can be enabled to fine-tune a firmware that will be installed into the system.

### unknown-license
Install firmware files whose licenses aren't known, e.g. Sound Blaster 16 or 3COM 3C359 TokenLink Velocity adapter.

This flag should normally be disabled, unless there is a need for such firmware files.
