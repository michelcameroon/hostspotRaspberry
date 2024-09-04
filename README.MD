we need a easy way to build the raspberry, which can function as hotspot

this example was done with a rsapberry pi 3 with lite 64 bits. 
we will not touch out internal wifi it is there to vie us interenet

we have an external usb wifi this will be our hotspot wlan1

hostspot
from

https://gist.github.com/narate/d3f001c97e1c981a59f94cd76f041140





    5  nmcli con add type wifi ifname wlan1 con-name Hostspot autoconnect yes ssid waterHostspot
    6  sudo nmcli con add type wifi ifname wlan1 con-name Hostspot autoconnect yes ssid waterHostspot
    7  nmcli con modify Hostspot 802-11-wireless.mode ap 802-11-wireless.band bg ipv4.method shared
    8  sudo nmcli con modify Hostspot 802-11-wireless.mode ap 802-11-wireless.band bg ipv4.method shared
    9  sudo nmcli con modify waterHostspot wifi-sec.key-mgmt wpa-psk
   10  sudo nmcli con modify Hostspot wifi-sec.key-mgmt wpa-psk
   11  sudo nmcli con modify Hostspot wifi-sec.psk "topstoHretaw"
   12  sudo nmcli con up Hostspot
   13  ip addr
   14  nmcli con show


now we have an hotspot

we can reach the machine 
ping raspberrypi.local

this gives the ip but careful when we restart this ip can change and we cannot login.





this give us the ip of the 
