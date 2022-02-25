# Small Network Switch

## 2021-12-24

#note

---

## Alternative Solution
- Why bother with making a [[Raspberry Pi Router]] that's essentially going to act as a network switch?
- Would it not be simpler and easier to use a small unmanaged switch?


## Devices
- [TP-Link Option 1](https://www.amazon.com.au/TP-Link-TL-SF1005D-V14-100Mbps-Desktop/dp/B0766D8HZ3/ref=sr_1_1?keywords=TP-LINK+TL-SF1005D+5-Port+10%2F100+Mbps+Unmanaged+Desktop+Switch+-+White&qid=1640315058&sr=8-1) 
- [TP-Link Option 2](https://www.amazon.com.au/TP-Link-Litewave-Networking-Auto-Negotiation-LS1005G/dp/B07VC68RW1/ref=sr_1_4?keywords=TP-LINK+TL-SF1005D+5-Port+10%2F100+Mbps+Unmanaged+Desktop+Switch+-+White&qid=1640315058&sr=8-4)


## Possible Downsides
- A switch would expose the GE Medical VLAN completely to the corporate network.
- Might have to introduce a firewall that permits only NTP traffic.