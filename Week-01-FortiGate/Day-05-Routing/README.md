# Day 5 – Static Routing

## Objective

Understand how FortiGate selects routes and verify a simple static route in the lab.

## Concepts

- Connected and static routes
- Default route
- Next-hop gateway
- Route lookup and route preference
- Routing versus firewall policy

## CLI discovery

```shell
get router info routing-table all
```

## Hands-on tasks

1. Inspect the current routing table.
2. Identify connected networks and the default route.
3. Draw the path from the LAN client to the test destination.
4. Add a static route only if your lab topology requires one and you know the correct next hop.
5. Test reachability and inspect the route selected.
6. Check firewall policies separately; a valid route does not automatically permit traffic.

## Verification

- [ ] Routing table understood.
- [ ] Next hop and outgoing interface identified.
- [ ] Any required static route verified.
- [ ] Connectivity tested.
- [ ] Routing and policy behavior distinguished.
