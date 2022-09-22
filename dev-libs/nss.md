# dev-libs/nss

### cacert
Apply an additional patch to add a Class 1 and Class 3 certificates from the CACert Inc. association into a built-in trusted root certificates list. These certificates aren't included by default because procedures to obtain them aren't compatible with the Mozilla verification and auditing policies.

These certificates are considered insecure by various strict policies and so it is recommended to disable the flag, however it is safe to enable it if that's necessary.

### test
Execute the `all.sh` script from the `tests` directory after the main build is completed to run the test suite provided with the source code and check for any regressions. This will extend the build time.

This flag should normally be disabled, because these tests are primarily oriented towards the developers, maintainers and testers.

### utils
Build and install additional utilities: `addbuiltin`, `atob`, `baddbdir`, `btoa`, `certcgi`, `certutil`, `cmsutil`, `conflict`, `crlutil`, `derdump`, `digest`, `makepqg`, `mangle`, `modutil`, `multinit`, `nonspr10`, `ocspclnt`, `oidcalc`, `p7content`, `p7env`, `p7sign`, `p7verify`, `pk11mode`, `pk12util`, `pp`, `rsaperf`, `selfserv`, `shlibsign`, `signtool`, `signver`, `ssltap`, `strsclnt`, `symkeyutil`, `tstclnt`, `vfychain`, `vfyserv` and their respective MAN pages.

It is safe to disable the flag.
