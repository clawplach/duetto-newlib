Duetto: A C++ compiler for the Web
==================================

Please report bugs on launchpad:
https://bugs.launchpad.net/duetto

Duetto libc build instructions
------------------------------

Building the duetto-enabled libc requires having the duetto compiler
and duetto-utils headers already installed in /opt/duetto. It also require
libcxx-duetto headers.

```
cd newlib
git clone <libcxx-duetto-repo> libcxx
mkdir build
cd build
../configure --host=duetto --with-cxx-headers=$PWD/../libcxx/include --prefix=/opt/duetto
make
make install
../build-bc-libs.sh
```

The last step is necessary since I've not been able (yet) to patch libtool to create
LLVM bitcode-base static libraries.
