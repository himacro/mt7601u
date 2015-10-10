AP Mode for MT7601 chip
=======================

Many MT7601 based WIFI adapters (like MiWifi/Xiaodu Wifi/360 Wifi 2) have AP-mode support only on Windows from official. It's the AP mode drivers for Linux.

## How to build

1. Edit `etc/Wireless/RT2870AP/RT2870AP.dat` to modify `SSID` and `WPAPSK` as you need.
2. Run `./miwifi_build.sh`

## How to use

1. Install `dhcp` (or maybe `dhcpd`) package depending on your linux distribution.
2. Add the following section into `dhcpd.conf` (usually `/etc/dhcpd.conf`)
  
   ```
   subnet 192.168.199.0 netmask 255.255.255.0 {
      range 192.168.199.100 192.168.199.200;
      option routers 192.168.199.1;
      option domain-name-servers 8.8.8.8;
   }    
   ```
   You should modify it to meet your need.
3. Run `./miwifi_work.sh` with root
4. The access point should works now now if everything goes well.
