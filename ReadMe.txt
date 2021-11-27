Arduino Controlled AD9850 DDS VFO
Designed by Richard Visokey AD7C
www.ad7c.com
Please feel free to contact me if you have any questions at ad7c@arrl.org.


AD9850_LCD_ROTARY_WMENUS 
This is the basic sketch. It can be used to create an output from 1mhz to 30mhz.  You set the starting frequency by altering this line: int_fast32_t rx=7200000.  What you see on the screen is the output frequency.  If you can find a friend with a calibrated frequency counter you can adjust "int32_t freq = frequency * 4294967295/125000000;" slightly to get the AD9850 exactly on frequency.  It is very accurate when tuned.  When using this sketch you do not need the switch and resistor to ground from PIN A5 on the Arduino.

AD9850_LCD_ROTARY_WMENUS_IF
This is the IF sketch. It can be used to create an output from 1mhz to 30mhz and also uses an IF.   You adjust the starting frequency the same as above.  When using this sketch you need the switch and resistor to ground from PIN A5 on the Arduino.  The IF is determined by this line: int_fast32_t iffreq = 4192000; It is a subtractive IF.  When A5 is low (ground) the output and the display are equal.  Then A5 is high the output is the display minus the IF frequency.

It is possible to switch my code around to have an additive IF and reverse the action of the A5 pin.  I left a lot of comments which should make it very easy for you.  Again... ask if you need help and I will do my best.


*** November 6th, 2013 ***
Rev 2.0 of the code has EEPROM memory storage of the last set frequency.  The frequency has to remain for 3 seconds (adjustable in code) before it is written to memory so as not to overload the EEPROM as you 'spin' through frequencies.


Some of the included code was produced by other authors.  I have included their original code and comments.  Please give credit where credit is due as without them this project would have been a lot more difficult. Especially the rotary encoder section!

Please excuse the very rough schematic.  I typically just draw something on paper and this was my first every attempt at Express SCH.


Thank you,

Rich Visokey
AD7C


