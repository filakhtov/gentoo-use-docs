# sys-firmware/ipxe

### binary
Download and install prebuilt firmware binaries instead of compiling from a source code.

It is generally recommended to enable this flag to avoid incompatibility issues.

### efi
Build (if the `binary` flag is disabled) and install the `ipxe.efi` binary to support PXE (Preboot eXecution Environment) booting from within the EFI (Extensible Firmware Interface) firmware.

This flag should be enabled on modern, EFI-based hardware.

### ipv6
Define the `NET_PROTO_IPV6` macro in local build config to enable support for the IPv6 protocol and allow network booting from IPv6 capable servers.

This flag should be enabled if there is a need to boot using an IPv6-enabled server.

### iso
Build (if the `binary` flag is disabled) and install the `ipxe.iso` ISO bootable disk image that can be used to run iPXE boot firmware from CD/DVD disc, instead of directly from firmware.

It is safe to disable the flag, unless there is a need for bootable ISO image.

### lkrn
Build (if the `binary` flag is disabled) and install the `ipxe.lkrn` standard firmware binary that can be directly loaded via Linux kernel boot-loaders (e.g. GRUB or LiLo) and can use an `ipxe` script embedded directly into the firmware itself, passed as command line arguments, or by passing a script as an initrd (aka initramfs) file.

It is safe to disable this flag, unless there is a need for such functionality.

### qemu
Build (if the `binary` flag is disabled) and install a number of `rom` firmware files that provide PXE-capabilities for early booting on QEMU platform using standard network adapters: `e1000`, `eepro100`, `ne2k`, `pcnet`, `rtl8139` and `virtio`.

This flag should be enabled if there is a need to run iPXE from QEMU virtual machines.

### savedconfig
Only makes sense if the `binary` flag is disabled. Use the `/etc/portage/savedconfig/sys-firmware/ipxe` saved configuration file with custom defined build settings.

This flag should normally be disabled.

### undi
Build (if the `binary` flag is disabled) and install the `undionly.kpxe` chainloader firmware that can be used by machines that already have PXE and can download iPXE over the network for extended features.

This flag should normally be disabled.

### usb
Build (if the `binary` flag is disabled) and install the `ipxe.usb` firmware that can be used for creating a bootable USB thumb drive with the iPXE environment.

It is safe to disable the flag.

### vmware
Build (if the `binary` flag is disabled) and install a number of `rom` and `mrom` files that provide PXE-capabilities for early booting using VMware standard network adapters: `e1000`, `e1000e`, `vlance`, `vmxnet3`.

This flag should be enabled if there is a need to use iPXE with VMWare, or other platform that provides VMWare-like virtual network adapters.
