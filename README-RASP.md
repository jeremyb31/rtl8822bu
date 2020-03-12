<u>**8822BU for Raspbian**</u>

# Driver for 802.11ac USB Adapter with
## RTL8822BU chipset
## Only STA/Monitor Mode is supported, no AP.

> NOTE: The build was tested with Raspbian GNU/Linux 9 (stretch) and kernel 4.19.66-v7+.
> In case it also works with additional releases, it would be nice ask to add your release as also compatible.

**To install Raspbian headers**
`sudo apt-get install raspberrypi-kernel-headers`

**To install prerequisites**
`apt-get install build-essential`

**To install build dependencies**
`sudo apt install git bc bison flex libssl-dev make`

**Build the driver**
`sudo make all`

<u>In case that you face build error due to wrong or missing headers you can identify your Kernel release and manually define it in the Makefile. Consider the following example to enforce the kernel release "4.19.66-v7+":</u>

### Section 1
**Comment the following line**
`KVER  := $(shell uname -r)`

**Add the following lines**
`## Example of kernel release manual definition`
`KVER  := 4.19.66-v7+`

###Section 2
**Comment the following line**
`KVER ?= $(shell uname -r)`

**Add the following lines**
`## Example of kernel release manual definition`
`KVER ?:= 4.19.66-v7+`

**Install the driver**
`sudo make install`

**Configure de driver into the system**
`modprobe 8188eu.ko`

**Reboot the system**
`sudo reboot`

**To blacklist an internal driver if it already exist on your system, add it to the respective file**
`/etc/modprobe.d/blacklist`

References
* https://www.raspberrypi.org/documentation/linux/kernel/building.md
* https://www.raspberrypi.org/forums/viewtopic.php?t=154749
* https://github.com/marcelolavor/rtl8822bu
* https://github.com/lwfinger/rtl8188eu