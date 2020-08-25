# dev-perl/Authen-SASL

### kerberos
Pull in the [dev-perl/GSSAPI](../dev-perl/GSSAPI.md) package as a dependency. Provide support for client part of the GSSAPI SASL algorithm, as described in RFC 2222 section 7.2.1.

This flag should be enabled if there is a need to handle GSSAPI SASL authentication in Perl, e.g. for LDAP.

### test
Execute the `make test` command after the main build is completed to run the test suite provided with the source code and check for regressions. This will extend the build time.

This flag should normally be disabled as it is mainly oriented towards the package maintainers, testers and developers.
