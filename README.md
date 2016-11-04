SBXG Manifests
==============

[![Build Status](https://travis-ci.org/sbxg/manifests.svg?branch=master)](https://travis-ci.org/sbxg/manifests)


SBXG (https://github.com/sbxg/sbxg) relies heavily on manifests files that
describe:
- which kernel revision must be used;
- which u-boot revision must be used;
- where are the kernel configuration files;
- where the boards' configuration files reside.

Each directory describes its own board and contains manifests named as it follows:
- `kernel type` (e.g. linux);
- `kernel version identifier` (optional);
- `kernel features` (optional).

The table below shows the supported boards.

| Board             | Kernel | Support        |
| ----------------- | ------ | -------------- |
| [Cubieboard1][1]  | Linux  | Good           |
| [Cubieboard2][1]  | Linux  | Good           |
| [Cubietruck][2]   | Linux  | Good           |
| [Cubieboard4][1]  | Linux  | Experimental   |
| [Cubieboard5][1]  | Linux  | Experimental   |


# Validation

Manifests are XML files, defined by the Document Type Definition (DTD) `manifest.dtd`.
The `validator` script is a python 3 script that uses the LXML python module
(`pip3 install lxml`) to validate all manifests files. This script can be used
for development to make sure valid manifests files are pushed. Travis checks every push
to make ensure manifests are valid.

This script checks, for each manifest:
- the syntactic correctness of the XML;
- its compliance to the defined DTD;
- that all URLs are reachable. `git ls-remote` is used under the hood the verify this point.


To install dependencies with `apt` (Debian/Ubuntu):

```bash
sudo apt-get install python3 python3-pip python-dev libxml2-dev libxslt1-dev zlib1g-dev 
sudo pip3 install lxml
```

Basic usage:
- `./validator --help`: for details;
- `./validator`: to check ALL XML files in the current directory and recursives directories;
- `./validator ./Cubietruck/*`: to check specific files (here all files in the Cubietruck/ directory.

[1]: http://cubieboard.org/
[2]: http://cubietruck.org/
