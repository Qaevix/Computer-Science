# 📶 Access Point

> An access point gives Wi-Fi clients a wireless connection to a local network.

## How Clients Connect

1. The client discovers the network name, called the **SSID**.
2. It associates with an access point and completes the security exchange required by the network.
3. The access point typically bridges traffic to the wired LAN. The client can then obtain IP settings via DHCP if a server is available.

Multiple access points can advertise the same SSID. A client can roam between them as it moves. Obstacles, interference, channel overlap, and distance can all affect the wireless link.

## Example

A laptop connected to the office SSID can reach an Ethernet printer if their network settings and access rules permit it. A guest SSID can use a separate VLAN so guests cannot reach the printer.

## Practice

On your own network, compare the Wi-Fi signal near the access point and in another room. If the device joins Wi-Fi but cannot reach its gateway, check its IP address and gateway before investigating Internet access.

[← Computer Networks](./README.md) · [Next: OSI and TCP/IP →](./OSI-and-TCP-IP.md)
