# HP 840 G6 Big Sur 11.2.3

Based on work done by:
- https://github.com/kecinzer/hpelitebook850g5-opencore
- https://github.com/Joaotcs/Hackintosh-Elitebook-8x0-g5
- r/hackintosh reddit posts by forgotten hero that helped me with my iGPU :)
- Dortania'a Guide of all guides
- forums, etc..

I didn't fork kecinzer or Joaotcs repo's since I didnt keep track of all changes made from the beginning, but most of the heavy work was done by them. So FW your praises to them :)

Changes from kecinzer repo:
- SMBIOS changed to MacBookPro 15,2 since my CPU is the most similar to this series
- Since SMBIOS changed CPU also changed from CP00 to PR00, so had to modify SSDT-PLUG for PR00 
- Fixed sound - ALC215 layout-id 18 for HP 830 G6 thanks to 965987400abc
- Fixed iGPU patches with the help of forgotten hero from reddit/hackintosh, added some more atributes that fixed external HDMI and DP output from HP UltraSlim dock and wake from sleep issues
- Created new USBPorts.kext using Hackintool until I found combo that works great with HP UltraSlim dock USB's and doesn't break sleep
- Created custom CPUFriend based on Fewt's fork of CPUFriendFriend, using MacBook Air values for better battery life
- Added SSDT-XOSI for trackpad fix
- Configured OpenCanopy and custom icons
- New OpenCore extra security options not used


My config:
- i5 8265U (UHD 620)
https://www.notebookcheck.net/HP-EliteBook-840-G6-6XD76EA.441613.0.html

- **Upgrade your BIOS to latest version!**.
- **Set iGPU to 64MB in BIOS**
- **Generate your own serial etc. https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html#generate-a-new-serial**

Using itlwm Airport version for integrated Intel AX200, working perfectly for me:
- 802.11n only for now. 
- Bluetooth working great.
- I prefer this option much more then Broadcom bcm94352z and BCM94360NG (Plug and Play) since they often have problems with Power management enabled/freezing. Especially if using multi-boot with Windows or Linux like I am.

Almost everything works except:
- integrated microphone/3.5mm microphone input(only sound output works)   :(
- Bluetooth microphone (worked on BCM94360NG with Galaxy Buds)
- Fibocom WWAN
- Hibernate
- Keyboard Nipple ;) and buttons 

Buggy:
- sometimes after upgrading to Big Sur and/or installing newer VoodooI2c I encountered some weird trackpad behavior while trying to mark text or drag-and-drop using touchpad and two fingers. For example I would click(mark) on the begining of the text with 1 finger on the bottom left, and hold it..while using second finger to mark a text or drag-and-drop, but as soon as I lift the second finger (but still holding first finger bottom left (aka virtual left mouse press area)) the text gets unmarked (or drag and drop gets - dropped) as If I removed my first finger from bottom left(I didnt :). IDK why or when it started to happen but It annoys me alot :/. If anybody figures it out, please let me know!
