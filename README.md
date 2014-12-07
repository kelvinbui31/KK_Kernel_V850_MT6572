KONKA_ANDROID_KERNEL_SOURCE DEBUG_CONFIG

1. Android build
  - Download original android source code ( kitkat 4.4.2 ) from http://source.android.com
  - Untar opensource packages of Android.tar.gz into downloaded android source directory
	a) cat Android.tar.gza* | tar zxvpf -
  - And, merge the source into the android source code
  - Run following scripts to build android
    a) source build/envsetup.sh
    b) lunch 1
    c) make
  - When you compile the android source code, you have to add google original prebuilt source(toolchain) into the android directory.
  - After build, you can find output at out/target/product/generic

2. Kernel Build  
  - Uncompress using following command at the android directory
        tar xvzf Kernel.tar.gz  
  - When you compile the kernel source code, you have to add google original prebuilt source(toolchain) into the android directory.
  - Run following scripts to build kernel
  	 a) source build/envsetup.sh
  	 b) lunch aosp_arm-eng
	 -cd kernel directory ( EX: android_mediatek_muse72_s4_kk)
  	 c) cd Kernel
    	 d) make muse72_s4_kk_debug_defconfig ARCH=arm CROSS_COMPILE=arm-eabi- ( change if your toolchain is "arm-linux-guneabi-" )
    	 e) make ARCH=arm CROSS_COMPILE=arm-eabi- ( change if your toolchain is "arm-linux-guneabi-" )

  - After build, you can find the build image(zImage) at arch/arm/boot

3. how to build chromium_lge (vendor\lge\external\chromium_lge\src),
       please refer to README.txt at the folder mentioned above.

----------------------------------TEST AND PREBUILD BY KELVIN--------------------------------------------



