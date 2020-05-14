# sys-apps/lm-sensors

### contrib
Install various configuration files for a variety of different motherboards contributed by users. These configs have proper voltage, RPM and temperature adjustments, both actual readings and minimum or maximum threshold where applicable, that otherwise will provide wrong information.

It is safe to disable this flag, however it can be useful for systems that display wrong details and have contributed config.

### sensord
Adjust the build system to properly compile and install the `sensord` binary and various init files for it. `sensord` is a daemon that can be used to periodically log sensor readings from hardware health-monitoring chips and to alert when a sensor alarm is signalled, for example, if a fan fails, a temperature limit is exceeded, etc.

It is safe to disable the flag.

### static-libs
A statically linked version of the `libsensors` library is built and installed by default, so when this flag is enabled nothing happens. When disabled, however, a build script will be patched in order to disable building it.

This flag should normally be disabled, unless there is an explicit need for static library.
