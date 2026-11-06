# 🔐 Network Security

> Network security controls who can connect, what they can reach, and how data is protected in transit.

| Control | What it helps protect |
| :--- | :--- |
| Segmentation | Limits how far devices can reach. A guest network can be isolated from internal systems |
| Firewalls and access control lists | Allow or deny traffic according to rules |
| TLS and SSH | Protect supported application sessions or remote administration in transit |
| WPA2 or WPA3 | Protects access and traffic on a Wi-Fi link when configured appropriately |
| Updates and strong authentication | Reduce exposure to known flaws and unauthorized administration |
| Logs | Help investigate failed connections and suspicious activity |

VLANs separate Layer 2 traffic. Once routing is enabled between VLANs, apply firewall or access rules to enforce who can reach which services.

## Practice

On a network you control or in a simulator, write a simple policy for a guest VLAN. Allow access to required services, such as the chosen DNS resolver and Internet gateway, and block access to the internal file server. Verify both sides of the policy by testing an allowed connection and a denied connection. For the denied case, check the policy logs or counters if available.

[← Computer Networks](./README.md)
