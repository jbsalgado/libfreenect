libfreenect
===========

libfreenect is a userspace driver for the Microsoft Kinect.
It runs on Linux, OSX, and Windows and supports

- RGB and Depth Images
- Motors
- Accelerometer
- LED

Audio is a work in progress.


# Build Instructions

To build libfreenect, you'll need

- [libusb](http://libusb.info) >= 1.0.13
- [CMake](http://cmake.org) >= 2.6
- [python](http://python.org) == 2.* (only if BUILD_AUDIO or BUILD_PYTHON)

For the examples, you'll need

- OpenGL   (included with OSX)
- glut     (included with OSX)
- [pthreads-win32](http://sourceforge.net/projects/pthreads4w/) (Windows)


## <a name="fetch-build"></a>Fetch & Build

    git clone https://github.com/OpenKinect/libfreenect
    cd libfreenect
    mkdir build
    cd build
    cmake -L ..
    make
    
    # if you don't have `make` or don't want color output
    # cmake --build .

You can also specify a build with debug symbols:

    cmake -L .. -DCMAKE_BUILD_TYPE=debug
    # or with optimizations
    # cmake -L .. -DCMAKE_BUILD_TYPE=RelWithDebInfo

## OSX

If you don't have a package manager, install [Homebrew](http://brew.sh/).
For a manual build, see [the wiki](http://openkinect.org/wiki/Getting_Started#Manual_Build_under_OSX).

### Homebrew

    brew install libfreenect
    # or get the very latest:
    # brew install --HEAD libfreenect
    
### MacPorts

    sudo port install git-core cmake libusb libtool
    
Continue with [Fetch & Build](#fetch-build).


## Linux

For a manual build, see [the wiki](http://openkinect.org/wiki/Getting_Started#Manual_Build_on_Linux).

### Ubuntu/Debian/Mint

The version packaged in Ubuntu may be very old.
To install newer packaged builds, see [the wiki](http://openkinect.org/wiki/Getting_Started#Ubuntu.2FDebian).
Continue with this section for a manual build.

    sudo apt-get install git-core cmake pkg-config build-essential libusb-1.0-0-dev
    sudo adduser $USER video
    sudo adduser $USER plugdev # necessary?
    
    # only if you are building the examples:
    sudo apt-get install libglut3-dev libxmu-dev libxi-dev
    
Continue with [Fetch & Build](#fetch-build).
    
There is also a [debian branch](https://github.com/OpenKinect/libfreenect/tree/debian) for packaging purposes.

### Gentoo Linux

There is a live ebuild for your convenience in [platform/linux/portage/dev-libs/libfreenect/](https://github.com/OpenKinect/libfreenect/tree/master/platform/linux/portage/dev-libs/libfreenect).

### Arch Linux

There is a [libfreenect](https://aur.archlinux.org/packages/libfreenect) PKGBUILD in the AUR.
Alternately, the [libfreenect-git](https://aur.archlinux.org/packages/libfreenect-git) PKGBUILD builds the very latest.


## Windows

The inf files in [platform/windows/](https://github.com/OpenKinect/libfreenect/tree/master/platform/windows) may be used for installing the device.
Follow [Fetch & Build](#fetch-build) or use Github and CMake GUI tools.
You may need to supply paths to CMake so it can find dependencies.
For example:

    cmake .. -DLIBUSB_1_INCLUDE_DIR="C:\path\to\libusb\include" -DLIBUSB_1_LIBRARY="C:\path\to\libusb\libusb.lib"


# Wrappers

Interfaces to various languages are provided in [wrappers/](https://github.com/OpenKinect/libfreenect/tree/master/wrappers).
Wrappers are not guaranteed to be API stable or up to date.

- C (using a synchronous API)
- C++
- C#
- python
- ruby
- actionscript
- Java (JNA)


# Maintainers

Ongoing Development and Maintenance by the OpenKinect Community

http://www.openkinect.org

- Original Code and Engineering: Hector Martin (marcan)
- Community Lead: Josh Blake (JoshB)
- Integration: Kyle Machulis (qDot)


# License

The libfreenect project is covered under a dual Apache v2/GPL v2
license. The licensing criteria are listed below, as well as at the
top of each source file in the repo.

```
This file is part of the OpenKinect Project. http://www.openkinect.org

Copyright (c) 2010 individual OpenKinect contributors. See the CONTRIB
file for details.

This code is licensed to you under the terms of the Apache License,
version 2.0, or, at your option, the terms of the GNU General Public
License, version 2.0. See the APACHE20 and GPL2 files for the text of
the licenses, or the following URLs:
http://www.apache.org/licenses/LICENSE-2.0
http://www.gnu.org/licenses/gpl-2.0.txt

If you redistribute this file in source form, modified or unmodified,
you may: 

- Leave this header intact and distribute it under the same terms,
  accompanying it with the APACHE20 and GPL2 files, or
- Delete the Apache 2.0 clause and accompany it with the GPL2 file, or
- Delete the GPL v2 clause and accompany it with the APACHE20 file 

In all cases you must keep the copyright notice intact and include a
copy of the CONTRIB file.
 
Binary distributions must follow the binary distribution requirements
of either License.
```


# More Information

Information about the OpenKinect project can be found at http://www.openkinect.org

For questions, support, and discussion, check out the google groups mailing list at http://groups.google.com/group/openkinect

Or the IRC channel at \#openkinect on [Freenode](http://freenode.net/)

We are also on twitter at http://twitter.com/openkinect
