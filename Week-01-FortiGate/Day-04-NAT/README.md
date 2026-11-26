# Day 4 – NAT: SNAT & DNAT

## Objective

Understand and test source NAT and destination NAT in an isolated lab.

## Concepts

- SNAT: translates the source address of traffic leaving a network.
- DNAT: translates the destination address, commonly implemented using a Virtual IP (VIP) for inbound publishing.
- Port forwarding and security policy interaction.
- NAT is address translation, not a replacement for firewall policy.

## Hands-on tasks

1. Review the NAT setting on the lab's outbound firewall policy.
2. Generate outbound traffic from the lab client and inspect the translated source address where observable.
3. Create a test server on the isolated LAN.
4. If the topology supports it, create a narrowly scoped VIP/DNAT mapping for one test service.
5. Add a matching restrictive firewall policy.
6. Test from the intended source network and confirm logs.

## Verification

- [ ] SNAT behavior understood and observed.
- [ ] VIP/DNAT mapping documented, if supported by topology.
- [ ] Only the intended service is exposed.
- [ ] Firewall policy restricts source and destination.
- [ ] Test results and logs recorded.

Do not expose a lab server to the public internet. Use isolated networks and private test addresses.
