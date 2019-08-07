# sys-kernel/linux-firmware

### initramfs
Combine and install an AMD CPU microcode into the `/boot/amd-uc.img` file, mounting the `/boot` directory first if needed. This early initrd image is loaded by the GRUB bootloader during an early boot.

This flag should only be enabled if there is a need to apply the AMD microcode during an early boot.

### redistributable
Install non-free (but redistributable) firmware files, e.g. AMD GPU and Intel wireless network adapters firmware.

This flag should be disabled, unless there is a need for such firmware files.

### savedconfig
When enabled, only firmware files that are listed in the `/etc/portage/savedconfig/sys-kernel/linux-firmware` file will be installed into the target system.

This flag can be enabled to fine-tune a firmware that will be installed into the system.

### unknown-license
Install firmware files whose licenses aren't known, e.g. Sound Blaster 16 or 3COM 3C359 TokenLink Velocity adapter.

This flag should normally be disabled, unless there is a need for such firmware files.
