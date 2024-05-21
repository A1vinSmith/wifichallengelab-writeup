1. ```bash
sudo wpa_supplicant -iwlan2 -c wifi-mobile.conf
Successfully initialized wpa_supplicant
wlan2: SME: Trying to authenticate with f0:9f:c2:71:22:12 (SSID='wifi-mobile' freq=2437 MHz)
wlan2: Trying to associate with f0:9f:c2:71:22:12 (SSID='wifi-mobile' freq=2437 MHz)
wlan2: Associated with f0:9f:c2:71:22:12
wlan2: CTRL-EVENT-SUBNET-STATUS-UPDATE status=0
wlan2: WPA: Key negotiation completed with f0:9f:c2:71:22:12 [PTK=CCMP GTK=TKIP]
wlan2: CTRL-EVENT-CONNECTED - Connection to f0:9f:c2:71:22:12 completed [id=0 id_str=]
wlan2: CTRL-EVENT-DISCONNECTED bssid=f0:9f:c2:71:22:12 reason=3 locally_generated=1
wlan2: SME: Trying to authenticate with f0:9f:c2:71:22:12 (SSID='wifi-mobile' freq=2437 MHz)
wlan2: Trying to associate with f0:9f:c2:71:22:12 (SSID='wifi-mobile' freq=2437 MHz)
wlan2: Associated with f0:9f:c2:71:22:12
wlan2: CTRL-EVENT-SUBNET-STATUS-UPDATE status=0
wlan2: WPA: Key negotiation completed with f0:9f:c2:71:22:12 [PTK=CCMP GTK=TKIP]
wlan2: CTRL-EVENT-CONNECTED - Connection to f0:9f:c2:71:22:12 completed [id=0 id_str=]

sudo dhclient wlan2 -v
Internet Systems Consortium DHCP Client 4.4.3-P1
Copyright 2004-2022 Internet Systems Consortium.
All rights reserved.
For info, please visit https://www.isc.org/software/dhcp/

Listening on LPF/wlan2/8e:d6:b2:19:83:66
Sending on   LPF/wlan2/8e:d6:b2:19:83:66
Sending on   Socket/fallback
DHCPREQUEST for 192.168.19.84 on wlan2 to 255.255.255.255 port 67
DHCPREQUEST for 192.168.19.84 on wlan2 to 255.255.255.255 port 67
DHCPDISCOVER on wlan2 to 255.255.255.255 port 67 interval 6
DHCPOFFER of 192.168.2.30 from 192.168.2.1
DHCPREQUEST for 192.168.2.30 on wlan2 to 255.255.255.255 port 67
DHCPACK of 192.168.2.30 from 192.168.2.1
bound to 192.168.2.30 -- renewal in 41209 seconds.
```

2. To impersonate, need to use the cooike from 09 of lab.php