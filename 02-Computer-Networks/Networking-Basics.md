# 🌐 Networking Basics

> A network lets devices exchange data and share services over wired or wireless links.

## 📖 LANs, WANs, and the Internet

A **LAN (local area network)** connects devices in a limited area, such as a home, classroom, or office. A laptop and a printer can communicate over the same LAN even when the Internet connection is down.

A **WAN (wide area network)** connects networks across larger distances, such as two company offices. The **Internet** is a global network of interconnected networks.

## 🔌 Devices and Links

| Component | What it does |
| :--- | :--- |
| Network interface | Gives an endpoint a way to connect, such as Ethernet or Wi-Fi |
| Ethernet switch | Learns which MAC addresses are reachable on its ports and forwards frames within the LAN |
| Wireless access point | Connects Wi-Fi clients to the LAN |
| Router | Forwards IP packets between networks. Hosts commonly use a router as their default gateway |

A home Wi-Fi router often combines a router, an Ethernet switch, and an access point in one box. Ethernet can run over twisted-pair copper or fiber. Wi-Fi uses radio.

## 🗺️ Network Topologies

- **Star** — Each endpoint connects to a central device, such as an Ethernet switch. One broken endpoint cable isolates that endpoint. A failed central switch can disconnect all of them.
- **Mesh** — Nodes have multiple links and may have alternate paths if one link fails.
- **Bus** — Devices share a single backbone. Older coaxial Ethernet is an example.

## 📦 How Data Moves

Suppose a laptop wants to print over Wi-Fi or load a website.

1. **Local destination.** For a printer on the same IPv4 subnet, the laptop can use ARP to learn the printer's MAC address. The access point bridges the traffic into the LAN if the printer is wired.
2. **Remote destination.** For a server outside the local subnet, the laptop sends traffic to its default gateway. The local frame is addressed to the gateway's MAC address and carries an IP packet addressed to the remote server. The router uses its routing table to choose where to forward the packet.
3. **Names.** DNS can resolve a hostname such as `example.com` to an IP address before the laptop connects.

An **IP address** helps identify the packet's destination across networks. A **MAC address** identifies a device interface for delivery on the local link. A **protocol** defines the rules devices follow when exchanging messages.

## 🔎 First Troubleshooting Checks

1. Check the cable or Wi-Fi connection.
2. Check the device's IP address, subnet mask, and default gateway.
3. Try reaching a known local device by IP address. For an Internet issue, also check the gateway and try a known reachable remote IP.
4. If a service works by IP but fails by name, check DNS. A failed `ping` alone can also mean that ICMP is blocked.

**Practice:** [Build a two-PC LAN in Packet Tracer](./Packet-Tracer-Labs/01-Two-PC-LAN.md).

[← Computer Networks](./README.md)
