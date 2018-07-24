# app-text/xmlto

### latex
Pull the [app-text/passivetex](app-text/passivetex.md) and the [dev-tex/xmltex](../dev-tex/xmltex.md) packages as dependencies. A `PassiveTeX` tool is used by `xmlto` script for producing documents in DVI format from XML-DocBook. An `xmltex` tool is used to convert `TeX` files into the `DVI` format.

It is safe to disable this flag.

### text
Pull one of the following packages: the [virtual/w3m](../virtual/w3m.md), [www-client/lynx](../www-client/lynx.md) or [www-client/links](../www-client/links.md) as a dependency. These browsers can be used by `xmlto` to convert an `HTML` formatted document into a plain text file.

This flag can be safely disabled.
