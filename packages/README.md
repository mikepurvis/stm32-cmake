Package Generation
==================

This directory creates a debian package of the stm32f1 or f4 CMSIS and StdPeriph libraries
and headers. This is useful for a few reasons:

 - You can use `sudo dpkg -i` to install a deb and avoid the fuss of manually
   compiling and installing the library.
 - You can place the deb on an apt repository, and make it trivially easy to
   set up a development environment on any Ubuntu or Debian machine---this is
   great for getting a whole team up and running quickly, or for temporary
   environments such as CI servers.

Usage
-----

You'll need a [fpm](https://github.com/jordansissel/fpm), which is what actually produces
the deb package from a folder of files. Apart from that, it's just a regular build:

~~~
sudo apt-get install rubygems
gem install fpm
mkdir packages/build
cd packages/build
cmake .. -DSTM32_FAMILY=F4
make
~~~

Enjoy your deb!
