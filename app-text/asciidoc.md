# app-text/asciidoc

### examples
Install additional examples on how to build a website using the `asciidoc` tool into the `/usr/share/doc/asciidoc-<VERSION>` directory.

It is safe to disable the flag.

### graphviz
Pull the [media-gfx/graphviz](../media-gfx/graphviz.md) package as a dependency. This will provide a Graphiz filter for AsciiDoc to draw graphs using a descriptions in a simple text language.

This flag should be enabled if there is a need to produce graphs.

### highlight
Pull additional packages as a dependency to enable syntax highlight features. AsciiDoc can use the GNU source-highlight and the Pygments Python syntax highlighter.

This flag should be enabled if there is a need for syntax highlighting.

### test
Execute the `testasciidoc.py` from the `tests` source directory. Run a test suite provided with the source code after the main build is completed. This will extend a build time.

This flag should normally be disabled. It is mainly used by the Gentoo team, testers and developers.
