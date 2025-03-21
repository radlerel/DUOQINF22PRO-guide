

<div align="center">
 <img src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExdWUxb2R3dWsxZHpzbzhlMnh0N2I0cGZwYTVuczZ6czFnZ3I0MGNjOCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/20ZUHwNogJMB6VgghD/giphy.gif"/>
 <h2>Epic Dumbphone FAQ</h2>
</div>

#### Device characteristics 
```bash
Operating System: Android 12
Processor: MTK Helio G85
Screen: 3.5-inch 640x960 touchscreen
Memory: 4GB RAM (LPDDR4X-1800MHz) + 64GB ROM
Camera: 8MP rear, 2MP front
Battery: 2150mAh
Connectivity: Wi-Fi, Hotspots, Bluetooth
Frequency Bands Supported:
   2G: GSM 2/3/5/8
   3G: WCDMA 1/2/5/8
   4G TDD-LTE: 34/38/39/40/41
   4G FDD-LTE: 1/3/5/7/8/20/28a/28b
Audio: Type-C and TWS headphone compatibility
Size and Weight: 147x58x9mm, 116g
```
#### How to enter in a BROM mode?

First, you need to turn off the phone, then hold down the volume down button and connect the cable to the phone. 

#### How to enter in Fastboot mode? 

We can do that using ADB ( Android Debug Bridge ). Just connect your phone to PC, open the terminal and run : 
```bash 
adb reboot bootloader
```

#### How to enter Recovery mode? 

Lmao, it's stange but if we run :
```bash
adb reboot fastboot
```
We can enter Recovery. Best way. 

## Getting Root. How? 

All we need is an unlocked bootloader, mtkclient with pre-installed drivers, about 20 IQ and a dump of your original firmware. If your bootloader is locked, you can unlock it! Thanks to the wonderful instruction on the GitHub of the Mtkclient project.

Les go -> 

Turn off your phone. Launch mtkclient with a : 
```bash
./mtk.py r boot_a boot_a.img
```
Hold down volume down button and connect dumbphone to PC : 

```bash
MTK Flash/Exploit Client Public V2.0.1 (c) B.Kerler 2018-2024

Preloader - Status: Waiting for PreLoader VCOM, please reconnect mobile to brom mode

Port - Hint:

Power off the phone before connecting.
For brom mode, press and hold vol up, vol dwn, or all hw buttons and connect usb.
For preloader mode, don't press any hw button and connect usb.
If it is already connected and on, hold power for 10 seconds to reset.


......Port - Device detected :)
Preloader - 	CPU:			MT6768/MT6769(Helio P65/G85 k68v1)
Preloader - 	HW version:		0x0
Preloader - 	WDT:			0x10007000
Preloader - 	Uart:			0x11002000
Preloader - 	Brom payload addr:	0x100a00
Preloader - 	DA payload addr:	0x201000
Preloader - 	CQ_DMA addr:		0x10212000
Preloader - 	Var1:			0x25
Preloader - Disabling Watchdog...
Preloader - HW code:			0x707
Preloader - Target config:		0xe0
Preloader - 	SBC enabled:		False
Preloader - 	SLA enabled:		False
Preloader - 	DAA enabled:		False
Preloader - 	SWJTAG enabled:		False
Preloader - 	EPP_PARAM at 0x600 after EMMC_BOOT/SDMMC_BOOT:	False
Preloader - 	Root cert required:	False
Preloader - 	Mem read auth:		True
Preloader - 	Mem write auth:		True
Preloader - 	Cmd 0xC8 blocked:	True
Preloader - Get Target info
Preloader - BROM mode detected.
Preloader - 	HW subcode:		0x8a00
Preloader - 	HW Ver:			0xca00
Preloader - 	SW Ver:			0x0
Preloader - ME_ID:			D547242F43D32F8E865BEE39FB8A2F0E
Preloader - SOC_ID:			0F8E96EDA883C4B85F956121D76F9E79690FBA970C5355F1387E9804640D1D2B
DaHandler - Device is unprotected.
DaHandler - Device is in BROM-Mode. Bypassing security.
PLTools - Loading payload from mt6768_payload.bin, 0x264 bytes
Exploitation - Kamakiri Run
Exploitation - Done sending payload...
PLTools - Successfully sent payload: /home/apis/Utils/mtkclient/mtkclient/payloads/mt6768_payload.bin
Port - Device detected :)
DaHandler
DaHandler - [LIB]: Device is in BROM mode. No preloader given, trying to dump preloader from ram.
DAXFlash - Uploading xflash stage 1 from MTK_DA_V5.bin
XFlashExt - Patching da1 ...
Mtk - Patched "Patched loader msg" in preloader
Mtk - Patched "hash_check" in preloader
Mtk - Patched "Patched loader msg" in preloader
Mtk - Patched "get_vfy_policy" in preloader
XFlashExt - Patching da2 ...
XFlashExt - Security check patched
XFlashExt - DA version anti-rollback patched
XFlashExt - SBC patched to be disabled
XFlashExt - Register read/write not allowed patched
DAXFlash - Successfully uploaded stage 1, jumping ..
Preloader - Jumping to 0x200000
Preloader - Jumping to 0x200000: ok.
DAXFlash - Successfully received DA sync
DAXFlash - Sending emi data ...
DAXFlash - DRAM setup passed.
DAXFlash - Sending emi data succeeded.
DAXFlash - Uploading stage 2...
DAXFlash - Upload data was accepted. Jumping to stage 2...
DAXFlash - Boot to succeeded.
DAXFlash - Successfully uploaded stage 2
DAXFlash - DA SLA is disabled
DAXFlash - EMMC FWVer:      0x0
DAXFlash - EMMC ID:         DH6DMB
DAXFlash - EMMC CID:        150100444836444d42058398cad544a3
DAXFlash - EMMC Boot1 Size: 0x400000
DAXFlash - EMMC Boot2 Size: 0x400000
DAXFlash - EMMC GP1 Size:   0x0
DAXFlash - EMMC GP2 Size:   0x0
DAXFlash - EMMC GP3 Size:   0x0
DAXFlash - EMMC GP4 Size:   0x0
DAXFlash - EMMC RPMB Size:  0x400000
DAXFlash - EMMC USER Size:  0xe8f800000
DAXFlash - HW-CODE         : 0x707
DAXFlash - HWSUB-CODE      : 0x8A00
DAXFlash - HW-VERSION      : 0xCA00
DAXFlash - SW-VERSION      : 0x0
DAXFlash - CHIP-EVOLUTION  : 0x1
DAXFlash - DA-VERSION      : 1.0
DAXFlash - Extensions were accepted. Jumping to extensions...
DAXFlash - Boot to succeeded.
DAXFlash - DA Extensions successfully added
DaHandler - Requesting available partitions ....
DaHandler - Dumping partition "boot_a"
Progress: |██████████| 100.0% Read (0x10000/0x10000, ) 8.34 MB/s3 MB/s
DaHandler - Dumped sector 823296 with sector count 65536 as /home/apis/Utils/mtkclient/boots/boot_a.img.

```

