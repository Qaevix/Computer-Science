# 🧱 OSI and TCP/IP

> Layer models give us a shared vocabulary for describing network communication and isolating faults.

| OSI layers | TCP/IP layer | Examples |
| :--- | :--- | :--- |
| 7 Application, 6 Presentation, 5 Session | Application | HTTP, DNS |
| 4 Transport | Transport | TCP, UDP |
| 3 Network | Internet | IPv4, IPv6, ICMP |
| 2 Data Link, 1 Physical | Link / Network Access | Ethernet framing, Wi-Fi, copper and radio signals |

The mapping is approximate. For example, TLS provides security services above transport in many applications.

## Encapsulation

For HTTP/1.1 over TCP on Ethernet, the sender puts HTTP data into TCP segments, wraps each segment in an IP packet, and puts each packet in an Ethernet frame for the current link. The receiver removes those headers as the data moves up the stack. A router can replace the link-layer frame at each hop while forwarding the IP packet.

## Practice

In [Lab 01](./Packet-Tracer-Labs/01-Two-PC-LAN.md), inspect a ping in Simulation Mode. Find the Ethernet and IP headers and identify ICMP. Then explain why this packet contains neither a TCP nor a UDP header.

[← Computer Networks](./README.md) · [Next: IP Addressing →](./IP-Addressing.md)
