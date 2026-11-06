# 🏷️ IP Addressing

> An IP address identifies an interface for communication across IP networks.

## IPv4 and IPv6

| Feature | IPv4 | IPv6 |
| :--- | :--- | :--- |
| Address length | 32 bits | 128 bits |
| Example | `192.168.10.25/24` | `2001:db8:10::25/64` |
| Local neighbor discovery | ARP | Neighbor Discovery via ICMPv6 |

The slash number is the **prefix length**. In `192.168.10.25/24`, the first 24 bits identify the network, `192.168.10.0/24`. IPv6 uses hexadecimal groups, and `::` compresses consecutive zero groups once per address. The IPv6 example above uses a documentation prefix.

## Local and Remote Destinations

If a destination is on-link, the host sends traffic directly. Otherwise it selects a router according to its routes. IPv4 devices can receive their settings from DHCP. IPv6 devices can use router advertisements to learn a default route and can use SLAAC or DHCPv6 for address configuration where supported.

Private IPv4 ranges are `10.0.0.0/8`, `172.16.0.0/12`, and `192.168.0.0/16`. These addresses are used inside local networks and are not routed on the public Internet.

## Practice

Run `ipconfig /all` on Windows. Identify the active adapter's IPv4 address, subnet mask, default gateway, and DNS servers. If it has an IPv6 address beginning with `fe80:`, identify it as link-local.

[← Computer Networks](./README.md) · [Next: Subnetting →](./Subnetting.md)
