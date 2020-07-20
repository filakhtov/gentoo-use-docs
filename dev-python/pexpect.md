# dev-python/pexpect

### doc
Execute the `make html` command in the `doc` source subdirectory to generate additional documentation in the HTML format and install it into the `/usr/share/doc/pexpect-<VERSION>/html` directory. Documentation includes developer docs, FAQ, common known issues, API reference, etc.

It is safe to disable the flag.

### examples
Install additional example scripts into the `/usr/share/doc/pexpect-<VERSION>/examples` directory. A script that checks the Apache server status on the remote host over the SSH, an example of how to control curses based application, a script that allows to ssh to a group of servers and control them as if they were one, etc.

The flag can be safely disabled.


### test
Execute the `pytest` command for each enabled Python target after the main build is completed. Run the test suite provided with the source code. This will extend the build time.

This flag is primarily oriented towards developers, testers or the Gentoo team and should normally be disabled.
