Content
==================

 * Dlient
 * Build Dlient on Linux
 * Build Dlient on Windows
 * Special notes for advanced users
 * Closing Remarks

Dlient
===================

Dlient is a gaming client that allows users to one click download and install games and game modification.


Build Dlient on Linux
===================

Dependencies
------------

You can install dependencies by package manager or install_deps.sh

Required dependencies:

 * GCC (4.6 or later, multilib support for 32 bit compatibility on 64 bit systems)
 * cmake (2.8.5 or later)
 * PkgConfig (for building DEB and RPM packages)
 * Boost (date_time, filesystem, thread system, test_exec_monitor, unit_test_framework)
 * Freetype
 * GTK2
 * libX11 (with libXt)
 * libEvent
 * libNotify (0.7 or later)
 * GLib2
 * OpenSSL (only for building Curl)
 * BZip2
 * Sqlite3
 * tinyxml2
 * V8
 * Python
 * C-ares

Optional dependencies (will be built by cmake if not existing):
- Curl (if there is no ares support)
- wxWidgets (2.9.3 or later)
- Breakpad
- CEF (Chromium Embedded)

Installation
------------

Open Terminal in Desurium source directory and run:

    ./build_desura.sh

or you can speed up things by running:

    ./build_desura.sh rebuild_all -j `getconf _NPROCESSORS_ONLN`

or you can build DEB package:

    ./build_desura.sh pack_deb

or you can build RPM package:

    ./build_desurat.sh pack_rpm

Finally run Desurium using:

    ./install/delient

or install created DEB or RPM package

For informations on advanced arguments of the build script, run:

    ./build_desura.sh help

Build Dlient on Windows
=====================

Download and install:

 * Svn http://www.sliksvn.com/en/download or http://tortoisesvn.net/downloads.html
 * Msvc 2015 or higher (as C++11 features are in use)
 * Python 2.7 x86 http://www.python.org/getit/
 * CMake 3.0 or higher http://www.cmake.org/
 * Patch either from msysGit or git bash
 * (Optional) Windows DirectX 9 SDK for the CEF build https://www.microsoft.com/en-us/download/details.aspx?id=6812

Note: Make sure you add svn and python to your environment PATH

## Command line build:

Open a 32bit cmd.exe with env vars set up by vc or other scripts (so we have a full build environment) and run:

    ./build_dlient.bat

wait


## Visual studio build:

Open a 32bit cmd.exe with env vars set up by vc or other scripts (so we have a full build environment) and run:

    ./build_dlient_vis.bat
	
* Set BUILD_ALL as startup project
* In properties for BUILD_ALL set debugging options:
 * Command to source code dir + "\build_vis\Debug_Out\desura.exe"
 * Working Directory to source code dir + "\build_vis\Debug_Out"
* Build ThirdParty folder first (race condition some times if you dont)
* Build BUILD_ALL
 
Should be able to run and debug Desura now.

Build Dlient on Mac
=====================
Please go to branch apple3, you can find out how to compile it.

WARNING: IT IS UNDER HEAVY DEVELOPMENT!


Special notes for advanced users
=====================

Dlient is using the cmake build system for configuration on prject files for several build systems (make, VS, nmake, ...).
At the top of CMakeFile.txt is a documented list of options

a "normal" way to configure cmake would be something like this:

  * UNIX-based systems:
    1. mkdir build
    2. cd build
    3. cmake ..
    4. make
    5. sudo make install (optionally)

  * win32 based systems:
    1. md build
    2. cd build
    3. cmake ..
    4. open project files and compile them

Closing Remarks
=====================

If you need help, want to give some suggestions or just want to talk, feel free to join our IRC channel #dlient on irc.freenode.net.
