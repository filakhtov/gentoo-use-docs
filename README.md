# gentoo-use-docs
A missing documentation for Gentoo USE flags

I'm a seasoned Gentoo user. I have a variety of things running on it: desktop workstations, laptops, servers, containers, even HP ThinClient that pretends to be a home gateway with wireless access point functionality.

Because Gentoo is a rolling release, I rarely have to build everything from scratch. Recently, I have got new hardware and needed to build an OS for it. Every time I have to build Gentoo, I find myself deep into documentation, mailing lists or source code of various tools, trying to find what each particular flag is doing and whether I need to enable it for my current use case.

This mainly happens, because Gentoo's existing documentation on USE flags is quiet brief and often times there is no package specific description for flags so you end up with something like:

> bzip2 Use the bzlib compression library

Which is great, but does not answer how this particular package will use `bzip2` dependency. This is why I decided to start this project: to document concrete use cases for as many packages as I can. My hope would be that it will became viral and together with other Gentoo community members we can get better understanding of ecosystem.

### Contribution
Simply fork, make your changes/additions and create a PR!

### License
This repository is covered by Unlicense, because I'm too bored to get into licensing politics, sorry.
