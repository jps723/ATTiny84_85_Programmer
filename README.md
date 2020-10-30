# ATTiny Programming Jig Build Notes                                                                    	1/5/20
 
This project is in partnership with [Bantam Tools](https://www.bantamtools.com)

**Design Notes:**

**LEDs**
Arduino pins 7, 8, and 9 are attached to LEDs to show Programming/Errors/Heartbeat, respectively.  These are status LEDs during programming and built into the ArduinoISP sketch.  The yellow LED ‘breathes’ when the programmer is connected, the green led blinks when programming is underway, and the red LED turns on when there is an error and when the sketch finishes uploading. 
 
```
7 — Programming
8 — Errors
9 — Heartbeat
```
 
**SPI PROGRAMMING**
```
10 — SS (Slave Select)
11 — (MOSI)
12 — (MISO)
13 — (SCK)
```
 
**GLOBAL**
```
5v — Power
GND — GND
Reset
```
 
**Build Process**
It’s easiest to solder in this order:
```
1. Resistors
2. Dip Sockets
3. Headers
4. LEDs
5. Capacitor
```
 
**Programming Process**
```
1. Upload ArduinoISP Sketch to the Arduino Uno
2. Install ATTinyCore by Spence Konde via the Arduino Board Manager
3. Tools > Board > ATTiny 25/45/85 (or 24/44/84)
4. Tools > Clock - 8 MHz (Internal) 
5. Tools > Chip > ATTiny85 (or ATTiny84)
6. Tools > LTO – “Disabled”
7. The remaining settings should remain as default.
8. Plug the ATTiny into the socket; With the Arduino’s USB port pointing down, pin 1 should be on the lower right
9. Plug the jig into the Arduino and power it (the yellow LED should begin to ‘breathe’ after a startup sequence)
10.  Tools > Burn Bootloader (This only needs to be done once per chip)
```
 
**Test**
```
1. File > Examples > 01.Basics > Blink; change LED pin to 3 (this is pin2 on the 85, pin10 on the 84)
2. Tools > Programmer: Arduino as ISP
3. Sketch > Upload using Programmer
```
