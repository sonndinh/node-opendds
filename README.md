# OpenDDS module for Node.js

## Requirements:
* OpenDDS (http://www.opendds.org) and its dependencies must be installed.
* Make sure all of the OpenDDS development environment variables are set before running npm to install this module.  If you use the OpenDDS configure script, these variables can be set using "setenv.sh" or "setenv.cmd" depending on your platform.
** The OpenDDS development environment can use either the source tree or the installed tree (the one created by "make install").
** If using the installed tree, set the DDS_ROOT environment variable using the installed dds-devel.sh script.

## Tested platforms:
* Node LTS versions 12, 14, 16
* Linux (Ubuntu18.04, CentOS7) x86_64 using the distro-supplied GCC and c++11=1
* Windows 10 x86_64 using Visual Studio 2015
* macOS using Xcode 9.x clang C++ compiler
* Other OpenDDS-supported platforms should work, but may required changes to binding.gyp

## Building and running the tests

This assumes you are using nvm.

```
$ # In OpenDDS directory.
$ source setenv.sh
$ # In node-opendds directory
$ npm install
$ mwc.pl -type gnuace
$ make
$ cd tests
$ ./run_test.pl
```

## To build the module (for development of this module, users can simply use npm)
```
$ node-gyp configure build
```

## Changelog

### Version 0.1.1

* Add support and test coverage for multiple LTS versions of Node (12, 14, 16)

### Version 0.1.0

* Add support for publishing from Node.js

### Version 0.0.9

* Support building this module using an installed OpenDDS

### Version 0.0.8

* Requires at least OpenDDS 3.13. It will not build with older versions of OpenDDS.
* Added support for Security-enabled versions of OpenDDS.
* Compatibility with Node.js version 10 and NAN 2.10.

### Version 0.0.7

* Added Apple macOS support.
* Works with Node.js version 8.

### Version 0.0.6

* Added Microsoft Visual C++ support.

### Version 0.0.5

* Updated for Node.js version 6.9.5 and V8 version 5.8.1.

### Version 0.0.4

* Now hosted on GitHub which required a version bump to tell npm about it.
* No code changes.

### Version 0.0.3

* Updated to use new abstract interface callback from DataReaderImpl to
execute as an atomic operation rather than in two stages.  This change
uses updates to OpenDDS starting with r5997 in subversion and any release
after 3.4.1.  This will not build with older versions of OpenDDS.

### Version 0.0.2

* Updated to use extended data reference counting available in OpenDDS as
of r5993 in subversion.  This change will be available in releases
starting with the one following OpenDDS 3.4.1.  This will not build with
the older versions of OpenDDS.
