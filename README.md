<h1> Infinity Kernel </h1>

<h3> For Micromax A106 & Clone Devices </h3>

> Micromax A106 (Unite 2) upstreamed kernel v3.4.113. All new stuffs added including (OC, Gov, Hotplugs, cpio, io schedulers,etc). Thanks to my brother Manjot Sidhu for releasing Kernel Source.
Custom Kitkat Kernel Source For Wiko Bloom , Micromax Unite 2 and other clones.
------
Version :- 3.4.113 (Kitkat)

Status :- Stable

Bugs :- N/A

Contributors
------
>GOD , Sunmughan Swamy(Maintainer) , Manjot Sidhu (Created this Kernel Source) , Monty Kumar(helping) , Sandeep Sethi(helped me always) , Ranjan(mentor) , Divyrajsinh Jadeja(Tester) , Anurag D'Cruz(motivator) and each and every person of unite 2 who inspired Manjot Sidhu to do this outstanding work... Thank You very Much Manjot Sidhu... You would always remember in my heart for your contribution. 

Introduction
------
Stock Kernel Source based on stock kitkat for Wiko Bloom , Micromax Unite 2 , Explay Vega and MyPhone Rio Lite.
Here are some codenames to be used for these clones

| Vendor (Manufacturer)| Device Name   | CodeName  |
|:-------------:|:-------------:|:---------:|
| Wiko          | Bloom         |   wiko    |
| Micromax      | A106          |   a106    |
| Explay        | Vega          |   vega    |
| MyPhone       | Rio Lite      |   rio     |

Requirements
------
* Ubuntu 10.0 + [Recommended(Ubuntu 16.04 LTS/Linux Mint 18.1 Cinnamon)] 
* Essential kernel Packages
* Android Device To Test
* Common Sense (which is not so common)
* Setting Up The Build Environment
------
>NOTE :- Do first ```sudo apt get-update``` before installing any packages 

1. <strong>Essential Kernel Packages</strong>
 ```
sudo apt-get install mingw-w64 git gnupg flex bison gperf build-essential zip curl libc6-dev libncurses5-dev:i386 x11proto-core-dev libx11-dev:i386 libreadline6-dev:i386 libgl1-mesa-glx:i386 libgl1-mesa-dev g++-multilib mingw32 tofrodos python-markdown libxml2-utils xsltproc zlib1g-dev:i386 git-core lzop ccache gnupg flex bison gperf build-essential zip curl zlib1g-dev zlib1g-dev:i386 libc6-dev lib32ncurses5 lib32z1 lib32bz2-1.0 lib32ncurses5-dev x11proto-core-dev libx11-dev:i386 libreadline6-dev:i386 lib32z-dev libgl1-mesa-glx:i386 libgl1-mesa-dev g++-multilib mingw32 tofrodos python-markdown libxml2-utils xsltproc readline-common libreadline6-dev libreadline6 lib32readline-gplv2-dev libncurses5-dev lib32readline5 lib32readline6 libreadline-dev libreadline6-dev:i386 libreadline6:i386 bzip2 libbz2-dev libbz2-1.0 libghc-bzlib-dev lib32bz2-dev libsdl1.2-dev libesd0-dev squashfs-tools pngcrush schedtool libwxgtk2.8-dev python gcc g++ cpp gcc-4.8 g++-4.8 && sudo ln -s /usr/lib/i386-linux-gnu/mesa/libGL.so.1 /usr/lib/i386-linux-gnu/libGL.so
 ```
 ><strong>NOTE:</strong> Some Packages will not be available depending on which ubuntu version u are , so the packages u will get error just remove them from commands