In my firmware i have double boot, so i read both images.

```bash
./mtk.py r boot_b boot_b.img
```

Okay, we have an image (or two images) of boot. Run : 
```bash
./mtk.py reset
```

Turn on our dumbphone. Now we need to install magisk.apk ( if not installed ). Connect phone to PC, run :  
```bash
adb install magisk.apk
```

Launch Magisk. Back to PC, run : 
```bash
adb push boot_a.img /sdcard/Download
adb push boot_b.img /sdcard/Download
```

In Magisk app select "Install" and select boot_a.img -> patch, wait. The same goes for the second boot image ( if you have ). 
 
After patching the image, remember its name. You can find out the name in the explorer ( the patched image will be in the /sdcard/Download folder ). Run : 
```bash
adb shell 
cd /sdcard/Download
ls 
exit
```
If you have two images, remember the name of the patched images so as not to accidentally patch boot_a into boot_b. Run : 

```bash
adb pull /sdcard/Download/magisk_patched***.img boot_a.img
```
Again, if there are two images, we also run it for boot_b.

Finally, turn off your dumbphone king. Using mtkclient run : 

```bash
./mtk.py w boot_a boot_a.img
```

Wait for complete. I will repeat again and again that if we have two images, we run this command for the second boot image. Next : 

```bash
./mtk.py reset
```

Remove the cable. Turn on your phone. Launch Magisk app, root rights successfully obtained!

#### About problem with flahing firmware in SP Flash Tool 

When trying to flash a phone with the SP Flash Tool program, you may encounter a problem with detecting the phone with working drivers, no one knows exactly how this problem occurs, but it exists. The computer itself can see the device as a COM port but at the same time report that the device is faulty, the device can continuously reconnect with some periodicity and disappear from the device manager.

Fix :

Reset bootloader errors! Or put the phone into emergency recovery mode. If you don't have any troubles, then just pull out the battery cable ( the phone case is VERY easy to remove and open the insides, because the Chinese tried very hard on the assembly ), after we remove the case with a credit card or something else, we will see the insides and a thin battery cable that is clamped by a small plate with two gaskets ( wide and thin ), we need a thin screwdriver, we unscrew this plate with it and CAREFULLY disconnect the power cable from the board. Next, connect the phone to the PC and try to flash ( you do not need to hold the volume down button ). Done. 

After you have flashed the phone, assemble it in reverse order, first connect the battery power cable back to the board and put the plate back ( do not mix it up, the correct position of the plate is important ), put the phone back into the case and snap all the notches. Great, everything is ready.

## Over time, I will supplement this guide for this phone and periodically make changes to this repository, attach firmware and various goodies. Thank you all!

#### Links 

Chinese stock firmware with a scatter file : https://drive.google.com/file/d/1di4SMTSEqYivjCX8rALX2yXqw-KAKGSV/view

4PDA Forum Topic : https://4pda.to/forum/index.php?showtopic=1050086

XDA Forum ( Unofficial ) Topic : https://xdaforums.com/t/flash-xiaomi-qin-f22-pro-stock-firmware-with-google-play-with-and-without-root.4509111

SP Flash Tool Download : https://androidmtk.com/smart-phone-flash-tool

MTKClient Github : https://github.com/bkerler/mtkclient

ModemMeta Tool : https://androidmtk.com/download-modemmeta-tool
