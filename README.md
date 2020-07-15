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
Extra (not completed with abadoned packages) for advanced mode in ccmake:
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
solution for

````
[100%] Automatic MOC for target kvispellchecker
cd /home/lsd/KVIrc/wydane/src/modules/spellchecker && /usr/bin/cmake -E cmake_autogen /home/lsd/KVIrc/wydane/src/modules/spellchecker/CMakeFiles/kvispellchecker_autogen.dir/AutogenInfo.json Debug
make[2]: Opuszczenie katalogu '/home/lsd/KVIrc/wydane'
[100%] Built target kvispellchecker_autogen
make -f src/modules/spellchecker/CMakeFiles/kvispellchecker.dir/build.make src/modules/spellchecker/CMakeFiles/kvispellchecker.dir/depend
make[2]: Wejście do katalogu '/home/lsd/KVIrc/wydane'
cd /home/lsd/KVIrc/wydane && /usr/bin/cmake -E cmake_depends "Unix Makefiles" /home/lsd/KVIrc /home/lsd/KVIrc/src/modules/spellchecker /home/lsd/KVIrc/wydane /home/lsd/KVIrc/wydane/src/modules/spellchecker /home/lsd/KVIrc/wydane/src/modules/spellchecker/CMakeFiles/kvispellchecker.dir/DependInfo.cmake --color=
make[2]: Opuszczenie katalogu '/home/lsd/KVIrc/wydane'
make -f src/modules/spellchecker/CMakeFiles/kvispellchecker.dir/build.make src/modules/spellchecker/CMakeFiles/kvispellchecker.dir/build
make[2]: Wejście do katalogu '/home/lsd/KVIrc/wydane'
make[2]: Nie ma nic do zrobienia w 'src/modules/spellchecker/CMakeFiles/kvispellchecker.dir/build'.
make[2]: Opuszczenie katalogu '/home/lsd/KVIrc/wydane'
[100%] Built target kvispellchecker
make[1]: Opuszczenie katalogu '/home/lsd/KVIrc/wydane'
/usr/bin/cmake -E cmake_progress_start /home/lsd/KVIrc/wydane/CMakeFiles 0
make -f CMakeFiles/Makefile2 preinstall
make[1]: Wejście do katalogu '/home/lsd/KVIrc/wydane'
make[1]: Nie ma nic do zrobienia w 'preinstall'.
make[1]: Opuszczenie katalogu '/home/lsd/KVIrc/wydane'
Install the project...
/usr/bin/cmake -P cmake_install.cmake
-- Install configuration: "Debug"
-- Installing: /usr/local/share/applications/kvirc.desktop
CMake Error at data/applnk/cmake_install.cmake:49 (file):
  file INSTALL cannot copy file
  "/home/lsd/KVIrc/wydane/data/applnk/kvirc.desktop" to
  "/usr/local/share/applications/kvirc.desktop": Permission denied.
Call Stack (most recent call first):
  data/cmake_install.cmake:42 (include)
  cmake_install.cmake:42 (include)


make: *** [Makefile:99: install] Błąd 1
lsd@lsd-Latitude:~/KVIrc/wydane$ 
````
````
sudo make install
````

##  Debugging

Command to properly set KVIrc inside GDB is:

````
user@computer:~$ gdb kvirc
````
then you should see 

````
GNU gdb (Ubuntu 9.1-0ubuntu1) 9.1
Copyright (C) 2020 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<http://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from kvirc...
(gdb) 
````
last step is to type command :
````
(gdb) r
````
then you should see :

````
Starting program: /usr/local/bin/kvirc 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".
[New Thread 0x7fffed27a700 (LWP 3016)]
[New Thread 0x7fffe7f63700 (LWP 3017)]
[New Thread 0x7fffe6404700 (LWP 3018)]
[New Thread 0x7fffe5c03700 (LWP 3019)]
[New Thread 0x7fffe5402700 (LWP 3020)]
[New Thread 0x7fffe4c01700 (LWP 3021)]
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
