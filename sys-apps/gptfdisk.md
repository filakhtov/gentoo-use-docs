# sys-apps/gptfdisk

### ncurses
Build and install the `cgdisk` tool - a curses-based user interface with a text-mode menuing system for GUID partition table (GPT) management.

It is safe to disable the flag.

### static
Append the `-static` option to the `LDFLAGS` variable for the duration of a build. Build and install a statically linked binaries: `gdisk`, `sgdisk` and `fixparts` (also `cgdisk` if the `ncurses` flag is enabled).

This flag should only be enabled if there is a need for the static binaries.
