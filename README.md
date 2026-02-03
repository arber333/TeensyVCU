# TeensyVCU
Design of a VCU for Teensy 4.1 board equipped with 3x CAN bus

![alt text](https://github.com/arber333/TeensyVCU/blob/main/Screenshot%202026-02-03%20201656.png)

After i succesfully finished Megane conversion i decided in the future i may need the same VCU type with more input/outputs. There is question to control AC signal to drive AC compressor without internal commands where there may be interlocks that are not bridged and are preventing AC to run because engine is now missing.
For my first VCU i use VCU from design of Anthony Bezencon, username aot93 on Openinverter forum https://openinverter.org/forum/viewtopic.php?t=2167. It works great until now even though i find it a little flimsy in form and there is no ground plane to shield against EM signals. Not that this works gainst VCU in operation…
I made my own design now with the same form and signal pinout in mind. That way if i would replace first VCU with my board the thing would directly work with the teensy chip and cable harness. The only difference would be the new expanded input, output pins with two new analog pins.

I am now left with:
– 4 new digital inputs, row D
– 2 new analog inputs, row F under previous throttle inputs
– 4 new digital outputs at about 0.5A capability, row G

Other changes include using NCV8401 protected switch to drive main DC contactors and precharge.
All digital inputs and outputs used are conneceted through ULN2003 SMD chips.
I made provision to use zener protective diodes on analog pins.
I also setup some pullup resistors so some of the input pins could be used to work with active low signals.
Code stil works from the same repository
https://github.com/arber333/Mini-E-VCU

After i soldered the board and added connector i tested it with existing harness on my Megane and Mazda….
![alt text](https://github.com/arber333/TeensyVCU/blob/main/image.png)

In version V2.2 i corrected some GND error connections and tested it with all 3 CAN bus modules populated.
This version allows the use of pullup resistors on the ULN2003 chip for use with PWM signals.
