# sys-apps/sandbox

### nnp
Patch the `sandbox.c` file to enable `PR_SET_NO_NEW_PRIVS` feature which blocks setuid/setguid programs (such as `sudo`) from gaining elevated privileges inside of the sandbox.

This flag should be enabled to improve security.
