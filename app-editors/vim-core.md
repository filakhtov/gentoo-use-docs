# app-editors/vim-core

### acl
Pass the `--enable-acl` option to the configure script. Provide an ability to copy ACLs from an original edited file into a backup or newly created file.

It is recommended to toggle this flag system-wide, otherwise there is high risk of losing ACLs.

### minimal
Remove syntax highlight configs for all but most important config files, macroses, tutor and so on to save space and minimize installation.

This flag is primarily introduced to save space on LiveCD and should normally be disabled.

### nls
Pass the `--enable-nls` option to the configure script. Provide an ability to translate program messages and prompts into various languages using a Gettext library.

It is safe to disable the flag, unless there is a need to use non-English languages.
