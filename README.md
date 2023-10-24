# This is the PHREEQC fork used in the mobile app PHREEQC plus

## Changes in this fork

* the working directory is /data/data/cz.p/files/ (PHREEQC plus app)
* added the stamp defining the release

## Compilation

* set paths to source directories and to Release directory (create if not present)
* add entry -> ANDROID_ABI arm64-v8a, armeabi-v7a, x86_64, x86 (the desired architecture)
* add entry -> ANDROID_NDK path to Android NDK r10e
* configure - choose cmake toolchain
* tick PHREEQC_USE_GMP
* configure
* fill in the red fields - path to gmp.h and libgmp.a for the same architecture
* configure
* generate
* open the Release directory, fild all flags.make and link.txt
* add -pie to all these file
* cd Release & mingw32-make (or make - in WSL)

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
