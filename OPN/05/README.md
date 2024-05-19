https://github.com/dh0ck/Wi-Fi-Pentesting-Cheatsheet/blob/main/Wifi/cheatsheet/0%20-%20connect%20to%20networks.md\#config-file-for-open-network

`sudo wpa_supplicant -Dnl80211 -i wlan0 -c wifi-client.conf`

    `-Dnl80211`: This option specifies the wireless driver to be used by wpa_supplicant. In this case, it's using the nl80211 driver, which is a common driver for Linux systems that supports modern Wi-Fi features.

    -i wlan0: This option specifies the wireless interface to be used. In this case, it's wlan0, which is a common name for the first wireless network interface in Linux systems.

    -c wifi-client.conf: This option specifies the configuration file to use for wpa_supplicant. In this case, it's wifi-client.conf. This file likely contains the configuration settings for the Wi-Fi network the user wants to connect to.

So, altogether, the command is telling wpa_supplicant to use the nl80211 driver, connect using the wlan0 wireless interface, and use the configuration settings specified in the wifi-client.conf file. The sudo at the beginning ensures that the command is executed with administrative privileges, which may be necessary for managing network interfaces and connections.

# request an ip by dhcp, once we are connected to an AP
`dhclient -v wlan0`