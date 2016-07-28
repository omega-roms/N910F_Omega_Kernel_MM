HOW TO BUILD KERNEL FOR SM-N910F_EUR_MM_XX

1. How to Build
	- get Toolchain
		From android git server , codesourcery and etc ..
		 - arm-eabi-
		
	- edit Makefile
		edit "CROSS_COMPILE" to right toolchain path(You downloaded).
       		  Ex)  export CROSS_COMPILE=/opt/toolchains/arm-eabi-4.7/bin/arm-eabi-          // check the location of toolchain
		$ export CROSS_COMPILE=(compiler path)
		$ export ARCH=arm
		$ mkdir output
		$ make -C $(pwd) O=output apq8084_sec_defconfig VARIANT_DEFCONFIG=apq8084_sec_trlte_eur_defconfig SELINUX_DEFCONFIG=selinux_defconfig
		$ make -C $(pwd) O=output 
		$ cp output/arch/arm/boot/zImage arch/arm/boot/zImage

2. Output filesS
	- Kernel : output/arch/arm/boot/zImage
	- module : output/drivers/*/*.ko

3. How to Clean	
		$ cd output
		$ make clean
			
4. How to make .tar binary for downloading into target.
	- change current directory to Kernel/arch/arm/boot
	- type following command
	$ tar cvf SM-N910F_EUR_MM_XX.tar zImage
		
		
		