# x11-misc/xdg-utils

### doc
Generate additional documentation in the HTML format using the xmlto tool and install it into the `/usr/share/doc/xdg-utils-<VERSION>/html` directory. Documentation contains the list of installed XDG commands, their description, list of options they support and a meaning of each option.

It is safe to disable the flag.

### perl
Pull in the [dev-perl/File-MimeInfo](../dev-perl/File-MimeInfo.md) package to enable the xdg-open utility to use XDG MIME Applications without a desktop environment. Trying to run the xdg-open tool with this flag disabled from outside of the DE will fall back to using the file util which does not implement the XDG standard.

This flag should be enabled if there is a need to invoke XDG MIME Applications via the xdg-open util outside of the DE.
