# Reflashing Cisco Switch 
## (2960 or equivalent without USB etc) over serial

Kinda used to having modern equipment with USB etc, unbricking
this was harder than expected and tftpd64 and equivalents weren't
proving reliable for me. 


#### Assumptions/Requirements:
- Console cable connected from serial/rs232/com port on windows to switch on console port. 
- Have a copy of the firmware required from the cisco website
- Have the firmware extracted from tar/zip/whatever, I suggest 7zip.
- Download a copy of Extraputty. 


#### Procedure
Using extraputty - console in over serial port.
Make sure baud is 115200 or this will take hours.

At "switch:" prompt

    flash_init
    load_helper
    copy xmodem: flash:c2960-lanbasek9-mz.122-55.SE12.bin

In extraputty go to "File Transfer" and **Xmodem 1k** --> send  
Choose: c2960-lanbasek9-mz.122-55.SE12.bin

Wait a while - at 115200, it'll probably take about 20 mins-ish  
Once successfully transferred:

    boot flash:c2960-lanbasek9-mz.122-55.SE12.bin