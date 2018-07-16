# sys-apps/hwids

### net
Pass the `NET=yes` (`no` when disabled) option to the `make` command. Install an `oui.txt` (Organizationally Unique Identifier) and an `iab.txt` (Individual Address Block) files. These files contain MAC address to vendor mappings.

It is safe to disable this flag.

### pci
Pass the `PCI=yes` (`no` if disabled) option to the `make` command. Install a `pci.ids` file containing IDs for PCI devices, their names and vendors. This file can be used by `lspci` for device identification.

This flag should be enabled if there is a need to use an `lspci` command from a [sys-apps/pciutils](pciutils.md) package. It can be safely disabled otherwise.

### udev
Pass the `UDEV=yes` (`no` when disabled) option to the `make` command. Execute a `udevadm hwdb --update` command after the main build is complete. Install Udev hardware database files and generates `hwdb.bin`.

It is recommended to enable this flag. Udev database can be used by the Udev itself and also by an `lspci` command if `udev` flag is enabled for a [sys-apps/pciutils](pciutils.md) package.

### usb
Pass the `USB=yes` (`no` if disabled) option to the `make` command. Install a `usb.ids` file containing IDs for USB devices, their names and vendors. This file is used by `usbutils` to identify USB devices.

This flag should be enabled if there is a need to use `usbutils`. It can be safely disabled otherwise.
