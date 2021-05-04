# net-dialup/ppp

### activefilter
When the flag is disabled patch the `Makefile.linux` file to comment out the `FILTER=y` variable. Enable support for `acitev-filter` option that is used to specify a packet filter to be applied to data packets to determine which packets are to be regarded as link activity, and therefore reset the idle timer, or cause the link to be brought up in demand-dialling mode.

This flag should normally be disabled.

### atm
Patch the `Makefile.linux` file to uncomment the `HAVE_LIBATM=yes` variable. Build and install the `pppoatm.so` plugin to enable support for PPPoATM (Point-to-Point Protocol over ATM).

This flag can be safely disabled if there is no need for PPPoATM support.

### dhcp
Patch the `Makefile.linux` file to append the `dhcp` directory that contains external DHCP module to the `SUBDIRS` variable. Doing this will build and install the Netservers `dhcpc.so` client plugin. This plugin is a hybrid DHCP client and proxy server that allows a PPP server to request an IP address from a local or remote DHCP server on behalf of the client.

It is recommended to disable this flag, because it is very uncommon to use DHCP with PPP.

### eap-tls
Apply the patch that enables support for PPP EAP-TLS (Extensible Authentication Protocol over TLS) authentication protocol in `pppd`, which requires mutual authentication between a client and a server using client-side X.509 certificates. If the flag is disabled remove the patch that enables EAP-TLS authentication support for PPP.

This flag can be safely disabled.

### gtk
Execute the `make -f Makefile.linux` from the `contrib/pppgetpass` source subdirectory to build both `pppgetpass.gtk` and `pppgetpass.vt` tools and install them together with the `pppgetpass.sh` script (unter `pppgetpass` name) that automatically uses a GTK-based user interface to ask for a PAP password if running under the graphical desktop environment and falls back to simple terminal prompt if not. When the flag is disabled, execute the `make pppgetpass.vt` instead to build just a terminal-based prompt and install it under the `pppgetpass` name.

It is safe to disable this flag.

### ipv6
Patch the `Makefile.linux` file to uncomment the `HAVE_INET6` variable and add the `+ipv6` option to the `/etc/ppp/options` configuration file. Enable support for IPv6CP (Internet Protocol version 6 Control Protocol) and IPv6 protocols.

This flag should only be enabled if there is a need to establish PPP connection with IPv6 protocol support.

### pam
Patch the `Makefile.linux` file to uncomment the `USE_PAM=y` variable. Enable support for PAM stack to allow users to authenticate with their system credentials (username and password), and install the `/etc/pam.d/ppp` configuration file. As an example, this can be used in conjunction with LDAP (Lightweight Directory Access Protocol) user authentication.

This flag should normally be disabled.

### radius
Build and install the `radius.so`, `radattr.so` and `radrealms.so` plugins, their configuration and manual pages.

The RADIUS plugin for pppd permits pppd to perform PAP, CHAP, MS-CHAP and MS-CHAPv2 authentication against a RADIUS server instead of the usual `/etc/ppp/pap-secrets` or `/etc/ppp/chap-secrets` files. The radattr plugin for pppd provides an ability to store all attributes returned by the RADIUS server in the local file; for example, to use them with `ip-up` and `ip-down` scripts. When the flag is disabled, comment out the `SUBDIRS += radius` line from the `Makefile.linux` file in the `plugins` source subdirectory to avoid building and installing these plugins.

This flag should normally be disabled, unless there is a need to authenticate against RADIUS server when establishing a PPP connection.
