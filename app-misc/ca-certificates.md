# app-misc/ca-certificates

### cacert
Apply an additional patch to provide Class 1 and Class 3 certificates from CACert Inc. issuer. Install them into the `/usr/share/ca-certificates/cacert.org` directory. These certificates aren't trusted by the majority of the vendors because they aren't compliant with various verification and auditing policies.

This flag should only ever be enabled if there is a need to "trust" resources that have certificates signed by the CACert.

### insecure_certs
Does nothing when enabled and allow to install insecure certificates from WoSign and StartCom. If disabled, removes these certificates from an installation. These certificates are distrusted due to security incidents. See [Gentoo Bug #598072](https://bugs.gentoo.org/598072) for details.

It is recommended to disable the flag as vendors mentioned above aren't up to the scratch with the best security practices.
