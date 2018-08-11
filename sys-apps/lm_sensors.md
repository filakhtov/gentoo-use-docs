# sys-apps/lm_sensors

### contrib
Install additional sensosr configuration files into the `/usr/share/lm_sensors` directory for the `it8720`, `f71882fg` and `f71868a` monitoring chips.

This flag should be enabled if the target system has one of the chips mentioned above.

### sensord
Patch the `Makefile` file to enable a rule to build and install the `sensord` binary - a daemon for periodic sensors monitoring and alerting when a sensor alarm is signalled. Install SystemD and initd startup services.

It is safe to disable the flag.

### static-libs
Statically linked version of the `libsensors` library is build and installed by default, so this flag does nothing if enabled. When disabled, patch the `Makefile` file to remove the rule responsible for building the static library.

This flag should only be enabled if there is an explicit need for the static library.
