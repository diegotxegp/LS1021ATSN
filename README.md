# LS1021ATSN
Instructions for compiling and creating a OS image SD card for a LS1021ATSN switch

Ubuntu 16.04

sudo apt install git
sudo apt install autoconf
sudo apt install dh-autoreconf

$ git clone https://github.com/openil/openil.git
$ cd openil
# checkout to the 201908 v1.6 release
$ git checkout OpenIL-201908 -b OpenIL-201908

$ unset PERL_MM_OPT

$ cd openil
$ make nxp_ls1021atsn_defconfig
$ make

COMPILING... WAITING FOR HOURS...

$ cd output/images
# Plug your SD card and check what storage unit is on your computed. According to this, replace "x" in the next command
$ sudo fdisk -l
$ sudo dd if=./sdcard.img of=/dev/sd<x>
