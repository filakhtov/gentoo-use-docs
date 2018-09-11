# gnome-base/gconf

### debug
Pass the `--enable-debug=yes` option to the configure script. Enable additional runtime debugging messages, including warnings where GConf would normally just fail silently.

This flag should only be enabled for debugging purposes.

### introspection
Pass the `--enable-introspection` option to the configure script. Generate and install the `GConf-2.0.gir` GIR metadata file to provide dynamic bindings for the `libgconf-2` library to languages other than C using the GObject Introspection framework.

It is safe to disable the flag.

### ldap
Pass the `--with-openldap` option to the configure script. Build and install the `libgconfbackend-evoldap` library - a special-purpose GConf backend which enables default mail accounts, addressbooks and calendars for Evolution to be configured using each user's LDAP entry.

This flag should only be enabled if there is a need to automatically populate Evolution data from LDAP server.

### policykit
Pass the `--enable-defaults-service` option to the configure script. Enable D-Bus service that is using Polkit for privilege management and is listening on `org.gnome.GConf.Defaults` to provide an ability to change system-wide defaults or mandatory settings from a user session, instead of manually editing XML configuration files.

This flag should be enabled if there is a need to modify system-wide defaults via GConf.
