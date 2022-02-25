# RasPi NTP Server

## 2021-12-24

#note

---

## Goal
NTP or Network Time Protocol is a protocol that is used to synchronize all system clocks in a network to use the same time. The following instructions show how to set up a RasPi as an NTP server.

This following instructions assume that the Ras-Pi is connected to the internet.

## Instructions
1. Install NTP server on the host computer
```bash
sudo apt install ntp
```

2. Configure NTP server
```bash
sudo vim /etc/ntp.conf
```

![[Pasted image 20211224120617.png]]