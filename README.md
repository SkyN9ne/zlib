### ZLIB DATA COMPRESSION LIBRARY

zlib 1.2.13 is a general purpose data compression library.  All the code is
thread safe.  The data format used by the zlib library is described by RFCs
(Request for Comments) 1950 to 1952 in the files
https://tools.ietf.org/html/rfc1950 (```zlib``` format), rfc1951 (```deflate``` format) and
rfc1952 (```gzip``` format).

All functions of the compression library are documented in the file ```zlib.h```
(volunteer to write ```man``` pages welcome, contact ```zlib@gzip.org```). A usage example
of the library is given in the file ```test/example.c``` which also tests that
the library is working correctly.  Another example is given in the file
```test/minigzip.c```. The compression library itself is composed of all source
files in the root directory.

To compile all files and run the test program, follow the instructions given at
the top of ```Makefile.in```. In short ```./configure; make test```, and if that goes
well, ```make install``` should work for most flavors of UNIX / Linux. For Windows, use
one of the special ```makefile```s in ```win32/``` or ```contrib/vstudio/```. 
For VMS, use ```make_vms.com```.

Questions about zlib should be sent to <```zlib@gzip.org```>, or to Gilles Vollant
<```info@winimage.com```> for the Windows DLL version. 


The zlib's webpage is at: https://zlib.net  
Before reporting a problem, please check this site to
verify that you have the latest version of zlib; otherwise get the latest
version and check whether the problem still exists or not.

You should read the zlib FAQ's at: https://zlib.net/zlib_faq.html before asking for help.

The changes made in version 1.2.13 are documented in the file ```ChangeLog.txt```.

Unsupported third party contributions are provided in the ```contrib/``` directory

zlib is available in Java using the ```java.util.zip``` package, documented at:
https://java.sun.com/developer/technicalArticles/Programming/compression/ 

A Perl interface to zlib written by Paul Marquess <pmqs@cpan.org> is available
at CPAN (Comprehensive Perl Archive Network) sites, including:
https://search.cpan.org/~pmqs/IO-Compress-Zlib/ 

A Python interface to zlib written by A.M. Kuchling <amk@amk.ca> is
available for Python 1.5+ and newer versions.
Python documentation: https://docs.python.org/library/zlib.html

zlib is built-in into the TCL / TK languages as well: https://www.tcl.tk/man/tcl/TclCmd/zlib.html

An experimental package to read and write files in ```.zip``` format, written on top
of zlib by Gilles Vollant <info@winimage.com>, is available in the ```contrib/minizip``` directory of zlib


Notes for some targets:

- For Windows DLL versions, please see ```win32/DLL_FAQ.txt```

- For 64-bit Irix ```deflate.c``` must be compiled without any optimization. 
With ```-O``` one ```libpng``` test fails. The test works in 32-bit mode (with the ```-n32``` compiler flag)
The compiler bug has been reported to SGI.

- zlib doesn't work with ```gcc``` v2.6.3 on a DEC 3000/300LX under OSF/1 2.1 
It works when compiled with ```cc```

- On Digital UNIX 4.0D (formely OSF/1) on AlphaServer, the ```cc``` option ```-std1``` is necessary 
to get ```gzprintf``` working correctly. This is done by ```configure```

- zlib doesn't work on HP-UX 9.05 with some versions of ```/bin/cc```. 
It works with other compilers tho. Use ```make test``` to check your compiler.

- ```gzdopen``` is not supported on RISCOS or BEOS.

- For PalmOS, see: https://palmzlib.sourceforge.net
