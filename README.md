# Control-LEDs-ON-OFF-with-IR-Remote-and-Arduino

I made this Arduino project that allows to turn ON and OFF LEDs using a cheap IR remote control as a preparation for the next big step: disassemble my girlfriend’s chinese LED lamp and replace its board with and Atmega Tiny microcontroller, probably ATTiny24A and change the stupid remote control with another one.

The project is pretty simple, you don’t need a lot of components. In my case I have used only 3 x 330Ω resistors, 3 leds and a TSOP4838 IR receiver module. You must check the datasheet before use the IR module to see which pins connect to the power supply and which one delivers the output voltage.

I used an available IR Arduino library so it was pretty easy to decode the signals transmitted by the infrared remote. You can download the version that I’ve used using the link below but I advice you to go to the official page and download any updated version. To install, unzip the archive, move the downloaded IRremote directory to: arduino-1.x/libraries/IRremote where arduino-1.x is your Arduino installation directory.

You will have to open the serial monitor window and press the remote buttons to find out what code does each button transmitts and then update the sketch to use those codes. You can add more leds but you’ll have to change the code inside the switch() function and add more cases. For example if you want to add one more led add this code after the last break; inside the switch();

The array itsONled[] = {0,0,0,0} is used to set the initial state of LEDs (in our case OFF) and has number of leds + 1 more zeros, so if you add 2 more leds, then add 2 more zeros (5 leds for a total of 6 zeros).

