# app-alternatives/sh

### bash
Use the [app-shells/bash](../app-shells/bash.md) package as a provider for `sh`. Use the Bourne Again Shell as a shell interpreter. This is a default choice.

### busybox
Use the [sys-apps/busybox](../sys-apps/busybox.md) package as a provider for `sh`. Use minimal shell environment provided by the BusyBox project.

### dash
Use the [app-shells/dash](../app-shells/dash.md) package as a provider for `sh`. Use Debian Almquist shell as a shell interpreter. It is POSIX compatible but not Bash compatible.

### ksh
Use the [app-shells/ksh](../app-shells/ksh.md) package as a provider for `sh`. Use KornShell developed by David Korn at Bell Labs as a shell interpreter.

### lksh
Use the [app-shells/mksh](../app-shells/mksh.md) package with the `lksh` flag enabled as a provider for `sh`. Use legacy KornShell built on mksh, which is intended exclusively for running legacy shell scripts.

### mksh
Use the [app-shells/mksh](../app-shells/mksh.md) package as a provider for `sh`. Use MirBSD™ Korn Shell, an actively developed free implementation of the Korn Shell.
