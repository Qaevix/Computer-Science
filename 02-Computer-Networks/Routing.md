# 🧭 Routing

> Routing determines where to send packets on their way to another network.

| Route type | How it appears |
| :--- | :--- |
| Connected | Added for a network on an active router interface |
| Static | Configured manually with a destination prefix and next hop or exit interface |
| Dynamic | Learned through a routing protocol such as OSPF |
| Default | Used when no more specific route matches, such as `0.0.0.0/0` for IPv4 |

## Longest Prefix Match

If a routing table has `192.168.0.0/16` and `192.168.20.0/24`, traffic for `192.168.20.40` follows the `/24` route because it matches more bits of the destination. Check the return route as well as the forward route.

## NAT and PAT

**NAT** translates IP addresses at a network boundary. **PAT**, also called NAT overload, lets many internal connections share one external IPv4 address by translating transport ports for TCP and UDP. Routing selects a path. Translation changes addressing information on that path.

## Practice

Connect R1 and R2 over `10.0.0.0/30`, with R1 at `10.0.0.1` and R2 at `10.0.0.2`. Place `192.168.10.0/24` behind R1 and `192.168.20.0/24` behind R2. In Cisco IOS global configuration mode, add:

```text
R1(config)# ip route 192.168.20.0 255.255.255.0 10.0.0.2
R2(config)# ip route 192.168.10.0 255.255.255.0 10.0.0.1
```

Give each PC its local router interface as its gateway. Check `show ip route`, then ping between the two PCs.

[← Computer Networks](./README.md) · [Next: Network Security →](./Network-Security.md)
