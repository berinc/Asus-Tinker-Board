# Asus-Tinker-Board
Asus tinker board setup and guide's:

Photos of the shell for the tinker board: 
https://photos.google.com/share/AF1QipNjUL9VJW4BIh58ZOHM6jOWS10l43lfzL_nr7FMD-YXm_o6hG63BfTN2Rv6ch6C_Q?key=OVV0UTBXUmF0NXNSR2NKVzdoaFhxQzVTbDI5V3JB


As I slowly build up this guide, I aim to produce a basic users guide to the tinker board helping people whom are interested in the tinker board have a more level or down hill experience in fulfilling there desires of a fully working and stable system.

First and foremost, some basics to know and understand about the tinker board. This will save you many hours of research and anger. Great resource for information https://tinkerboarding.co.uk/

1: The Tinker board is finicky about its power supply AND THE VOLTAGE SUPPLIED. I strongly suggest you power the board via both the micro usb and the GPIO pins. The micro usb and dual 5v GPIO pins are directly linked. The micro USB connector is NOT designed for the power requirements of the board and causes a voltage drop often down to 4.73V during boot. When the voltage falls to low the board will reboot causing a reboot cycle. This is a major design goof by ASUS. I am shocked and awed that ASUS let a flaw such as that go by them. So if your board seems to cycle reboot, chances are your board is just fine and your PSU is the issue.

2: Power the board with stable regulated 5.25 to 5.3V and 2.5 or more amps minimum "usb is rated for 5.6v absolute max". I use to do a lot of quad-copter and RC car racing, so I had on hand many small parts including a nice dc-dc power supply that has worked flawlessly. The higher range 5.3v voltage helps maintain a higher current level, because more current can flow with less heat production. I used the castle BEC DC-DC http://www.castlecreations.com/en/cc-bec-010-0004-00 This power supply can be programmed to output any voltage with in its working range. And has a wide DC input range. Adjusting the voltage requires the programmer from CASTLE to set the voltage output FYI. There are many other BEC power supplies that may work as well for a psu. My main power supply is an old laptop 12v 6amp brick. 

3: Short list of some Sdcard images. https://www.armbian.com/tinkerboard/ ARMBIAN based most mature and stable IMO, https://www.asus.com/us/Single-Board-Computer/Tinker-Board/ original tinker board link, tinker board S is the second model. Only major difference is the addition of an EMMC storage extra HDMI features and one or 2 other small adjustments and 2x the price. https://www.asus.com/us/Single-Board-Computer/Tinker-Board-S/ newest model  and 100% software compatable with original tinker board. https://github.com/EriHoss/TinkerRetroPie/releases tinker board retropi game emulation. https://sourceforge.net/projects/tinkerboard/files/ based on tinker OS with lots of added features. If anyone is looking for an SD card image based on armbian with full preempt RT using kernel 4.4 or 4.19 contact me.

4: Enabling 3D graphics on armbian    first apt-get update/upgrade then	apt-get install libglfw3-dev libgles2-mesa-dev gcc  https://forum.armbian.com/topic/7262-rk3288-media-script-tinkerboard/?page=5&tab=comments#comment-74409 see this link for more help on 3D. FYI libegl1-mesa-dev has dependency issues that I have run into dont install it.. if you get issues apt-get remove it...   installing these drivers etc... may work on other distros as well I have not tested. More to do with enabling 3D opengl -->  https://forum.armbian.com/topic/6934-stability-problem-tinker-board/
