# Hackintosh-u303l

EFI boot folder based on OpenCore for ASUS UX303LA
Last update: November 05th 2024. 

## Description

EFI files based on OpenCore  
OpenCore version: 1.0.2 
Compatible macOS version: __Sonoma 14.x__  
Tested with: __Monterey 12.7.3__ & __Ventura 13.x__  

## How to use  

1/ Download a release corresponding to your macOS version  
2/ Extract it on USB stick (GPT disk with FAT32 primary partition) or EFI partition  
3/ Generate a new "SystemSerialNumber" and "SystemUUID" using OCAuxiliaryTools for example  
4/ Save and reboot  

### Important note: macOS Ventura and Sonoma

Required to patch root with OpenCore Legacy Patcher (actual version 2.0.0)  to enable GPU acceleration.  
To root patch, I edit boot-args and csr-active-config inside config.plist file :  
- amfi_get_out_of_my_way=1 to disable AMFI  
- car-active-confi=EF0F0000 to disable SIP  

Some apps cannot work with this : Steam / Shadow.tech / Music (Apple DRM) / Adobe apps (Illustrator / Photoshop)    

I recommend to use MacOS Monterey for full support.  

MacOS Monterey is the last OS supporting natively HD4000 iGPU.  

## Hardware

__Laptop Toshiba Tecra Z50-A__  
![ASUS UX303L](/Assets/AsusUX303L.jpg "ASUS UX303L")  
[Datasheet ASUS](/Assets/Asus-UX303L-Datasheet.pdf)  

| Type	| Name                   |
|:------|:-----------------------|
| CPU	| Intel i5 4210U	 |
| RAM	| 2xDDR3l 1600MHz - 8Gb  |
| GPU	| Intel HD Graphics 4400 |
| Drive	| SATA SSD 500 Gb	 |
| Sound	card	| Realtek ALC283	 |
| WLAN	| Intel Wireless 7260 N	 |
| Bluetooth | Intel Wireless 7260 #Port008 |
| Display | LVDS or eDP display |

## SMBIOS Info

System Product Name : Macbook Pro 16.4  
System Serial : xxxxxxx    

## Working and Not-Working

### Testing
WIFI : ok  
GPU : ok   
Shutdown/Restart : ok  
USB Port : ok  
Sound : ok (speakers and microphone)  
Brightness : ok  
Webcam : ok  
Keyboard : ok  
Card Reader : ok  
Bluetooth : ok  
Auto-unlock : with BLEUnlock  
Boot shime : ok

### Working with issue

### Not-Working

HDMI port: doesn't work at all. Not included in this Macbook Pro SMBIOS.  

## Screenshots

### macOS Monterey 12.7.1  
Last OS with native HD4400 support (no root patch)  
![ASUS UX303L Monterey](/Assets/Monterey.png "ASUS UX303L")
![ASUS UX303L SystemInfo](/Assets/SystemInfo.png "ASUS UX303L")
![ASUS UX303L SystemSettings](/Assets/SystemSettings.png "ASUS UX303L")
![ASUS UX303L OCAuxiliaryTools](/Assets/OCAuxiliaryTools.png "ASUS UX303L")

## Work to do

Improve HDMI support  
Improve ALPS Touchpad support  
Try to upgrade Monterey to Ventura or Sonoma : works (but need OpenCore Legacy Patcher)  

## About Boot Shime
I added boot shime. It can be disable by turning "AudioSupport" OFF in config.plist (section UEFI/Audio).  

## Credit

EFI Base folder : https://github.com/arduinovc/hackintosh-z50  
