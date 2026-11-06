# 🧩 VLAN

> A virtual LAN separates a switched network into distinct Layer 2 broadcast domains.

## Access Ports and Trunks

An **access port** normally connects an end device to one VLAN and sends ordinary untagged Ethernet frames to it. A **trunk** carries multiple VLANs between devices, typically using IEEE 802.1Q tags. On a typical Cisco trunk, traffic for the native VLAN can be untagged. Configure the native VLAN consistently at both ends.

Hosts in different VLANs usually use different IP subnets. They need a Layer 3 device, such as a router with subinterfaces or a Layer 3 switch with VLAN interfaces, to exchange traffic. Routing policies determine which traffic is allowed.

## Practice

On a Cisco switch in Packet Tracer, create VLANs 10 and 20 with `vlan 10` and `vlan 20` in global configuration mode. On each PC port, use `switchport mode access` and `switchport access vlan 10` or `20`. Put two PCs in VLAN 10 and a third in VLAN 20. Assign addresses from one subnet per VLAN.

Run `show vlan brief` to check port membership. Confirm the VLAN 10 PCs can ping each other. Without an inter-VLAN gateway, expect a ping to VLAN 20 to fail.

[← Computer Networks](./README.md) · [Next: Routing →](./Routing.md)
