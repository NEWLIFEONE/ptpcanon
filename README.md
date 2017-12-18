# ptpcanon
Remote capture and test program for Canon photo cameras supporting PTP portocol. 

(c) 2003 Nikolai Kopanygin
Based on ptpcam  (c)2001-2003 Mariusz Woloszyn <emsi@ipartners.pl>

=====================
*About this software*
=====================

You may find new versions of this software at:
https://github.com/nikolai-kopanygin/ptpcanon

This folder contains following code:
ptpcanon.c, ptpcanon.h	- test and capture program
ptpusb.c, ptpusb.h	- PTP USB implementation

===================
*Supported Cameras*
===================

Canon PowerShot A60/A70
Canon Digital IXUS 400
Canon IXUS i
Probably other Canon PTP cameras

======================
*Prerequisites       *
======================
Install GNU Autotools, packages libusb-dev and
libptp2 from https://sourceforge.net/projects/libptp.

======================
*How to build        *
======================

aclocal && \
autoheader && \
automake --add-missing && \
autoconf && \
./configure && \
make

======================
*How to use the test*
======================

For a test run ptpcanon -c 
For a capture run ptpcanon -t
