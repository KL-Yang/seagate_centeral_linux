# seagate_centeral_linux

The following two files are patch for OpenWRT 15.05's cns3xxx
1. 901_seagate_central_ethernet_smp.patch
2. config_seagate_smp
Both ethernet and SMP are working fine, can boot into debian Jessie and compile the kernel itself locally with -j2

The rest files are mainline linux patch for Seagate Central NAS 4.x (linux-4.2.y)

see: http://forum.doozan.com/read.php?2,22114
the config_seagate_good0 after apply patch is a basic configuration for Debian Jessie.

Works: sata, ethernet
Not yet: smp, usb, rtc, mtd

Note for the ethernet driver, cns3420 uses edge triger irq.
http://www.linuxfoundation.org/collaborate/workgroups/networking/napi#non-level_sensitive_IRQs

This is a Wip patch, in progress of cleaning up and try to upstream later.
The files are copied from OpenWRT, and the patch applies on top of them.
