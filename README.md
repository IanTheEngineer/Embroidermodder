What is Embroidermodder ?
-------------------------

Embroidermodder is a free machine embroidery software program.
The newest version, Embroidermodder 2 can:

- edit and create embroidery designs
- estimate the amount of thread and machine time needed to stitch a design
- convert embroidery files to a variety of formats
- upscale or downscale designs
- run on Windows, Mac and Linux

For more information, see [our website](http://embroidermodder.github.io).

Dependencies
------------

To build Embroidermodder 2 from source you will need at least:
- [Embroidermodder 2](https://github.com/Embroidermodder/Embroidermodder)
- [Qt](http://www.qt-project.org) (version >= 4.8).

Optionally, you may want to add:

- [KDE](http://www.kde.org) for thumbnailer
- [Valgrind](http://www.valgrind.org) for debugging

Ubuntu repository packages:
The Qt, KDE and Valgrind build dependencies can be installed easily by opening a terminal and issuing this command:
```
sudo apt-get install git build-essential qt4-dev-tools libqt4-opengl-dev kdelibs5-dev valgrind
```

Fedora repository packages:
The Qt, KDE and Valgrind build dependencies can be installed easily by opening a terminal and issuing this command:
```
sudo yum install git gdb gcc-c++ qt-devel kdelibs-devel valgrind
```

Mac OS X repository packages:
It is recommended that you first install [XQuartz](http://xquartz.macosforge.org), setting it to be your default X11 server, and logout/login again or restart.
Then, after installing the OS X package manager [Homebrew](http://brew.sh), Qt can be installed easily by opening a terminal and issuing this command:
```
brew install qt
```
Building
--------

Various methods of building can be found in the project-files subfolder.
For most builds, it is as simple as opening a terminal in the
project-files/qmake subfolder and typing:
```
qmake && make
```

Build time can be considerably decreased on multi-core machines, for example:

- Dual Core:
```
qmake && make -j2
```
- Quad Core:
```
qmake && make -j4
```

When building for Fedora:
Substitute qmake-qt4 for qmake.

When building for Windows:
If you are using Qt/Mingw, substitute mingw32-make for make.
If you are using Qt/MSVC, substitute nmake for make.
You may need to add the directory where those executables are located to your system path.
It is recommended that when targeting Windows, that you should omit the -j switch completely,
otherwise build errors may occur unless you are building an individual pro file.

Help Files
------------
The help files for Embroidermodder 2 are a git submodule, which means that
they reside in a separate repository. They are not required for the application
to run, but if they are not present, you will likely receive an error that they
do not exist when pressing F1 or attempting to access help through the menu.

If you used ```git clone``` to obtain the Embroidermodder source,
you need to run these commands from the toplevel of
the working tree(which is the Embroidermodder directory):

```
git submodule init
git submodule update
```

If you downloaded a zip file of the Embroidermodder source rather than using git,
you will need to:

- Download the [help files](https://github.com/Embroidermodder/Embroidermodder.github.io/archive/master.zip)
- Unzip the archive
- Rename the "Embroidermodder.github.io-master" directory to "help"
- Copy the "help" directory to "Embroidermodder-master/embroidermodder2/help"

Sample Files
------------

Various sample embroidery design files can be found in
the embroidermodder2/samples folder.

Install/Uninstall
-----------------

- Linux:
To install, open a terminal in the
project-files/qmake subfolder and type:
```
sudo make install
```

To uninstall, open a terminal in the
project-files/qmake subfolder and type:
```
sudo make uninstall
```
