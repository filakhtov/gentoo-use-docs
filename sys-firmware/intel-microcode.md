# sys-firmware/intel-microcode

### hostonly
This flag only works together with a `split-ucode` flag. Install only microcode for the target machine CPU.

This flag can be enabled to save space.

### initramfs
Generate early loadable initramfs file that contains microcode and install it into the `/boot/intel-uc.img` image file. Bootloader is still has to be pointed to this image file manually.

This flag can be enabled to automatically install and generate initramfs file.

### split-ucode
Install separate microcode files for different processor types and revisions.

It is recommended to enable this flag to have more granular control over microcode loading.

### vanilla
When enabled, only microcode that is included in the Intel's official tarball will be installed, instead of installing a broader microcode collection that is maintained by the Gentoo maintainers.

It is _generally_ safe to disable the flag.