* <strong>Ubuntu 16.04 LTS users use below commands:</strong>
 ```
sudo apt-get install git gnupg flex bison gperf build-essential zip curl libc6-dev libncurses5-dev:i386 x11proto-core-dev libx11-dev:i386 libreadline6-dev:i386 libgl1-mesa-glx:i386 libgl1-mesa-dev g++-multilib tofrodos python-markdown libxml2-utils xsltproc zlib1g-dev:i386 git-core lzop ccache gnupg flex bison gperf build-essential zip curl zlib1g-dev zlib1g-dev:i386 libc6-dev lib32ncurses5 lib32z1 lib32ncurses5-dev x11proto-core-dev libx11-dev:i386 libreadline6-dev:i386 lib32z-dev libgl1-mesa-glx:i386 libgl1-mesa-dev g++-multilib tofrodos python-markdown libxml2-utils xsltproc readline-common libreadline6-dev libreadline6 libncurses5-dev lib32readline6 libreadline-dev libreadline6-dev:i386 libreadline6:i386 bzip2 libbz2-dev libbz2-1.0 libghc-bzlib-dev libsdl1.2-dev libesd0-dev squashfs-tools pngcrush schedtool python gcc g++ cpp gcc-4.8 g++-4.8 && sudo ln -s /usr/lib/i386-linux-gnu/mesa/libGL.so.1 /usr/lib/i386-linux-gnu/libGL.so
```
* <strong>Note:<strong> If you have no idea about packages then type this command
```
sudo apt-get install build-essential
```

 2. <strong>Go to etc/udev/rules.d/51-android.rules  and add these codes at the end</strong>
 >NOTE :- If file doesnot exist create one ... if u get permission eror then give permsission to folder , ```sudo chmod 777 -R rules.d```
 ```
 # adb protocol on passion (Nexus One)
SUBSYSTEM=="usb", ATTR{idVendor}=="18d1", ATTR{idProduct}=="4e12", MODE="0600", OWNER="<username>"
# fastboot protocol on passion (Nexus One)
SUBSYSTEM=="usb", ATTR{idVendor}=="0bb4", ATTR{idProduct}=="0fff", MODE="0600", OWNER="<username>"
# adb protocol on crespo/crespo4g (Nexus S)
SUBSYSTEM=="usb", ATTR{idVendor}=="18d1", ATTR{idProduct}=="4e22", MODE="0600", OWNER="<username>"
# fastboot protocol on crespo/crespo4g (Nexus S)
SUBSYSTEM=="usb", ATTR{idVendor}=="18d1", ATTR{idProduct}=="4e20", MODE="0600", OWNER="<username>"
# adb protocol on stingray/wingray (Xoom)
SUBSYSTEM=="usb", ATTR{idVendor}=="22b8", ATTR{idProduct}=="70a9", MODE="0600", OWNER="<username>"
# fastboot protocol on stingray/wingray (Xoom)
SUBSYSTEM=="usb", ATTR{idVendor}=="18d1", ATTR{idProduct}=="708c", MODE="0600", OWNER="<username>"
# adb protocol on maguro/toro (Galaxy Nexus)
SUBSYSTEM=="usb", ATTR{idVendor}=="04e8", ATTR{idProduct}=="6860", MODE="0600", OWNER="<username>"
# fastboot protocol on maguro/toro (Galaxy Nexus)
SUBSYSTEM=="usb", ATTR{idVendor}=="18d1", ATTR{idProduct}=="4e30", MODE="0600", OWNER="<username>"
# adb protocol on panda (PandaBoard)
SUBSYSTEM=="usb", ATTR{idVendor}=="0451", ATTR{idProduct}=="d101", MODE="0600", OWNER="<username>"
# adb protocol on panda (PandaBoard ES)
SUBSYSTEM=="usb", ATTR{idVendor}=="18d1", ATTR{idProduct}=="d002", MODE="0600", OWNER="<username>"
# fastboot protocol on panda (PandaBoard)
SUBSYSTEM=="usb", ATTR{idVendor}=="0451", ATTR{idProduct}=="d022", MODE="0600", OWNER="<username>"
# usbboot protocol on panda (PandaBoard)
SUBSYSTEM=="usb", ATTR{idVendor}=="0451", ATTR{idProduct}=="d00f", MODE="0600", OWNER="<username>"
# usbboot protocol on panda (PandaBoard ES)
SUBSYSTEM=="usb", ATTR{idVendor}=="0451", ATTR{idProduct}=="d010", MODE="0600", OWNER="<username>"
# adb protocol on grouper/tilapia (Nexus 7)
SUBSYSTEM=="usb", ATTR{idVendor}=="18d1", ATTR{idProduct}=="4e42", MODE="0600", OWNER="<username>"
# fastboot protocol on grouper/tilapia (Nexus 7)
SUBSYSTEM=="usb", ATTR{idVendor}=="18d1", ATTR{idProduct}=="4e40", MODE="0600", OWNER="<username>"
# adb protocol on manta (Nexus 10)
SUBSYSTEM=="usb", ATTR{idVendor}=="18d1", ATTR{idProduct}=="4ee2", MODE="0600", OWNER="<username>"
# fastboot protocol on manta (Nexus 10)
SUBSYSTEM=="usb", ATTR{idVendor}=="18d1", ATTR{idProduct}=="4ee0", MODE="0600", OWNER="<username>"
```
3. <strong>Add The below code at the end of etc/bash.bashrc</strong>
```
export USE_CCACHE=1
```

4. <strong>JDK 1.6 (6u45)</strong>

Download jdk1.6 6u45 from here :- http://www.oracle.com/technetwork/java/javase/downloads/java-archive-downloads-javase6-419409.html
>Download Linux x64 and .bin one

