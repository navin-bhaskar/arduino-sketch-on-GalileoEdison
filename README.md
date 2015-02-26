
# Introduction
A simple scons script that can be used to compile the Arduino sketches on the Edison/Galileo
itself.

# Usage
* Clone this repo in your Galileo or Edison
* Download the Arduino IDE from here: https://downloadcenter.intel.com/download/24355/Intel-Arduino-IDE-1-6-0
* Extract the downladed Arduino archive and copy the "Hardware" folder into the folder where this repo was cloned  
* run "scons"
* This will compile blink.cpp and output sketch.elf
* Run sketch.elf to see LED connected at port D5 blink using command ./sketch.elf
* Exit the application any time by hitting ctrl+c

# Modifying the scons
The target for compilation can be selected by changing the "board" variable in SConstruct.
ALso new or other source files can be added by naming them in the second argument list to env.Program().
You can find more information regarding this here: http://navinbhaskar.blogspot.in/2015/08/compiling-arduino-sketchs-on.html
   
