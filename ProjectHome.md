# Introduction #

This project is a spin-off from https://code.google.com/p/nfc-tools/ to maintain libfreefare development on its own repository.

The _libfreefare_ project aims to provide a convenient API for MIFARE card manipulations.

If you are new to _libfreefare_, you should browse its dedicated wiki page[¹] to collect useful information and have a look to our forum[²].

This project is part of the nfc-tools, you can find more info on them on the nfc-tools wiki[³] and nfc-tools project[⁴]

# Feature matrix #
## Tags ##
| MIFARE Classic 1k | Supported |
|:------------------|:----------|
| MIFARE Classic 4k | Supported |
| MIFARE DESFire 2k | Supported |
| MIFARE DESFire 4k | Supported |
| MIFARE DESFire 8k | Supported |
| MIFARE DESFire EV1 | Supported |
| MIFARE Mini | Not supported |
| MIFARE Plus S 2k | Not supported |
| MIFARE Plus S 4k | Not supported |
| MIFARE Plus X 2k | Not supported |
| MIFARE Plus X 4k | Not supported |
| MIFARE Ultralight | Supported |
| MIFARE UltralightC | Supported |

## Specifications ##
| Mifare Application Directory (MAD) v1 | Supported |
|:--------------------------------------|:----------|
| Mifare Application Directory (MAD) v2 | Supported |
| Mifare Application Directory (MAD) v3 | Supported (part of Mifare DESFire support) |

# Installation #
You can use released version (see **Download** section) or development version:

First you have to checkout sources:
```
git clone https://code.google.com/p/libfreefare/
cd libfreefare
```

Before compile it, remember to run
```
autoreconf -vis
```

Once fetched, you can now compile **libfreefare** using usual autotools way:

```
./configure --prefix=/usr
make
sudo make install
```

# Debug #
In order to debug using gdb, you need to compile with some CFLAGS:
```
CFLAGS="-g -Wall -pedantic -O0 -ggdb" ./configure --prefix=/usr
make clean all
```

To simply view transfer trace between PCD and PICC:
```
./configure --enable-debug
make clean all
```

To debug an example (e.g. mifare-classic-write-ndef), you need to run the following command:
```
libtool --mode=execute gdb examples/mifare-classic-write-ndef
```

# Links #
  * `[1]` **Dedicated wiki page**: http://nfc-tools.org/index.php?title=Libfreefare
  * `[2]` **Forum**: http://www.libnfc.org/community
  * `[3]` **Official wiki**: http://nfc-tools.org/
  * `[4]` **nfc-tools project**: http://nfc-tools.googlecode.com