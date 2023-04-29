# DigiFri
Project files for making my own APRS Digipeater / IGate with the le potato SBC

Inspired by the work of KM6LYW's DigiPi project which packs every Digital mode under the Sun it raspberry pi. This project isn't so ambitious but since raspberries are still out of season at the moment I thought I'd work on building one using a commonly availble low cost SBC, 'le Potato' from Libre computers. 
## Phase I - Complete
Working APRS Digipeater using the following Hardware:
  + Le Potoato ($35)
  + Digirig interface ($60)
  + Baofeng UV5R HT ($20)
  
Up and running using the raspian 10 OS build from the Libre repository. No drivers were needed for the Digirig and all the Heavy lifting is done by the MOST EXCELLENT software TNC, DIREWOLF. Getting it up and running was aoccomplished using the Direwolf documents on APRS using raspberry pi. 
Direwolf has great Network capabilities was able to connect to the pi via TCP/IP with both Pinpoint APRS from a Windows machine and APRSdroid from my Phone.
## Phase II - Complete
Make it wireless and autostart
  + Add '2A4M1' Wifi dongle ($10)
  
This too was rather seamless (although could not get it to work on the 'lite' version of raspian. 
A little more involve was making Direwolf start on boot. to do this I followed the instructions detailed at [Marold's Blog](https://www.marrold.co.uk/2019/04/installing-direwolf-15-on-raspberry-pi.html) which details how to make Direwolf a service and redirects its output to a logfile. The only adjustment I needed to make was to add user 'direwolf' to the 'dialout' group it could access /DEV/ttyUSB0 for the PTT method I am using on the Digirig. 
###Checking in on the direwolf service
using a ssh connection you can:
+ check if direwolf is running by: `systemctl status direwolf`
+ restart direwolf by: `systemctl restart direwolf`
+ monitor the logfile by: `tail -n 100 -f /var/log/direwolf/direwolf.log`

## Phase III
Make it more wireless
Thinking that would be the best way to communicate 'in the wild' vs. WiFi???
  + Add 'BTD400' Bluetooth dongle ($13)
## Phase IV
Replace Digirig (-$60) with a CM108 ($8) soundcard. 
