[![DOI](https://zenodo.org/badge/27887433.svg)](https://zenodo.org/badge/latestdoi/27887433)
[![Build and Test](https://github.com/csdms/bmi-c/actions/workflows/test.yml/badge.svg)](https://github.com/csdms/bmi-c/actions/workflows/test.yml)
[![Anaconda-Server Badge](https://anaconda.org/conda-forge/bmi-c/badges/version.svg)](https://anaconda.org/conda-forge/bmi-c)
[![Anaconda-Server Badge](https://anaconda.org/conda-forge/bmi-c/badges/platforms.svg)](https://anaconda.org/conda-forge/bmi-c)
[![Anaconda-Server Badge](https://anaconda.org/conda-forge/bmi-c/badges/downloads.svg)](https://anaconda.org/conda-forge/bmi-c)

# bmi-c

C bindings for the CSDMS [Basic Model Interface](https://bmi-spec.readthedocs.io).


## Build/Install

The C BMI bindings can be built on Linux, macOS, and Windows.
Instructions are given below.

**Prerequisites:**
* A C compiler
* CMake

Alternately,
[conda binaries](https://anaconda.org/conda-forge/bmi-c)
have been built for Linux, macOS, and Windows.
Install the C BMI bindings (no build needed)
into an Anaconda distribution with

    conda install bmi-c -c conda-forge

### Linux and macOS

To install the C BMI bindings from source with cmake, run

    mkdir _build && cd _build
    cmake .. -DCMAKE_INSTALL_PREFIX=<path-to-installation>
    make install

where `<path-to-installation>` is the base directory
in which to install the bindings (`/usr/local` is the default).

The installation will look like:

```bash
.
|-- include
|   `-- bmi.h
`-- lib
    `-- pkgconfig
        `-- bmic.pc
```

### Windows

An additional prerequisite is needed for Windows:

* Microsoft Visual Studio 2017 or Microsoft Build Tools for Visual Studio 2017

To configure and install the C BMI bindings from source with cmake,
run the following in a [Developer Command Prompt](https://docs.microsoft.com/en-us/dotnet/framework/tools/developer-command-prompt-for-vs)

    mkdir _build && cd _build
    cmake .. ^
	  -G "NMake Makefiles" ^
	  -DCMAKE_INSTALL_PREFIX=<path-to-installation> ^
	  -DCMAKE_BUILD_TYPE=Release
	cmake --build . --target install --config Release

where `<path-to-installation>` is the base directory
in which to install the bindings (`"C:\Program Files (x86)"` is the default;
note that quotes and an absolute path are needed).


## Use

To write a BMI for a model,
include the `bmi.h` header and implement all the BMI functions
included in the interface defined therein.
BMI functions that aren't used
(e.g., `get_grid_x` for a uniform rectilinear grid)
can simply return the BMI_FAILURE status code.
A sample implementation is given in the
https://github.com/csdms/bmi-example-c
repository.
