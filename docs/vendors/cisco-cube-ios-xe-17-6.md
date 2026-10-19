---
title: Cisco CUBE IOS XE 17.6+
---

# Cisco CUBE — IOS XE 17.6 and onward

**Primary source:** [Cisco Unified Border Element Configuration Guide, IOS XE 17.6 Onwards](https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/voice/cube/ios-xe/config/ios-xe-book.html)

This page is an original navigation and troubleshooting aid, not a substitute for the guide. Match each procedure to the exact platform, release, license, topology and feature support.

## Before changing configuration

Record the exact software and platform, running configuration relevant to voice, dial-peer match, inbound/outbound call leg, codec policy, SIP transport, trust/certificate state, media flow and current symptoms. Save a rollback copy in an approved secure location.

## Call-path checklist

1. **Ingress matching:** identify the inbound dial-peer and how called/calling number, URI, source address or tenant is matched.
2. **Routing:** prove the selected outbound dial-peer, destination target, preference, translation and any tenant/context logic.
3. **Signaling:** correlate the SIP request and response sequence, headers, tags, CSeq, authentication and timers.
4. **SDP:** compare ingress and egress offer/answer: codec list, media address/port, direction, DTMF, RTP profile and security.
5. **Media:** confirm whether media is flow-through or flow-around as configured, and verify packets at both capture points.
6. **Interworking:** check cause mapping, early media, PRACK/100rel, UPDATE/re-INVITE, session timers, transfer and identity requirements.
7. **Security:** validate trust boundaries, SIP TLS peer identity, certificate chain and SRTP requirements.

## Evidence to collect

Use commands documented for the actual IOS XE release. Depending on platform and feature, useful command families may include:

- `show version` — establish software/platform baseline.
- `show running-config | section voice` — inspect voice configuration (protect sensitive values).
- `show dial-peer voice summary` — review dial-peer inventory.
- `show call active voice brief` — inspect active voice calls where supported.
- `show sip-ua status` — inspect SIP UA status where supported.
- `debug ccsip messages` and other debugs only with a scoped plan; debugs can be disruptive or expose sensitive call data.

Confirm command availability and exact behavior in the release-specific command reference. Prefer read-only outputs and embedded packet capture before enabling broad debugging.

## When a call fails

Compare the two CUBE legs rather than assuming one end-to-end SIP dialog. A B2BUA can create independent dialogs, Call-IDs, tags, SDP and transactions. For each leg, determine what arrived, what was sent, and what response came back.

## Source and version policy

The 17.6 guide is a baseline requested for this library. For newer or different trains, use the corresponding official guide and release notes. Never assume a 17.6 syntax or default is universal across all IOS XE versions.
