# 🧮 Subnetting

> Subnetting divides an address block into smaller networks.

## Read an IPv4 Prefix

The prefix length tells you how many bits are fixed. An IPv4 `/26` leaves six host bits, so each subnet contains `2^6 = 64` addresses. Its mask is `255.255.255.192`. In a conventional LAN subnet, the first address is the network address and the last is the broadcast address, leaving 62 usable host addresses.

| Subnet inside `192.168.10.0/24` | Usable host range | Broadcast |
| :--- | :--- | :--- |
| `192.168.10.0/26` | `.1–.62` | `.63` |
| `192.168.10.64/26` | `.65–.126` | `.127` |
| `192.168.10.128/26` | `.129–.190` | `.191` |
| `192.168.10.192/26` | `.193–.254` | `.255` |

A `/31` point-to-point link and a `/32` host route are special cases. IPv6 has no broadcast address and commonly uses `/64` on LANs.

## Practice

Find the subnet, broadcast address, and usable range for `192.168.10.142/26`.

<details>
<summary>Answer</summary>

The subnet is `192.168.10.128/26`, the broadcast is `192.168.10.191`, and usable addresses run from `192.168.10.129` through `192.168.10.190`.

</details>

[← Computer Networks](./README.md) · [Next: Network Protocols →](./Network-Protocols.md)
