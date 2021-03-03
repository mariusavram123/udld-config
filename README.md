# Unidirectional Link Detection(UDLD) configuration

This lab has been build using GNS3.
Objectives:
* Configure UDLD on interface fa0/16 of both switches, use aggressive mode.
* Configure a MAC filter on SW2 that filters MAC address 0100.0ccc.cccc to simulate a link failure.

[x] Configure the ports e0/0 on both switches to use UDLD in aggressive mode
```
interface e0/0
udld port aggressive
```

[x]Configure a MAC access list to filter the MAC address 0100.0ccc.cccc (UDLD MAC address)
```
mac access-list extended UDLD-FILTER
deny any host 0100.0ccc.cccc
permit any any

int e0/0
mac access-group UDLD-FILTER in
```


## Documentantion

https://www.cisco.com/c/en/us/td/docs/switches/lan/catalyst3750/software/release/12-2_52_se/configuration/guide/3750scg/swudld.html