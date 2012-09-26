My latest binary build of the Raspberry Pi kernel ( https://github.com/raspberrypi/linux ) with RT patches 40 ( http://www.kernel.org/pub/linux/kernel/projects/rt/3.2/older/patch-3.2.27-rt40.patch.bz2 )  

##WARNING: I **just** applied the patch and fixed one tiny _Makefile_ line, as my skills get me thus far, BCM2708 might very well need some special case patch or something, if you have one do holler  
  
**Source tree:** https://github.com/licaon-kter/linux/tree/rt-3.2.27  
  
**Config file:** https://github.com/licaon-kter/linux/blob/rt-3.2.27/config.myrt1  
  
**Build info:**  
    * kernel source up to patch 14cfebb3a7  
    * gcc version 4.4.5 (Debian 4.4.5-8) from http://wiki.debian.org/EmdebianToolchain crosscompiling on x86_64  
    * make ARCH=arm CROSS_COMPILE=/usr/bin/arm-linux-gnueabi-  
    * Tickless w/ HZ=100  
    * also activated KSM w/ compaction and Cleancache w/ zcache (as a module)  
  
**Contents:**  
    * ./boot: kernel_rt.img main image, to use it add "kernel=kernel_rt.img" (without quotes) to your /boot/config.txt file. More info: http://elinux.org/RPi_config.txt  
    * ./lib/firmware: current build firmware  
    * ./lib/modules: current build modules  
