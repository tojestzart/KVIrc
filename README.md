# ![KVIrc-Midnight](https://github.com/kvirc/KVIrc/wiki/images/KVIrc-midnight.png) KVIrc

These are dependencies for kubuntu 19.10 or earlier
````
#!/bin/bash
sudo apt-get install doxygen libenchant-dev qtbase5-dev cmake-curses-gui extra-cmake-modules gettext \
             qttools5-dev libkf5i18n-dev qtmultimedia5-dev libqt5webkit5-dev libqt5svg5-dev git \
             libphonon4qt5-dev libphonon4qt5experimental-dev libkf5xmlgui-dev libkf5notifications-dev \
             libperl-dev libtheora-dev libvorbis-dev libssl-dev python3-dev libqt5x11extras5-dev \
             build-essential
 ````
Extra for advanced mode in ccmake:
````
#!/bin/bash
sudo apt-get install libaudiofile-dev graphviz
````

Solution for 
````
kvirc: error while loading shared libraries: libkvilib.so.5: cannot open shared object file: No such file or directory

[1]+  Kod wyjścia 127        kvirc

`````


````
-- Installing: /usr/local/lib/kvirc/5.0/modules/libkviupnp.so
-- Set runtime path of "/usr/local/lib/kvirc/5.0/modules/libkviupnp.so" to ""
-- Installing: /usr/local/lib/kvirc/5.0/modules/libkviurl.so
-- Set runtime path of "/usr/local/lib/kvirc/5.0/modules/libkviurl.so" to ""
-- Installing: /usr/local/lib/kvirc/5.0/modules/libkviuserlist.so
-- Set runtime path of "/usr/local/lib/kvirc/5.0/modules/libkviuserlist.so" to ""
-- Installing: /usr/local/lib/kvirc/5.0/modules/libkviwindow.so
-- Set runtime path of "/usr/local/lib/kvirc/5.0/modules/libkviwindow.so" to ""
-- Installing: /usr/local/lib/kvirc/5.0/modules/libkviperl.so
-- Set runtime path of "/usr/local/lib/kvirc/5.0/modules/libkviperl.so" to ""
-- Installing: /usr/local/lib/kvirc/5.0/modules/libkvipython.so
-- Set runtime path of "/usr/local/lib/kvirc/5.0/modules/libkvipython.so" to ""
-- Installing: /usr/local/lib/kvirc/5.0/modules/libkvispellchecker.so
-- Set runtime path of "/usr/local/lib/kvirc/5.0/modules/libkvispellchecker.so" to ""
````
solution 
````
sudo ldconfig
````

## Compile Your Own

If you want to compile KVIrc on your chosen platform, we have guides on how to do that for a few popular ones:

* [Linux](https://github.com/kvirc/KVIrc/wiki/installation)
* [macOS](https://github.com/kvirc/KVIrc/wiki/Compiling-KVIrc-on-macOS)
* [Windows](https://github.com/kvirc/KVIrc/wiki/Compiling-KVIrc-on-Windows)

## License

[![KVIrc GPLv2+](https://img.shields.io/badge/KVIrc-GPLv2+-blue.svg)](./COPYING)
[![OpenSSL](https://img.shields.io/badge/OpenSSL-Licence-orange.svg)](./doc/LICENSE-OPENSSL)
[![OpenSSL exception](https://img.shields.io/badge/OpenSSL-Exception-orange.svg)](./doc/LICENSE-OPENSSL)
