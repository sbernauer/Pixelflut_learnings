# Pixelflut_learnings

## ethtool

`ethtool -k lo`. List all features. Turn on with: `ethtool -K lo gro (on/off)`

`ethtool -g enp3s0f0`. List ring buffer

## iptables
`iptables -S`. List rules

`iptables -t filter -I INPUT -p tcp --syn --dport 1234 -m connlimit --connlimit-above 10 --connlimit-mask 32 -j DROP`
