# Pixelflut_learnings

## ethtool

`ethtool -k lo`. List all features. Turn on with: `ethtool -K lo gro (on/off)`

`ethtool -g enp3s0f0`. List ring buffer

## iptables
`iptables -S`. List rules

### create
`iptables -t filter -I INPUT -p tcp --syn --dport 1234 -m connlimit --connlimit-above 10 --connlimit-mask 32 -j DROP`. Create Rule for 10 connections per ip

`iptables -t filter -I INPUT -p tcp --syn --dport 1234 -m connlimit --connlimit-above 10 --connlimit-mask 32 -j REJECT --reject-with tcp-reset` Some more fancy limitiation with reset


`iptables -L INPUT -v`. show statistiks

### delete

`iptables -L INPUT -v --line-numbers` gives line number.
Ddelete with `iptables -D INPUT <number>`

## Client
Kill client connections: `ss -K dst 127.0.0.1 dport = 1234`


## Ausprobieren mit echter NIC:
MTU bei 1500 lassen und Segmentation Offload ausprobieren
Anzahl Queues ausprobieren
Spectre und Meltdown-Patches deaktivieren
