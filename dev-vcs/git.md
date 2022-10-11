# dev-vcs/git

### blksha1
Pass the `BLK_SHA1=YesPlease` variable to the `make` command. Use the GIT's own SHA1 library (inspired by Mozilla's) instead of relying on the OpenSSL library to calculate SHA1 hashes.

It is safe to disable the flag.

### cgi
Only works if the `perl` flag is enabled. Execute the `make gitweb` command to generate the `gitweb` script - a Git web interface, written in Perl and can be used as a CGI, and install it into the `/usr/share/git` directory. Also create a compatibility symling to the `/usr/share/gitweb` directory.

This flag should be enabled if there is a need to run GIT web interface.

### curl
The `libcurl` library integration is enabled by default and is used by the `git fetch` and `git http-fetch` commands to downloads remote HTTP and HTTPS repositories and by the `git imap-send` command to upload a mailbox generated with the `git format-patch` command into an IMAP drafts folder. When disabled, pass the `NO_CURL=YesPlease` variable to the `make` command to disable the cURL integration.

It is recommended to enable this flag, unless there is absolutely no need to use aforementioned functionality.

### cvs
Build a set of tools to integrate with CVS repositories: `git cvsexportcommit` to export a commit from Git to a CVS checkout to merge patches from a Git repository, `git-cvsserver` - a CVS server emulator for Git, `git-cvsimport` to import a CVS repository into Git and either create a new repository, or incrementally import into an existing one. When disabled, pass the `NO_CVS=YesPlease` variable to the `make` command to disable the CVS integration.

This flag should be enabled if there is a need to migrate data between GIT and CVS repositories.

### doc
Download an archive with documentation sources, unpack it into the `Documentation` subdirectory and run the `make info` command there to generate additional documentation in the HTML format. Run the `make doc` command from source directory, generate documentation based on enabled features and install it into the `/usr/share/doc/git-<VERSION>` directory.

It is safe to disable the flag.

### gnome-keyring
Execute the `make` command from the `contrib/credential/libsecret` subdirectory to build the `git-credential-libsecret` binary to handle storing and providing usernames and passwords to Git using the `libsecret` library.

This flag should be enabled to integrate GIT with the GNOME Keyring.

### gpg
Pull in the [app-crypt/gnupg](../app-crypt/gnupg.md) package as a dependency. Provide an ability to cryptographically sign and verify commits, using the `git commit -S` and `git verify-commit` commands and tags using the `git tag -s` and `git verify-tag` commands respectively.

This flag should be enabled if there is a need to sign commits, e.g. for GitHub, GitLab, etc.

### highlight
Only works if the `cgi` flag is enabled. Pull in the [app-text/highlight](../app-text/highlight.md) pacakage as a dependency and use it to provide source code highlight feature for the gitweb frontend.

It is safe to disable the flag.

### iconv
When disabled, pass the `NO_ICONV=YesPlease` variable to the `make` command. Use the `libiconv` library to perform a character encoding translation, e.g. when formatting commit messages for displaying purposes and input or output encoding is not a UTF-8, or displaying messages from remote that aren't in native output encoding.

It is recommended to enable this flag to avoid issues with character encoding.

### mediawiki
Run the `make` command inside of the `contrib/mw-to-git` source subdirectory. Build and install the Git-Mediawiki - a project which aims the creation of a gate between git and mediawiki, allowing git users to push and pull objects from mediawiki just as one would do with a classic git repository.

It is safe to disable the flag.

### mediawiki-experimental
Only makes sense if the `mediawiki` flag is enabled. Apply experimental patches to improve Mediawiki support, however this will affect stability.

This flag should be enabled.

### nls
A Gettext library is used by default for localizing Git, e.g. providing an ability to translate programs messages into various languages based on the system locale settings. When disabled, pass the `NO_GETTEXT=YesPlease` variable to the `make` command to disable localization.

It is safe to disable the flag, unless there is a need to use a non-English language.

### pcre
Pass the `USE_LIBPCRE2=YesPlease` variable to the `make` command. Use the `libpcre2` library to provide support for Perl-compatible regular expressions for `git grep` command via the `-P` runtime switch. When disabled, GIT will respond with `fatal: cannot use Perl-compatible regexes when not compiled with USE_LIBPCRE` if trying to pass the `-P` flag.

It is safe to disable the flag.

### perforce
Use the Python integration to provide an ability to import from and submit to Perforce repositories via the `git p4` command. When disabled, pass the `NO_PYTHON=YesPlease` variable to the `make` command.

The flag can be safely disabled.

### perl
Perl integration is used by default to provide additional features, like preparing a partial commit using `git add -i` and `git add -p`, interacting with svn repositories with `git svn`, etc. When disabled, pass the `NO_PERL=YesPlease` variable to the `make` command.

It is safe to disable the flag.

### ppcsha1
Only works when the `blksha1` flag is disabled. Use the GIT's own SHA1 library (inspired by Mozilla's) and optimized for the PowerPC platform, instead of relying on the OpenSSL library to calculate SHA1 hashes.

It is recommended to enable this flag on PowerPC platforms.

### safe-directory
When this flag is disabled, apply the patch that disables git `safe.directory` check, i.e. allows to use directories that are owned by a different user when the `GIT_TEST_ASSUME_DIFFERENT_OWNER` environment variable is set.

This flag should be enabled.

### selinux
Pull in the [sec-policy/selinux-git](../sec-policy/selinux-git.md) package as a dependency to provide necessary SELinux policies for git to properly operate under a SELinux-restricted kernel.

This flag should only ever be toggled system-wide, e.g. as part of the SELinux-enabled Portage profile.

### subversion
When disabled, pass the `NO_SVN_TESTS=YesPlease` variable to the `make` command. Build and install the `svn-fe` tool to convert an SVN "dumpfile" to a fast-import stream. Provide an ability to move changesets between Subverion and GIT repositories using the `git svn` command.

It is safe to disable the flag, unless there is a need to access SVN repositories with GIT.

### test
Decide which tests to disable based on the enabled flags and append the `.DISABLED` prefix to their file names to skip. Execute the `make clean`, `make test` and `make aggregate-results` commands to run the test suite provided with the source code and collect results after the main build is completed. This will extend a build time.

This flag should normally be disabled, because it is mainly useful for the Gentoo team, testers or developers.

### tk
Build the portable graphical interface to Git that uses the Tcl/Tk toolkit and can be accesse via the `git gui` command, allowing users to make changes to their repository by making new commits, amending existing ones, creating branches, performing local merges, and fetching/pushing to remote repositories. When disabled, pass the `NO_TCLTK=YesPlease` variable to the `make` command to disable GUI.

It is safe to disable the flag.

### webdav
Use the `libexpat` library to provide a remote lock management ability for the WebDAV (Web Distributed Authoring and Versioning) protocol when pushing changes to a GIT repository over an HTTP using the `git http-push` command. When disabled, pass the `NO_EXPAT=YesPlease` variable to the `make` command.

It is safe to disable the flag, however pushing to GIT repositories over HTTP won't work.

### xinetd
Install the `git-daemon.xinetd` config into the `/etc/xinetd.d` directory. Provide an ability to run the `git-daemon` daemon, that provides an access to repositories over the `git://` protocol, behind the xinetd (extended Internet daemon) to provide access control and on-demand daemon launch.

This flag can be safely disabled.
