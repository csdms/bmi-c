[![Build Status](https://travis-ci.org/csdms/bmi-c.svg?branch=master)](https://travis-ci.org/csdms/bmi-c)
bmi-c
=====

C-Bindings for the Basic Modeling Interface

Build
-----
To build the BMI C-bindings and tests,

    $ mkdir _build && cd _build
    $ cmake ../ -DCMAKE_INSTALL_PREFIX=<path-to-installation>
    $ make

where `<path-to-installation>` is the base directory where you want to install
things (`/usr/local` is the default). To install,

    $ make install
