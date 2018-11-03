# net-misc/telnet-bsd

### nls
This flag does nothing and should normally be disabled.

### xinetd
Install additional `telnetd` configuration file for the xinetd (Extended Internet Service Daemon) into the `/etc/xinetd.d` directory to provide an ability to launch `in.telnetd` server for handling incoming telnet connections.

This flag should only ever be enabled if there is a need to run the telnet server behind the xinetd daemon.
