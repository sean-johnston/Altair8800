# Altair8800
Source code for Arduino Altair 8800 simulator<br>
For details about the simulator see:<br>
https://www.hackster.io/david-hansel/arduino-altair-8800-simulator-3594a6

For extending the simulator with external harware see:
https://github.com/dhansel/Altair8800-IOBus

Support for Teensy 3.6 host implemented by Dirk Herrendoerfer:
https://github.com/dherrendoerfer/altair-8800-again

Please post any questions or issues in:
https://groups.google.com/forum/#!forum/altair-duino


## Overview Of New Features

This is a fork of the original Altair 8800 Simulator by David Hansel. This
is enhancement to the host code (Window, MacOS, Linux, and FreeBSD). This
version implements the following features:

* Ability to connect a graphical Altair 8800 panel to the simulator through
a socket. This is a Python program, that uses Tkinter as a GUI. This project 
can be found at the following location:

    https://github.com/sean-johnston/altair-panel

* Ability to change what the backspace outputs. Currently, most system return
the value 8, when the key is pressed. This toggle lets you use the value 127.
This is useful when using the 4k and 16k Basic. CP/M seems to expect the 
value 8. You can toggle this by pressing the keys to get the **~** character.

* Get a menu with the auxiliary switch functions. This is the same as setting
the first 4 right switches to 0 and pressing the Aux Down. You can then select a 
number corresponding the function that you want. This was added to make it
easier to access this functionally.

* Pressing the space bar to display the serial panel. This is useful if you 
have the serial panel turned off.

* Ability to compile on MacOS. There is some code that prevented the compilation
on MacOS. Particularly the eventdf function. This was changed to 
the socketpair function, and there is a conditional compile to use this.
Compiling on MacOS is the same as compiling for Linux

* Ability to compile on FreeBSD. I added this, because of the change for MacOS.
MacOS runs under BSD Unix, so it was a small step to make it work with FreeBSD.
Compiling is a little different. You need to install g++ and gmake. Once these
are install you can compile the code with **gmake** instead of **make**.

* Changed the serial panel to include what key to press for toggling the data 
switches.

