Hello01
======================

Makes a .bin file that could be uploaded using u-Boot 
        to the Zedboard and display Hello World  using the serial uart

BUILD REQUIREMENTS
===================

Build requirements for  Linux Mint 15 (Olivia) (should work for all debian
installation on x86 platfom)

Install ARM Cross-Compiler:

   Refresh list of software available
      sudo apt-get update

   Install the ARM Cross-Compiler using 
      sudo apt-get install gcc-arm-linux-gnueabihf

BUILD 
======

The hello01.bin file is compiled using make :)


UPLOAD AND RUNNING USING U-BOOT
===============================

hello01.bin has its entrypoint / start address at: 0x10000

 a) Connect the Zedboard UART (USB) to the Computer.
 b)  use a serial terminal program to comunicate width the ZedBoard's UART 
        Windows:  can use Tera Term from
         http://hp.vector.co.jp/authors/VA002416/teraterm.html )
        Linux:
           Start a new terminal
	   Install minicom:
              sudo apt-install minicom
	      minicom -D/dev/ttyACM0 -b115200 -o                 

 c) power on the ZedBoard and wait for the message:
        Hit any key to stop autoboot:   
     and stop it by pressing a key :)

 d) Upload the program hello01.bin  using 
       loady 0x10000
             Send the file hello01.bin using the y-modem protocol
               Push ([Ctrl] + 'a') and then 'S' Select ymodem
               And select the file hello01.bin (using space) and [enter]
               (enter folders pushing space)         
       Linux:
             Stop screen by pushing ( [Ctrl] + 'a') and then 'k'
 
 e)  Run the program using
       go 0x10000

Now you shold se 
       ## Starting application at 0x00010000 ...
       Hello world!

LICENSE
==========

Copyright (C) 2012  Rune Langoy

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to
deal in the Software without restriction, including without limitation the
rights to use, copy, modify, merge, publish, distribute, sublicense, and/or
sell copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS
IN THE SOFTWARE.
