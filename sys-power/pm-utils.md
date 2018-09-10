# sys-power/pm-utils

### alsa
Pull in the [media-sound/alsa-utils](../media-sound/alsa-utils.md) package as a dependency. It used to be a dependency for `65alsa` script but it has been removed. According to the ALSA dev team, all drivers that have power management support will save and restore their state correctly across a suspend or hibernate, and drivers that don't have power management support need to have their state saved, then unloaded before suspend, reloaded on wakeup, and then have their state restored.

This flag should be disabled.

### debug
Append the `PM_DEBUG="true"` variable to the Gentoo-specific configuration file for pm-utils to enable scripts to print (and log) each action as they performs it. This can also be done without reinstallation by modifying the `/etc/pm/config.d/gentoo` config.

This flag should be enabled to debug things like sleeping, hibernation, etc.

### ntp
Install an additional `90clock` script, into the `/etc/pm/sleep.d/` directory, that is responsible for saving realtime clock into hardware clock during sleep or hibernation and restoring it when resuming or waking up.

This flag should normally be disaled as any modern kernel will handle this task properly itself.