Then go to our downloaded directory and do ``` chmod a+x jdk-6u45-linux-x64.bin```  

Now Extract it by using ```./jdk-6u45-linux-x64.bin  ```

<strong><i>Follow the commands below</i></strong>
```
sudo mkdir /usr/lib/jvm
sudo mv jdk1.6.0_45 /usr/lib/jvm/  
sudo update-alternatives --install /usr/bin/javac javac /usr/lib/jvm/jdk1.6.0_45/bin/javac 1  
sudo update-alternatives --install /usr/bin/java java /usr/lib/jvm/jdk1.6.0_45/bin/java 1  
sudo update-alternatives --install /usr/bin/javaws javaws /usr/lib/jvm/jdk1.6.0_45/bin/javaws 1 
sudo update-alternatives --config javac  
sudo update-alternatives --config java  
sudo update-alternatives --config javaws
ls -la /etc/alternatives/java*
```
Now To Verify java is installed do ```java -version```


5. <strong>Git :-</strong>
```
sudo apt-get install git
```

6. <strong>Python and Make are preinstalled from ubuntu 10.0+</strong>

Compiling Kernel
------

1. <strong>Open Terminal in desktop and First Clone This Repository By</strong> 
```
git clone https://github.com/Droidadda/Infinity_Kernel_Micromax_A106.git
```

2. <strong>Rename cloned folder to kernel_source By</strong>
```
mv Infinity_Kernel_Micromax_A106 ~/kernel_source
```

3. <strong>Now Lets get the toolchain (arm-linux-androideabi-4.7)</strong>
```
cd kernel_source
git clone https://android.googlesource.com/platform/prebuilts/gcc/linux-x86/arm/arm-linux-androideabi-4.7
```
* <strong><i>For (arm-linux-androideabi-4.9)</i><strong>
```
cd kernel_source
git clone https://android.googlesource.com/platform/prebuilts/gcc/linux-x86/arm/arm-linux-androideabi-4.9
```

4. <strong>Some Commands to make kernel source know that we are compiling for a device :p</strong>
> <strong>NOTE:-</strong> MAKE SURE TO REPLACE CODENAME 
* <strong><i>For (arm-linux-androideabi-4.7)</i></strong>
```
export TARGET_BUILD_VARIANT=user TARGET_PRODUCT=(codename) MTK_ROOT_CUSTOM=../mediatek/custom/ TARGET_KERNEL_VERSION=(codename) &&export PATH=~/kernel_source/arm-linux-androideabi-4.7/bin:$PATH&&export CROSS_COMPILE=arm-linux-androideabi-&&export ARCH=arm
````

* <strong><i>For (arm-linux-androideabi-4.9)</i></strong>
```
export TARGET_BUILD_VARIANT=user TARGET_PRODUCT=(codename) MTK_ROOT_CUSTOM=../mediatek/custom/ TARGET_KERNEL_VERSION=(codename) &&export PATH=~/kernel_source/arm-linux-androideabi-4.9/bin:$PATH&&export CROSS_COMPILE=arm-linux-androideabi-&&export ARCH=arm
````

5. <strong>The Main Step </strong>
> <strong>NOTE:-</strong> MAKE SURE TO REPLACE CODENAME
```
./mk (codename) n k
```

It may take time upto 10 mins max 

6. <strong>The compiled Kernel Sourced is generated in out folder</strong>
   If u get error then the error log is in ```out/target/product/(codename)_kernel_err.log ```
>Check error log carefully , your mistakes will be highlighted


7. <strong>If the kernel compiled successfully</strong>
   The newly compiled kernel will be in the folder ```out/target/product/(codename)/obj/kernel_obj/arm/arch/boot/zImage ```


8. <strong>Now We Need To Add Mediatek Header to it</strong>
   Make a new folder in your desktop/source and copy zImage in it ... 

Now copy ```mkimage``` file from ```kernel_source/mediatek/build/tools/ ``` to your new folder (with zImage)
U can also do this
```
cp ~/kernel_source/meditatek/build/tools/mkimage ~/(new folder name)/
```

Now Your Folder should be containing zImage and mkimage

9. <strong>Final Step</strong>
```
cd ~/(your folder name)/
chmod a+x mkimage
./mkimage zImage KERNEL > zImage_with_header
```

10. <strong>Now in order to test new compiled kernel</strong>
    Just replace ```zImage_with_header ``` with ```kernel``` in your stock boot of stock rom ...

Thank You Very Much <strong>Manjot Sidhu</strong> ...
<strong>Maintained by: Sunmughan Swamy</strong> <3
