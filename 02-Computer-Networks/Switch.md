# 🔀 Switch

> An Ethernet switch forwards frames between devices on the same LAN.

## MAC Learning and Forwarding

The switch learns the **source MAC address** of each incoming frame and records its port and VLAN. If it knows the destination MAC address, it forwards the frame through the associated port when that port differs from the incoming port. It floods broadcasts and unknown unicasts out eligible ports in the same VLAN, excluding the incoming port.

MAC table entries age out. Spanning Tree can block redundant Layer 2 paths so frames do not loop indefinitely.

## Example

When PC0 first sends traffic to PC1, the switch learns PC0's MAC address from the incoming frame. Once PC1 responds, the switch learns PC1's port too. Later unicast frames can go straight to the right port.

## Practice

Complete [Lab 01](./Packet-Tracer-Labs/01-Two-PC-LAN.md). After a successful ping, run `show mac address-table` on the Cisco switch and match the dynamic entries to the two ports.

[← Computer Networks](./README.md) · [Next: Access Point →](./Access-Point.md)
