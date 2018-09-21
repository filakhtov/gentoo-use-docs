# net-wireless/bluez

### alsa
Pass the `--enable-midi` option to the configure script. Enable support for the Low-Energy Bluetooth MIDI sequencers via the ALSA API.

This flag should only be enabled if there is a need to use MIDI Synthesizer that advertises the MIDI Primary Service over Bluetooth.

### btpclient
Pass the `--enable-btpclient` option to the configure script. Build and install the `btpclient` tool - a BTP (Bluetooth Test Protocol) client for qualification testing.

This flag should normally be disabled.

### cups
Pass the `--enable-cups` option to the configure script. Patch the `Makefile` files to point it to the correct location of the CUPS libraries. Provide an ability to use Bluetooth printers.

This flag should only be enabled if there is a need to print over Bluetooth.

### debug
Pass the `--enable-debug` option to the configure script. This will append the `-g` compiler option for the build process. Produce libraries and binaries with debugging symbols.

This flag should only be enabled if there is a need to debug the BlueZ itself or apps linked against its libraries.

### deprecated
Pass the `--enable-deprecated` option to the configure script. Build and install deprecated tools: `hciattach`, `hciconfig`, `hcitool`, `hcidump`, `rfcomm`, `sdptool`, `ciptool` (and `gatttool` if the `extra-tools` flag is enabled).

This flag should normally be disabled, unless there is a need for any of the deprecated tools.

### doc
Install additional documenation in the plain text format into the `/usr/share/doc/bluez-<VERSION>/` directory. Documentation include API descriptions, protocol formats, settings storage etc.

It is safe to disable the flag.

### experimental
Pass the `--enable-experimental` option to the configure script. Build and install the `pcsuite` experimental tool for Nokia OBEX PC Suite services.

This flag should only be enabled if there is a need to communicate with devices that support Nokia PC Suite services.

### extra-tools
Build and install additional tools, that aren't supported by upstream: the `gatttool` - a tool for Bluetooth Low Energy devices, and the `btmgmt` - a command-line interface of BlueZ for management.

It is safe to disable the flag.

### mesh
Pass the `--enable-mesh` option to the configure script. Enable Mesh networking support to enable an interoperable many-to-many mesh networking solution for Bluetooth Low Energy. Build and install the `meshctl` tool for provisioning and management of Mesh-based networks.

This flag should only be enabled if there is a need to support Mesh-networking.

### obex
Pass the `--enable-obex` option to the configure script. Enable the OBEX (OBject EXchange) protocol support that facilitates the exchange of binary objects between devices. Provide support for the Bluetooth Phone Book Access Profile (PBAP) that allows to exchange Phone Book objects and call history between carkits and mobile devices and IrMC profile - another method to transfer the phone book.

It is safe to disable the flag.

### readline
Pass the `--enable-client` option to the configure script and export the `ac_cv_header_readline_readline_h=yes` variable for it. Build and install `bluetoothctl` - an interactive bluetooth control tool, that depends on the `libreadline` library to provide history, completion and line editing features.

This flag should be enabled if there is a need to configure Bluetooth from command line.

### selinux
Pull the [sec-policy/selinux-bluetooth](../sec-policy/selinux-bluetooth.md) package as a dependency. Provide SELinux policies that allow BlueZ stack daemons to properly operate under a SELinux-enabled Kernel.

This flag should only ever be toggled system-wide, i.e. as part of a SELinux-enabled Portage profile.

### systemd
Pass the `--enable-systemd` option to the configure script. Install SystemD unit service files: `bluetooth.service`, `org.bluez.service`, `obex.service` and `org.bluez.obex.service`.

This flag should be enabled if the target system runs the SystemD init system.

### test
Prepare Python environment for running tests. Execute the `make check` command to run a test suite provided with the source code. This will extend a build time.

This flag should normally be disabled as it is mainly useful for the Gentoo team, testers or developers.

### test-programs
Pass the `--enable-test` option to the configure script. Install additional test tools: the `test-manager`, `test-gatt-profile`, `test-device`, `test-nap`, `test-adapter`, `test-network`, `ftp-client`, `map-client`, `example-advertisement`, `test-health`, `test-discovery`, `test-profile`, `simple-player`, `pbap-client`, `test-hfp`, `opp-client`, `simple-endpoint`, `monitor-bluetooth`, `test-health-sink`, `list-devices`, `simple-agent` and `test-sap-server` into the `/usr/lib/bluez/test` directory. Create symlinks for these tools into the `/usr/bin` directory with the `bluez-` prefix.

It is safe to disable the flag.

### udev
Pass the `--enable-udev` and the `--enable-sixaxis` options to the configure script. Build and install the `hid2hci` tool - a HID to HCI mode switching utility that is used by various Bluetooth devices and adapters from Apple, Dell, Logitech etc.

It is recommended to enable this flag.

### user-session
Provide an ability to spawn the individual per-user `obexd` daemon via SystemD user instance, instead of using shared system daemon. When disabled, apply a patch that resorts back to spawning single shared daemon that will be used by all users.

It is recommended to enable this flag for systems that use the SystemD daemon as an init system.
