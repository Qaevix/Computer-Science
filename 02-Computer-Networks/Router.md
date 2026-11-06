# 📡 Router

> A router forwards IP packets between networks.

## How It Works

Each router interface connects to a network. When a packet arrives, the router looks up its destination IP address in the routing table, selects a next hop or outgoing interface, and forwards it in a new link-layer frame. The router decreases IPv4 TTL or IPv6 Hop Limit to limit forwarding loops.

A host normally sends traffic for destinations outside its subnet to a **default gateway**. The gateway's address must be reachable on the local link. A home gateway often also runs DHCP, NAT, and Wi-Fi, but packet forwarding is the router's core role.

## Example

A PC at `192.168.10.10/24` can reach `192.168.10.20` directly. To reach `192.168.20.20`, it can send the packet through its gateway at `192.168.10.1`. The router needs a route to the destination, and the remote side needs a return path.

## Practice

In Packet Tracer, connect one PC to each of two router interfaces. Use `192.168.10.1/24` and `192.168.20.1/24` for the router and a `.10` address for each PC. Enable the router interfaces and set each PC's gateway to its local router address. Ping each gateway before testing across the router.

[← Computer Networks](./README.md) · [Next: Switch →](./Switch.md)
