# This is the PHREEQC fork used in the mobile app PHREEQC plus

## Changes in this fork

* cross compilation for the PHREEQC plus app
* added the stamp defining the release (class_main.cpp)

## Cross-compilation

export CC=/path/to/android-ndk/toolchains/llvm/prebuilt/linux-x86_64/bin/armv7a-linux-androideabi33-clang
export CXX=/path/to/android-ndk/android-ndk-r25b/toolchains/llvm/prebuilt/linux-x86_64/bin/armv7a-linux-androideabi33-clang++

* cross compile libgmp (optional) - get the sources from https://gmplib.org/download/gmp/gmp-6.3.0.tar.xz, untar, configure & install
./configure --with-pic --with-cxx --host=armv7a-linux-androideabi33 --prefix=/path/to/install/gmp_arm

* switch to phreeqc sources, configure

cmake .. -DCMAKE_INSTALL_PREFIX=/path/to/install/phreeqc_arm -DPHRQC_USE_GMP=ON -DGMP_LIBRARY=/path/to/gmp_arm/lib/libgmp.a -DGMP_INCLUDE_PATH=/path/to/gmp_arm/include

* change -rdynamic to -fPIC -static-libstdc++ in link.txt
* change CXX_FLAGS = -fPIC in flags.make
make install

* for the other architectures just change the cross-compiler (aarch64-linux-android33-clang, aarch64-linux-android33-clang++ / i686-linux-android33-clang, i686-linux-android33-clang++, x86_64-linux-android33-clang, x86_64-linux-android33-clang++)

# ORIGINAL DESCRIPTION:

# PHREEQC

## Description

PHREEQC Version 3 is a computer program written in the C++ programming language 
that is designed to perform a wide variety of aqueous geochemical calculations. 
PHREEQC implements several types of aqueous models including two ion-association aqueous models. 

## Disclaimer

This software is preliminary or provisional and is subject to revision. It is
being provided to meet the need for timely best science. The software has not
received final approval by the U.S. Geological Survey (USGS). No warranty,
expressed or implied, is made by the USGS or the U.S. Government as to the
functionality of the software and related material nor shall the fact of release
constitute any such warranty. The software is provided on the condition that
neither the USGS nor the U.S. Government shall be held liable for any damages
resulting from the authorized or unauthorized use of the software.
