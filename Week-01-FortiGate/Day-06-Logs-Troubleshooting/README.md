# Day 6 – Logs & Traffic Troubleshooting

## Objective

Use FortiGate logs and diagnostic tools to understand why lab traffic is allowed or blocked.

## Concepts

- Forward traffic logs
- Policy ID and action
- Source/destination/service fields
- Packet sniffer
- Debug flow
- Session table and route lookup

## Useful diagnostic commands

```shell
diagnose sniffer packet any 'host <LAB_CLIENT_IP>' 4 0 l
diagnose debug flow filter clear
diagnose debug flow filter addr <LAB_CLIENT_IP>
diagnose debug flow show function-name enable
diagnose debug enable
diagnose debug flow trace start 20
```

After collecting the trace, stop debugging:

```shell
diagnose debug disable
diagnose debug reset
```

Use diagnostic commands carefully and only in the lab. Syntax and available options can vary by FortiOS version. Avoid leaving debug enabled.

## Hands-on tasks

1. Generate one allowed test flow and locate its traffic log.
2. Generate one denied test flow and inspect the deny reason.
3. Capture a short packet trace for the lab client.
4. If needed, run a short debug-flow trace.
5. Check interface status, route selection, policy match, and NAT in that order.

## Verification

- [ ] Allowed flow identified in logs.
- [ ] Denied flow identified in logs.
- [ ] Packet capture saved or summarized.
- [ ] Debug output collected safely and then disabled.
- [ ] Root cause and fix documented.
