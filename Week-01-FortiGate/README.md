# Week 1 – FortiGate Firewall Hands-on

## Goal

Build a safe, isolated FortiGate lab and gain practical experience with FortiOS administration, interfaces, firewall policies, NAT, routing, and traffic troubleshooting.

## Suggested lab topology

```text
Internet / NAT Network
        |
      [WAN]
   FortiGate VM
      [LAN]
        |
   Lab switch / virtual network
      |             |
   Ubuntu VM      Kali VM
 (test server)  (test client)
```

Use an isolated virtual network for the LAN side. Do not bridge the lab into a production network unless you intentionally need to and understand the risks.

## 7-day plan

| Day | Hands-on topic | Evidence |
|---|---|---|
| 1 | Lab preparation, FortiGate VM deployment, first GUI/CLI access | Topology and system status |
| 2 | WAN/LAN interfaces, IP addressing, administrative access | Interface status and addressing |
| 3 | Firewall policies, policy order, allow/deny testing | Policy screenshots and test results |
| 4 | Source NAT and Destination NAT / Virtual IP concepts | NAT configuration and verification |
| 5 | Static routing and route-table checks | Routing table and connectivity tests |
| 6 | Traffic logs, packet sniffer, debug flow and troubleshooting | Sanitized logs and troubleshooting notes |
| 7 | End-to-end mini project and documentation | Complete topology, rules, tests and findings |

## Important prerequisites

- A supported FortiGate VM image or physical FortiGate device with legitimate access.
- A hypervisor such as VirtualBox, VMware, or a network emulator that supports the selected FortiGate image.
- One client VM (Kali or another Linux VM) and optionally one server VM (Ubuntu).
- Console access and a way to take VM snapshots before major changes.

FortiGate VM availability, evaluation terms, and supported hypervisors depend on Fortinet's current licensing and product releases. Use an image and license you are authorized to use; do not download cracked images or bypass licensing.

## Daily workflow

1. Read the objective and topology.
2. Configure one feature at a time.
3. Verify the expected traffic path.
4. Test both permitted and denied traffic.
5. Save sanitized screenshots and command output.
6. Write what worked, what failed, and why.

## Completion criteria

Do not mark a day complete merely because a setting was entered. Verify the resulting interface state, routing, policy match, NAT behavior, or logs as appropriate.
