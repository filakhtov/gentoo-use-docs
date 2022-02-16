# sys-kernel/installkernel

### grub
Install additional hook script `91-grub-mkconfig.install` into the `/etc/kernel/postinst.d` that will execute the `grub-mkconfig` tool to regenrate GRUB configuration any time the kernel is installed via the `make install` command.

This flag should only be enabled if the system uses GRUB as a boot loader.
