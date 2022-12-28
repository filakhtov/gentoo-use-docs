# awk

### busybox
Use the [sys-apps/busybox](../sys-apps/busybox.md) package as a provider for awk. This is a minimal limited version of awk provided by BusyBox.

### gawk
Use the [sys-apps/gawk](../sys-apps/gawk.md) package as a provider for awk. Reference GNU awk implementation. This is the default choice.

### mawk
Use the [sys-apps/mawk](../sys-apps/mawk.md) package as a provider for awk. An (often faster than gawk) awk-interpreter.

### nawk
Use the [sys-apps/nawk](../sys-apps/nawk.md) package as a provider for awk. This is the version of awk described in The AWK Programming Language, by Al Aho, Brian Kernighan, and Peter Weinberger (Addison-Wesley, 1988, ISBN 0-201-07981-X).

### split-usr
If the flag is enabled some of the produced libraries will be installed into the `/lib` directory, instead of the `/usr/lib` directory, so that they are available during the early boot when the `/usr` partition is not yet mounted.

This flag is necessary to boot the system that has separated `/usr` partition, but otherwise can be safely disabled.
