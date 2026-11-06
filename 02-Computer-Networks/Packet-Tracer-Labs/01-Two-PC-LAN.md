# 🧪 Lab 01 · Build a Two-PC LAN

## Objective

Connect two PCs through a switch, verify that they can reach each other, and diagnose an IPv4 subnet mismatch.

## Topology

```text
PC0 FastEthernet0 ── Fa0/1 [2960 Switch] Fa0/2 ── FastEthernet0 PC1
```

## Addressing Table

| Device | IPv4 address | Subnet mask | Default gateway |
| :--- | :--- | :--- | :--- |
| PC0 | `192.168.10.10` | `255.255.255.0` | Leave blank |
| PC1 | `192.168.10.20` | `255.255.255.0` | Leave blank |

Both PCs are in `192.168.10.0/24`. They can communicate on the same LAN without a router.

## Configuration

1. Add two PCs and one 2960 switch in Cisco Packet Tracer.
2. Select **Copper Straight-Through** and connect each PC to its switch port as shown above. Wait for the switch links to turn green.
3. On each PC, open **Desktop → IP Configuration** and enter its address and mask. Leave the gateway blank.

## Verification

On PC0, open **Desktop → Command Prompt** and run:

```text
ping 192.168.10.20
```

Expect replies from PC1. If the first attempt times out, retry after the links are up and ARP has resolved the destination. Then try the reverse direction from PC1 with `ping 192.168.10.10`.

## Troubleshooting Exercise

Change PC1 to `192.168.20.20` and keep the same mask. From PC0, run `ping 192.168.20.20`. Expect it to fail because the destination is in another subnet and PC0 has no default gateway. Restore `192.168.10.20` and verify that the original ping works again.

If the ping still fails, check that both cables are connected to the expected ports, both links are up, and each PC has the correct address and mask.

Optional: In **Simulation Mode**, filter for **ARP** and **ICMP** and step through a ping. ARP can be absent if the PCs already cached each other's MAC addresses.

[← Computer Networks](../README.md)
