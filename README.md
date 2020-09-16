Hello,

this is for the Samsung NP350E7C with a Pentium B980.
This laptop will spew an error if you try to upgrade the processor.
Tried to upgrade the ME but this results in a failure.

Even if you disable the Intel ME, it will still shut itself down due to the incompatibilty.

I also modified the VBIOS and overclocked the 7670M from 600/900 to 780/1135.

My laptop froze during the erase flashing... so welp.

I bought a SOIC8 clip to flash this chip so hopefully, i can unbrick it.
I also have another identical laptop like that so if my dump doesn't work, then i can just take it from this one.
See you in 18 more days. (Written the 4th September 2020)

Update (16th September) :


![CHA341A-based Flasher](https://raw.githubusercontent.com/gameblabla/SAMSUNG_NP350_INTEL_ME_REMOVAL/master/USB_FLASH.jpg)

I finally got my flasher (it arrived in 12 days) and the motherboard separated the BIOS in two ROMS :
One that is 4MB and contais the BIOS, the other contains the ME firmware (2MB).
Both EEPROM chips are made by Winbound.

To read the BIOS chip, use flashrom in a linux distro :
sudo flashrom --programmer ch341a_spi -r new.bin

This will read the EEPROM and output it to new.bin.

To write to the BIOS chip, use flashrom again :
sudo flashrom --programmer ch341a_spi --write BIOS_to_flash.bin

However, it still complains about "INVALID CPU AND PCH COMBINATION" even after updating the ME firmware xox


Instructions on how to flash chip : 
https://www.win-raid.com/t796f16-Guide-Using-CH-A-based-programmer-to-flash-SPI-EEPROM.html

How to unlock flash chip with pinmod :
https://www.win-raid.com/t3553f39-Guide-Unlock-Intel-Flash-Descriptor-Read-Write-Access-Permissions-for-SPI-Servicing.html

Intel ME versions (i upgraded mine to the latest one. Still, no effect it seems) :
https://www.win-raid.com/t596f39-Intel-Management-Engine-Drivers-Firmware-amp-System-Tools.html

How to use the flasher :
https://www.youtube.com/watch?v=2Y06x1f22B0
