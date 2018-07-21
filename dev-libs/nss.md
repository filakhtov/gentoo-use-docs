# dev-libs/nss

### cacert
Apply an additional patch to add a Class 1 and Class 3 certificates from the CACert Inc. association into a built-in trusted root certificates list. These certificates aren't included by default because procedures to obtain them aren't compatible with the Mozilla verification and auditing policies.

These certificates are considered insecure by various strict policies and so it is recommended to disable the flag, however it is safe to enable it if that's necessary.

### nss-pem
Download an additional source code for a PKCS#11 module to read certificates in PEM format, extract and move it into main build directory. Patch a `manifest.mn` file to build and install PEM module.

This flag should be enabled if there is a need to manage PEM formatted certificates via NSS, otherwise it can be safely disabled.

### utils
Build and install additional utilities: `addbuiltin`, `atob`, `baddbdir`, `btoa`, `certcgi`, `certutil`, `cmsutil`, `conflict`, `crlutil`, `derdump`, `digest`, `makepqg`, `mangle`, `modutil`, `multinit`, `nonspr10`, `ocspclnt`, `oidcalc`, `p7content`, `p7env`, `p7sign`, `p7verify`, `pk11mode`, `pk12util`, `pp`, `rsaperf`, `selfserv`, `shlibsign`, `signtool`, `signver`, `ssltap`, `strsclnt`, `symkeyutil`, `tstclnt`, `vfychain`, `vfyserv` and their respective MAN pages.

It is safe to disable the flag.
