# dev-util/ninja

### doc
Execute a `ninja-build -v doxygen manual` command. Build an HTML documentation using doxygen and install it into a `/usr/share/doc/ninja-<VERSION>/html` directory.

It is safe to disable this flag.

### emacs
Build and install a Major Mode for an Emacs editor. Install a `ninja-mode.el` file into a `/usr/share/emacs/site-lisp` directory.

This flag should be enabled if there is a need to edit `.ninja` files using an Emacs editor. Otherwise, it is safe to disable.

### test
Build and execute test suite provided with a source code. This will extend a build time.

The flag should normally be disabled as it is only useful for the Gentoo team, testers or developers.

### vim-syntax
Install a `/usr/share/vim/vimfiles/syntax/ninja-<VERSION>.vim` and a `/usr/share/vim/vimfiles/ftdetect/ninja-<VERSION>.vim` files. Enable a syntax highlighting for `.ninja` files for the Vim editor.

It is safe to disable this flag, unless there is a need to edit Ninja files using Vim.

### zsh-completion
Install a `_ninja` ZSH script into a `/usr/share/zsh/site-functions` directory. Enable a ZSH completion support for the `ninja` command.

This flag should be enabled if the target system uses a ZSH (Z SHell), otherwise it safe to disable.
