# Reflashing Cisco Switch 
##(2960 or equivalent without USB etc) over serial

Using extraputty - console in over serial port.
Make sure baud is 115200 or this will take hours.

At "switch:" prompt

    flash_init
    load_helper
    copy xmodem: flash:c2960-lanbasek9-mz.122-55.SE12.bin

In extraputty go to "File Transfer" and Xmodem 1k --> send
Choose: c2960-lanbasek9-mz.122-55.SE12.bin

Wait a while - at 115200, it'll probably take about 20 mins-ish
Once successfully transferred:

    boot flash:c2960-lanbasek9-mz.122-55.SE12.bin