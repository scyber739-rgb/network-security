# Day 3 – Firewall Policies

## Objective

Create and verify a least-privilege firewall policy between the lab LAN and WAN.

## Policy fields to understand

- Incoming interface
- Outgoing interface
- Source and destination address objects
- Schedule and service
- Action: ACCEPT or DENY
- NAT setting
- Logging options
- Policy order

## Hands-on tasks

1. Inspect existing policies before changing anything.
2. Create a narrowly scoped LAN-to-WAN allow policy for a test client.
3. Enable appropriate traffic logging.
4. Test one permitted service, such as DNS or HTTPS, from the lab client.
5. Create a controlled deny test and verify that the traffic is blocked.
6. Review which policy matched each test.

## CLI inspection

```shell
show firewall policy
```

Use the GUI for creating/editing policies unless you are comfortable with the CLI syntax for your FortiOS version.

## Verification

- [ ] Policy uses the correct ingress and egress interfaces.
- [ ] Source, destination, and services are restricted.
- [ ] Allowed traffic succeeds.
- [ ] Denied traffic fails as expected.
- [ ] Logs show the relevant policy decision.

Never create a broad any-to-any allow rule for convenience. Keep tests inside the authorized lab.
