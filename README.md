# UNI-T UT61D IR RS232 signal Cable to USB com port DIY
since the RS232 port is not availible in most of the PC and laptop, modify the RS232 signal to USB com port TTL signal for easy access
during my teardown, the UT61D uses main chip FS9922-DMM4, where it 
# required tools #
- cp2102 converter chip
  ![image](https://github.com/WASmars/UNI-T_UT61D_RS232toUSB_port/assets/54877239/ae2ab262-d15f-438e-96da-5a7eb8f8ccf8)
- basic solder tools and skill
- 180K ohm chip resistor
- 100 ohm chip resistor
  

# UNI-T RS232 cable UT-D02 disassembly
my original RS232 cable UT-D02 is old type, which has larger space for placing CP2102 module to convert TTL

![image](https://github.com/WASmars/UNI-T_UT61D_RS232toUSB_port/assets/54877239/bec2b783-43ce-4f96-8b9f-f34582ea171d)

![image](https://github.com/WASmars/UNI-T_UT61D_RS232toUSB_port/assets/54877239/438648f9-30af-4f00-8b99-5a89aaa1bb4d)
![image](https://github.com/WASmars/UNI-T_UT61D_RS232toUSB_port/assets/54877239/e403065a-f597-41c3-a0c6-8a7163404fe1)

# Circuit modify for the correct UART receive
![image](https://github.com/WASmars/UNI-T_UT61D_RS232toUSB_port/assets/54877239/60f3caae-0aae-49c7-af6a-c7ef9549dcb6)
after mod, missing pictures for the front

![image](https://github.com/WASmars/UNI-T_UT61D_RS232toUSB_port/assets/54877239/55bbb4a2-dd5d-484a-8948-e002b3fa6bbc)

Since TTL and RS232 has reversed High/Low signal, only need to revised Q2 direction from Common collector to Common Emitter mode to get proper 1s and 0s for TTL com port
To prevent the high level voltage from Q1 collector, I place 180K resistor to limit the voltage of Q2-base.
### Correct serial port settings for UT61D meter in TS DMM viewer, we can choose_____###
- mothertool MT-4520
- or @HID Multimeter
- or MASTECH MS8150D
will update as I confirmed


Reference information
- UNI-T UT61E RS232 serial interface cable to USB diy mod ### Correct serial port settings for UT61E meter are: speed 19200, bits 7, stop 1, parity odd. ###
http://blog.avrnoob.com/2014/03/uni-t-ut61e-rs232-serial-interface.html
- Analysis of UT61 communications
https://sourceforge.net/p/ut61/wiki/protocol/
- Sigrok UNI-T UT61D info, especially for the  IC datasheet spec for RS232 interface definition
https://sigrok.org/wiki/UNI-T_UT61D
-  Differential pair signal
https://www.bb-elec.com/Learning-Center/All-White-Papers/Serial/%E2%80%A2-Polarities-for-Differential-Pair-Signals-(RS-422.aspx


- the Ts Digital Multi Meter Viewer can give windows GUI interface with logger for the adaptor http://www.ts-software-jp.net/products/tsdmmview.html

