# Day 7 – FortiGate End-to-End Mini Project

## Scenario

A small organization needs controlled internet access for a LAN and a protected internal test server. Build and validate the design inside an isolated virtual lab.

## Required deliverables

1. Network topology diagram with interface names and private lab subnets.
2. FortiGate system/version and interface inventory.
3. LAN-to-WAN firewall policy using least privilege.
4. SNAT configuration for outbound client traffic.
5. Static route documentation where required by the topology.
6. Optional VIP/DNAT for one internal test service, restricted to a lab source.
7. Allowed and denied traffic test cases.
8. Traffic logs and troubleshooting evidence.
9. Backup/snapshot note and rollback steps.

## Test matrix

| Test | Expected result | Actual result |
|---|---|---|
| Client reaches FortiGate LAN interface | Success | Fill after test |
| Authorized outbound service | Allowed | Fill after test |
| Unapproved service | Blocked | Fill after test |
| Route to test destination | Correct route selected | Fill after test |
| Restricted inbound test (if configured) | Only permitted source/service allowed | Fill after test |

## Submission structure

```text
Week-01-FortiGate/
├── README.md
├── Day-01-Lab-Setup/
├── Day-02-Interfaces-IP/
├── Day-03-Firewall-Policies/
├── Day-04-NAT/
├── Day-05-Routing/
├── Day-06-Logs-Troubleshooting/
└── Day-07-Mini-Project/
```

Each day folder should contain its README, sanitized screenshots, and notes. Include actual commands and observed outputs; do not claim a test passed unless you performed it.

## Final review

- [ ] Topology is clear.
- [ ] Policies follow least privilege.
- [ ] NAT and routing are explained.
- [ ] Allowed and blocked tests have evidence.
- [ ] Logs support the findings.
- [ ] Sensitive information is redacted.
- [ ] Repository documentation is complete.
