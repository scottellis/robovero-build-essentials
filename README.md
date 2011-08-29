  robovero-build-essentials
=======

A meta-package to install the crosstool-NG required packages for doing Gumstix
Robovero expansion board development from an Ubuntu Linux workstation.

There is an accompanying python script for checking the installed packages on
your workstation without trying to do an install.

Last tested with Ubuntu 11.04


Checkout
-------

Checkout the project from github like this

    $ git clone git://github.com/scottellis/robovero-build-essentials-project.git
    

Usage
-------

If you just want to check for missing packages, you can use the check-installed.py
script. 

Run it with no arguments. You should hopefully get a listing like this.

    scott@laptop:~/projects/robovero-build-essentials-project$ ./check-installed.py 
    
    Packages installed:
    
    ii  gawk                1:3.1.7.dfsg-5               GNU awk, a pattern scanning and processing language
    ii  bison               1:2.4.1.dfsg-3               A parser generator that is compatible with YACC
    ii  flex                2.5.35-10ubuntu1             A fast lexical analyzer generator.
    ii  automake            1:1.11.1-1ubuntu1            A tool for generating GNU Standards-compliant Makefiles
    ii  libtool             2.2.6b-2ubuntu3              Generic library support script
    ii  libncurses5-dev     5.7+20101128-1               developer's libraries for ncurses
    ii  zlib1g-dev          1:1.2.3.4.dfsg-3ubuntu3      compression library - development
    ii  libusb-dev          2:0.1.12-17                  userspace USB programming library development files
    ii  unzip               6.0-4ubuntu1                 De-archiver for .zip files
    ii  xutils-dev          1:7.6+1                      X Window System utility programs for development  
    
    Packages missing:
    
    <none>
    

The meta-package robovero-build-essentials.deb can be used to install all or just the
missing packages on your Ubuntu system. 

If you did a git checkout of this project, the you could also customize the
package first by editing the robovero-build-essentials/DEBIAN/control file and 
rebuilding the deb.


If you are customizing, after your edits, run the following command to rebuild

    $ cd robovero-build-essentials-project
    $ dpkg-deb -b robovero-build-essentials


To install the robovero-build-essentials.deb package, run the following:

    $ sudo dpkg -i robovero-build-essentials.deb
    $ sudo apt-get -f install


The apt-get call does the real installation and will give you a list of what's
going to happen and a chance to abort before it does anything.


Package List
-------

The list of packages come from the Gumstix recommendations on the Wiki - 
<a href="http://wiki.gumstix.org/index.php?title=RoboVero#Prerequisites>
Robovero -Toolchain - Prerequisites</a>

Here's the package list

    gawk
    bison
    flex
    automake
    libtool
    libncurses5-dev
    zlib1g-dev
    libusb-dev
    unzip
    xutils-dev (for makedepend)

