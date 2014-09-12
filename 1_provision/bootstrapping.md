Bootstrapping Notes
====================

usb install Debian 7 
---------------------

Several of the Debian CD and Debian Live images are created using isohybrid technology, which means that they may be used in two different ways:

* They may be written to CD/DVD and used as normal for CD/DVD booting.
* They may be written to USB flash drives, bootable directly from the BIOS of most PCs.

The most common way to copy an image to a USB flash drive is to use the "dd" command on a Linux machine:

dd if=<file> of=<device> bs=4M; sync

where:

* <file> is the name of the input image, e.g. "netinst.iso"
* <device> is the device matching the USB flash drive, e.g. /dev/sda, /dev/sdb.
* "bs=4M" tells dd to read/write in 4 megabyte chunks for better performance; the default is 512 bytes, which will be much slower
* The "sync" is to make sure that all the writes are flushed out before the command returns. 

Which image to download?
------------------------
* Avoid long download / need for internet access --> Full install iso, not netinst.
* VIA Eden X2 processors are natively 64-bit compatible.
* "The first CD/DVD disk contains all the files necessary to install a standard Debian system.
To avoid needless downloads, please do not download other CD or DVD image files unless you know that you need packages on them."

Choosing latest debian 7, amd64, dvd-1 iso that is available

download image
--------------
cd ~/

wget http://cdimage.debian.org/debian-cd/7.5.0/amd64/iso-dvd/debian-7.5.0-amd64-DVD-1.iso

download + compare checksum
---------------------------

wget http://cdimage.debian.org/debian-cd/7.5.0/amd64/iso-dvd/SHA512SUMS

cat SHA512SUMS

sha512sum debian-7.5.0-amd64-DVD-1.iso

dd image to USB stick
----------------------

dd if=debian-7.5.0-amd64-netinst.iso of=<device> bs=4M; sync

Setup
-----
open SSH server
standard system utilities

automating the install / unattended
-----------------------------------
https://www.debian.org/releases/stable/example-preseed.txt

including non-free firmware
---------------------------
* Intel Wireless Firmware
* Gobi GSM / GPS similar to: http://www.thinkwiki.org/wiki/Qualcomm_Gobi_2000

References
----------
[1] https://www.debian.org/CD/faq/#write-usb
[2] http://www.via.com.tw/en/products/processors/edenX2/
[3] http://cdimage.debian.org/debian-cd/7.5.0/amd64/bt-dvd/
http://cdimage.debian.org/debian-cd/7.5.0/amd64/iso-dvd/
[4] https://www.debian.org/CD/http-ftp/#stable
