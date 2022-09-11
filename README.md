# CTF_ADDA_writeups
Writeups for https://ctf.adda.gov.ae/ 2022

## Challenge: `Folders`
Solution:
```bash
$ pip install folders
$ unzip New_Folder.zip
$ Folder New\ Folder
#output will contain flag
```

References:  
https://github.com/SinaKhalili/Folders.py  
https://esolangs.org/wiki/Folders 

## Challenge: `CatCoffee`
Solution:  
Open provided pcap file in wireshark.  
Goto Wireless > WLAN traffic > 12 Auths can be seen for CatCoffee SSID  
Crack auth with aircrack-ng: `aircrack-ng -w rockyou.txt -b 00:21:29:77:a3:05 traffic.pcap`  
In Wireshark goto: Edit > Preferences > Protocols > IEEE 802.11 > Edit  
Create new entry with Key Type as wpa-pwd and key with that obtained from aircrack-ng.  
Then Goto Wireshark > File > Export Objects > HTTP and save resources to a file  
Resources will have a file named flag.txt containing the flag.  
References:  
https://book.hacktricks.xyz/generic-methodologies-and-resources/basic-forensic-methodology/pcap-inspection/wifi-pcap-analysis   
