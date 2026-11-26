# Day 1 – FortiGate Lab Setup & First Access

## Objective

Prepare an isolated lab, boot an authorized FortiGate VM/appliance, and identify the FortiOS version and management access method.

## Before starting

- Confirm that you have a FortiGate VM image/device and legitimate evaluation or production entitlement.
- Confirm the hypervisor and FortiOS version are supported by the image.
- Create a VM snapshot before configuration.
- Keep the lab network isolated from your normal LAN.

## Suggested topology

```text
Virtual NAT / upstream
        |
      FortiGate
        |
   Isolated LAN network
      /          \
  Kali client  Ubuntu server
```

## Tasks

1. Create or select an isolated virtual network for the lab LAN.
2. Attach the FortiGate WAN and LAN interfaces to the intended virtual networks.
3. Boot the firewall and open its console.
4. Complete only the initial setup steps required by your authorized image.
5. Log in to the FortiOS GUI if management access is available.
6. Record the FortiOS version and interface names shown by your device.
7. Take a snapshot before moving to interface or policy changes.

## CLI discovery commands

Run these read-only commands in the FortiGate CLI:

```shell
get system status
get system interface
```

Depending on FortiOS version and permissions, output may differ.

## Verification checklist

- [ ] FortiGate boots successfully.
- [ ] FortiOS version recorded.
- [ ] WAN and LAN virtual adapters identified.
- [ ] GUI/console access confirmed.
- [ ] Lab is isolated.
- [ ] Snapshot created.

## Evidence

Save sanitized screenshots in this day's `Screenshots/` folder. Hide serial numbers, license details, passwords, public IPs, and sensitive identifiers.

## Troubleshooting notes

If GUI access fails, verify the management interface IP, virtual NIC attachment, host-only/isolated network settings, and whether administrative access is enabled on that interface. Do not expose management access to the public internet.

## Result

Fill in the actual FortiOS version, hypervisor, interface mapping, and verified outcome after performing the lab. Do not invent values.
