# Day 2 – Interfaces & IP Addressing

## Objective

Identify FortiGate interfaces and configure lab-side IP addressing safely.

## Concepts

- Physical and virtual interfaces
- WAN and LAN roles
- Interface IP address and subnet mask
- Administrative access (HTTPS, SSH, PING) and why it should be restricted
- Interface status and link state

## Read-only discovery

```shell
get system interface
show system interface
```

## Hands-on tasks

1. Identify the WAN and LAN interface names from your own VM/device.
2. Record their current status and addressing.
3. Assign a private lab subnet to the LAN interface using the GUI or version-appropriate CLI.
4. Enable only the management protocols needed for the isolated lab.
5. Configure the client VM with an address in the LAN subnet.
6. Test reachability to the FortiGate LAN interface.

Do not copy interface names or IPs from an example without checking your own topology.

## Verification

- [ ] Correct interfaces identified.
- [ ] LAN interface has the intended lab IP/prefix.
- [ ] Client is in the same subnet.
- [ ] Client can reach the LAN interface.
- [ ] Management access is limited to the lab.

## Evidence

Capture interface status and client addressing. Redact public IPs, MAC addresses, serial numbers, and other sensitive details.
