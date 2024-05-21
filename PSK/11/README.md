```bash
sudo arp-scan -I wlan2 -l
Interface: wlan2, type: EN10MB, MAC: c2:36:7c:5e:36:a8, IPv4: 192.168.2.30
Starting arp-scan 1.10.0 with 256 hosts (https://github.com/royhills/arp-scan)
192.168.2.1     f0:9f:c2:71:22:12       Ubiquiti Networks Inc.
192.168.2.7     28:6c:07:6f:f9:43       XIAOMI Electronics,CO.,LTD
192.168.2.7     28:6c:07:6f:f9:44       XIAOMI Electronics,CO.,LTD (DUP: 2)
192.168.2.8     28:6c:07:6f:f9:43       XIAOMI Electronics,CO.,LTD
192.168.2.8     28:6c:07:6f:f9:44       XIAOMI Electronics,CO.,LTD (DUP: 2)

5 packets received by filter, 0 packets dropped by kernel
Ending arp-scan 1.10.0: 256 hosts scanned in 2.083 seconds (122.90 hosts/sec). 3 responded

curl 192.168.2.7
flag{QvD1ervLa4EwVh81Tfm0}%         

curl 192.168.2.8
flag{QvD1ervLa4EwVh81Tfm0}% 
```