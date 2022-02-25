# Raspberry Pi Router

## 2021-12-13

#networking #raspi #router

---
## Goal
- Creating a device which can route traffic between 2 VLANS so that an isolated network and sync it's time to the hospital time sync server.


## Configuring the Network
1. Create a network configuration file for the first network (*e.g. eth1*)
```bash
sudo vim /etc/network/interface.d/eth1
```

2. Add the following into the new file
```bash
allow-hotplug eth1
iface wlan0 inet dhcp
		wpa-conf /etc/wpa_supplicant/wpa_suppluicant.conf
```

3. Create a network configuration file for the second network (*eth0*)
```bash
sudo vim /etc/network/interface.d/eth0
```

4. Add the following into the new file
```bash
auto eth0  
iface eth0 inet static  
address 192.168.100.1  
netmask 255.255.255.0
```

5. Disable the dhcpcd service
```bash
sudo systemctl disable dhcpcd
```

Note: Network configuration changes will only come into effect on the next reboot


## Checking Configuration Changes
To ensure that the specified network configuration has applied correctly, input the following code:

```bash
ip addr show eth1
ip addr show eth0
```


## Resources
- [Raspberry Pi Wired Router](https://linuxhint.com/raspberry_pi_wired_router/)
- [Dual NIC RasPi](https://www.seeedstudio.com/Rapberry-Pi-CM4-Dual-GbE-Carrier-Board-p-4874.html)