---
layout: post
title:  the home assistant rabbit hole
categories: blog
---
Another rabit hole - Home Assistant the midnight project

{:refdef: style="text-align: center;"}
![light_switch](/assets/images/image.png){: width="250" }
{: refdef}

Always wanted to automate my home, got a home pod, but sick of always shouting at Siri to get things done.

So I took the hassle to run home assistant over Wireguard on remote vm.

A few key takeaways

- HomeKit requires both mdns and ssdp relay (`mdns-repeater` and `udp-broadcast-relay-redux` was used)
- add routes on openwrt
- Add these entries to wg peer allowed_ips '224.0.0.251/32' '239.255.255.250/32'

And if course, using copilot speeds things up a lot!

refs:

- [Can't get zeroconf/avahi/mDNS reflection to work through WG : r/WireGuard](https://lnkd.in/dHfZDY9D)
- [Since WireGuard is Layer 3, what would is everyone's use case of doing Layer 2 o... \| Hacker News](https://lnkd.in/dP2v9Cj4)
- [Avahi with Wireguard · Issue #262 · avahi/avahi](https://lnkd.in/dG6nhgZX)


originally posted on [LinkedIn](https://www.linkedin.com/feed/update/urn:li:activity:7443094444926468097/)

#homekit #homeassistant #wireguard #openwrt
