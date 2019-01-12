# Upload2Arduino-Without-IDE
This project sends the sketch compiled to the Arduino without necessity of IDE Arduino, with a simple command it is possible to send the sketch directly. Mostly on windows operacional system.


#Compilation
The sketch needs to be compiled on linux using the xxx folder using the makefile(only works on linux), after which the build (build-one, build-mega ..) folder should be moved to the upload folder. We put an example (blinky) already compiled for initial tests.

#Command to send the sketch
into the directory /Upload2Arduino-Without-IDE

#UNO
avrdude -q -V -p atmega328p -c /avrdude.conf -D -c arduino -b 115200 -P COM5 \ -U flash:w:build-uno/sketchbook.hex:i

#MEGA
avrdude -q -V -p atmega2560 -C avrdude.conf -D -c wiring -b 115200 -P COM3 -U flash:w:build-mega2560/sketch_microdrum.cpp.hex:i

Inside the command it is necessary to inform some parameters like for example the port in which the Arduino is connected, in this case COM5 and the file in hex inside the build folder.
