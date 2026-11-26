# Day 1 – Network Fundamentals & Diagnostics

## Objective

Explore basic host connectivity, route discovery, IPv4 routing information, ARP address resolution, and packet inspection using Windows Command Prompt and Wireshark.

## Tools

- Windows Command Prompt
- Wireshark
- Npcap

## Practical exercises

### 1. Test connectivity to the default gateway

```cmd
ping -n 10 <DEFAULT_GATEWAY_IP>
```

**Observed result from this lab**
- Packet loss: **0%**
- Average response time: **1 ms**

**What it means:** All ten probes received replies in this test, with a measured average round-trip time of 1 ms to the local default gateway. This is evidence of successful local gateway connectivity during the test, not proof that the entire network or internet path is problem-free.

### 2. Trace the route to a destination

```cmd
tracert 8.8.8.8
```

**Wireshark display filter**

```text
icmp
```

**Observed:** ICMP Echo Request packets and ICMP Time Exceeded responses were seen.

**What it means:** Traceroute discovers hops by sending probes with increasing TTL values. A router may return ICMP Time Exceeded when a probe's TTL reaches zero. The TTL in the outer IP header of the Time Exceeded response belongs to the response packet; it should not be mistaken for the original probe's TTL.

### 3. Inspect ICMP Echo Request and Echo Reply

Wireshark display filter:

```text
icmp.type == 8 || icmp.type == 0
```

- Type 8: Echo Request
- Type 0: Echo Reply

**Purpose:** Compare requests sent by the PC with replies received from the destination.

### 4. Inspect the IPv4 routing table

```cmd
route print
```

Review the IPv4 Route Table, especially the default route:

- Network destination: `0.0.0.0`
- Netmask: `0.0.0.0`
- Gateway: next hop used for destinations without a more specific route
- Interface: local interface used
- Metric: route preference value used in route selection

### 5. Inspect the ARP cache

```cmd
arp -a
```

Review the Internet Address, Physical Address, and Type columns.

**What it means:** ARP maps an IPv4 address on the local network to a link-layer MAC address. The ARP cache stores recently learned mappings.

### 6. Capture ARP traffic in Wireshark

Start a capture on the active network interface and use:

```text
arp
```

To trigger fresh resolution for the gateway, run Command Prompt as Administrator:

```cmd
arp -d <DEFAULT_GATEWAY_IP>
ping -n 2 <DEFAULT_GATEWAY_IP>
```

Look for:
- **ARP Request:** A device broadcasts a request asking which MAC address owns the target IPv4 address.
- **ARP Reply:** The device owning that IPv4 address responds with its MAC address.

If no new ARP exchange appears, the capture may have started too late, the wrong interface may be selected, or the entry may not have been cleared. Do not conclude that ARP is broken from an empty capture alone.

## Results summary

| Exercise | Result |
|---|---|
| Gateway ping | Successful |
| Packet loss | 0% |
| Average gateway response time | 1 ms |
| Traceroute | ICMP Time Exceeded responses observed |
| ICMP inspection | Echo Request / Reply inspected |
| Routing table | Inspected |
| ARP cache | Inspected |
| ARP packet capture | Performed; screenshot evidence saved locally |

## Evidence

Place sanitized screenshots in the `Screenshots/` folder:

- `ping-test.png`
- `tracert-analysis.png`
- `icmp-capture.png`
- `routing-table.png`
- `arp-table.png`
- `arp-capture.png`

Only upload screenshots after removing or masking public IPs, MAC addresses, Wi-Fi SSIDs, usernames, and any other sensitive network or personal details.

## Key learnings

- Used `ping` to test local gateway reachability and measure round-trip time.
- Used `tracert` to observe hop discovery and ICMP Time Exceeded responses.
- Inspected ICMP packets in Wireshark.
- Reviewed the Windows IPv4 routing table with `route print`.
- Inspected IP-to-MAC mappings with `arp -a`.
- Captured ARP traffic and identified the purpose of ARP Request and Reply messages.

## Conclusion

The Day 1 exercises provided hands-on practice with basic network diagnostics and packet analysis on a Windows host. The recorded gateway ping result was 0% packet loss with a 1 ms average response time during the test.

**Next:** Day 2 – Subnetting Fundamentals.
