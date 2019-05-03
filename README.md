# Seagate_central_linux (Single Disk Version)

For linux-3.18.y and 4.4.y kernel, use corresponding branch; master is updated to 4.19.y.

The 4.19.y kernel is still WIP, support file will be merged gradually.
Foundamental patches are from OpenWRT of cns3xxx kernel, they are copied and merged for convinence.
There are aslo a few patch to fix the ethernet setup problems that specific to Seagate Central. 
config_seagate_smp is a working example of kernel configuration.

USB and RTC is not working. USB is likely due to missing PHY/VBUS configuration. SATA, Ethernet and SMP are 
working fine in my test of compiling the kernel itself on Seagate Central with -j2.

Kernel can be compiled with command: $LOADADDR=0x02000000 make uImage

# Prebuild images
All the thanks goes to OpenWRT. Some discussion can be found on http://forum.doozan.com/read.php?2,22114
A Debian Jessie rootfs (debootstrap armel) and kernel 3.18.27 can be found here
https://drive.google.com/file/d/0B-PZDFHXqH6pWmRJQ0k3enUzNzg/view?usp=sharing
MD5: 39fa4a61da52e9e2da909fe90990dcee

The kernel is built on Seagate Central. After booting, find the DHCP address on you router, ssh login, 
and root password is password.
Note, the MAC address was set to a random value by me, it cannot read the value in your firmware.

Unpack and copy uImage to the first (sda1) partition, and copy the rootfs to sda3, it should boot.
The stock uboot seems passing kernel parameters in a strange way, the rootfs must be seat on sda3. 
You may need force kernel command line argument to put rootfs on other partition.

A new kernel (kernel and kernel modules only) can be found here
https://drive.google.com/file/d/0B-PZDFHXqH6pWHBqR1ZUNkJPTk0/view?usp=sharing
MD5: 4b3ac00ac9e6eeafa7d4526bca98c351

Debian Stretch with linux-4.4.88 kernel.
https://drive.google.com/file/d/0B-PZDFHXqH6pZ0FYT2FjVkhMUVk/view?usp=sharing 
MD5: 72ef5ff3a270ede0a2315e52a81051c6

This is a Wip patch, use ON YOUR OWN RISK.
