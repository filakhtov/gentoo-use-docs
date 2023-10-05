# sys-devel/llvm-toolchain-symlinks

### multilib-symlinks
Install prefixed symlinks, i.e. `x86_64-pc-linux-gnu-ar`, `x86_64-pc-linux-gnu-nm`, `i686-pc-linux-gnu-ar` and so forth for every supported and enabled ABI.

This flag should only be enabled on multilib systems.

### native-symlinks
Install native symlinks for `addr2line`, `ar`, `dlltool`, `nm`, `objcopy`, `objdump`, `ranlib`, `readelf`, `size`, `strings`, `strip`, `windres` tools pointing to the respective LLVM toolchain provided ones (`llvm-addr2line`, `llvm-ar`, etc).

This flag should normally be enabled.
