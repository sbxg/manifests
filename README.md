SBXG Manifests
==============

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
| [Sabre SD][3]     | Linux  | Experimental   |


[1]: http://cubieboard.org/
[2]: http://cubietruck.org/
[3]: http://www.nxp.com/products/microcontrollers-and-processors/arm-processors/i.mx-applications-processors-based-on-arm-cores/i.mx-6-processors/i.mx6qp/sabre-board-for-smart-devices-reference-design-based-on-the-i.mx-6-series:RDIMX6SABREBRD
