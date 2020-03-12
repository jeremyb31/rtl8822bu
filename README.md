<u>**8822BU for Linux**</u>

Driver for 802.11ac USB Adapter with  
RTL8822BU chipset  
Only STA/Monitor Mode is supported, no AP.  

A few known wireless cards that use this driver include 
* [Edimax EW-7822ULC](http://us.edimax.com/edimax/merchandise/merchandise_detail/data/edimax/us/wireless_adapters_ac1200_dual-band/ew-7822ulc/)
* [ASUS AC-53 NANO](https://www.asus.com/Networking/USB-AC53-Nano/)


> NOTE: At least v4.7 is needed to compile this module
> sorry people with older kernels, the code is removed.
> Upon request I can work towards making it backwards compatible.

Currently tested on X86_64 and ARM platform(s) **only**,  
cross compile possible.

For compiling type  
`make`  
in source dir  

To install the firmware files  
`sudo make install`


To Unload driver you may need to disconnect the device  

If the driver fails building consult your distro how to  
install the kernel sources and build an <u>external</u> module.


**NOTES**  
This driver allows use of wpa_supplicant by using the nl80211 driver
`wpa_supplicant -Dnl80211`

If installing on Rasberry Pi or other "armv71" devices, firstly install all prerequisities mentioned at README-RASP.md, edit the Makefile and set `CONFIG_PLATFORM_ARM_RPI = y` and `CONFIG_PLATFORM_I386_PC = n`, and finally, proceed with make proceedures mentioned above.

**STATUS**  
Driver works fine (some sort of)  
Most of the work is done is cleaning the driver and make this mess **readable**   for conversion.
Updates for wireless-ext/cfg80211  are not accepted.  

  
**BUGS**  
 
