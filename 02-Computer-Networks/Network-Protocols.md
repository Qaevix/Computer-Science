# 📬 Network Protocols

> Protocols define the messages and rules that devices use to communicate.

| Protocol | Purpose | Common transport or port |
| :--- | :--- | :--- |
| TCP | Reliable, ordered byte stream | Transport protocol |
| UDP | Datagrams with no built-in retransmission or ordering | Transport protocol |
| DNS | Looks up records, including addresses for hostnames | UDP or TCP 53 for classic DNS |
| DHCPv4 | Leases IPv4 addresses and provides network settings | UDP 67 server, UDP 68 client |
| HTTP | Exchanges web requests and responses | Commonly TCP 80 for plain HTTP |
| HTTPS | Protects HTTP traffic with encryption and server authentication | Commonly TCP 443, or UDP 443 with HTTP/3 over QUIC |
| ICMP | Carries IP control and diagnostic messages | Runs directly over IP, with no port number |

## Example

After a device obtains its network settings, a browser can resolve a website hostname using DNS. It then connects to an address returned by DNS, negotiates security for HTTPS, and sends an HTTP request. Which transport it uses depends on the HTTP version negotiated.

## Practice

On Windows, run `nslookup example.com` to check name resolution and `curl.exe -I https://example.com` to request HTTP response headers. If the lookup succeeds but the web request fails, inspect the connection or TLS error before changing DNS settings.

[← Computer Networks](./README.md) · [Next: VLAN →](./VLAN.md)
