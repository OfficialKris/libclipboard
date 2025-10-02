libclipboard [![Linux/OS X Build Status](https://travis-ci.org/jtanx/libclipboard.svg?branch=master)](https://travis-ci.org/jtanx/libclipboard) [![Win32 Build status](https://ci.appveyor.com/api/projects/status/r1oanfx5kd18xfxa?svg=true)](https://ci.appveyor.com/project/jtanx/libclipboard)
=========

> [!IMPORTANT]
> This fork provides maintenance to keep the library compiling and working properly. To see specific changes, view commit log.
>
> As opposed to other clipboard libraries, this library has no dependencies and is quite minimal (under 2k lines of code).

A cross-platform clipboard library.

## Currently supported actions
* Checking clipboard data ownership
* Clearing clipboard
* Retrieving/setting text (UTF-8)

## Supported platforms
* Linux (X11)
* MacOS (Cocoa)
* Windows

## Platforms to be supported in the future
> [!NOTE]
> Only setting and reading the clipboard from the same application works currently.
>
> Reading from other applications does not work on Wayland right now.
* Linux (Wayland)

## Requirements
* cmake
* make
* c99 compiler (gcc/clang/msvc)
* gtest & g++ >= 4.7 (optional - for unit testing)
* libxcb-dev (for Linux/X11)
* pthreads (for Linux/X11)

## Building
Quickstart
~~~~~
git clone https://github.com/jtanx/libclipboard
cd libclipboard
mkdir build
cd build
cmake ..
make
sudo make install        (optional)
~~~~~

Building test module and samples
~~~~~
cd libclipboard
git submodule init
git submodule update
mkdir build
cd build
cmake ..
make check
~~~~~

To add SOVERSION to the library (i.e. `libclipboard.so.1`), configure with
~~~~~
cmake -DLIBCLIPBOARD_ADD_SOVERSION=ON
~~~~~

To build a shared library instead of a static library
~~~~~
cmake -DBUILD_SHARED_LIBS=ON
~~~~~

To build the library using the stdcall calling convention
~~~~~
cmake -DLIBCLIPBOARD_USE_STDCALL=on
~~~~~

To force the build of a particular backend, choose one of
~~~~~
cmake -DLIBCLIPBOARD_FORCE_WIN32=on
cmake -DLIBCLIPBOARD_FORCE_X11=on
cmake -DLIBCLIPBOARD_FORCE_COCOA=on
~~~~~

Note: This setting has only been tested for compiling the X11 backend on Windows.

To uninstall
~~~~~
sudo make uninstall
~~~~~
