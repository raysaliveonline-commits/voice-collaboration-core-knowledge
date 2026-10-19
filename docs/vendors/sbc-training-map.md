---
title: SBC vendor documentation and SIP training map
---

# SBC vendor documentation and SIP training map

Use official vendor manuals for product behavior. Training resources help build intuition but are not normative sources. This page links to legitimate resources; it does not reproduce paid course content.

| Ecosystem | Official / source portal | Use it for |
|---|---|---|
| Cisco CUBE | [IOS XE 17.6 Onwards Configuration Guide](https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/voice/cube/ios-xe/config/ios-xe-book.html) | Dial peers, SIP, media, interworking and troubleshooting. |
| AudioCodes | [Technical Documents Library](https://www.audiocodes.com/library/technical-documents) | SBC/gateway releases, TLS/certificates, voice quality and interoperability. |
| Oracle Communications SBC | [SBC documentation](https://docs.oracle.com/en/industries/communications/session-border-controller/index.html) | Realms, SIP interfaces, session agents, header manipulation, media and diagnostics. |
| Ribbon | [Ribbon Academy](https://academy.ribboncommunications.com/) | SBC learning paths and support courses; enrollment may be required. |
| The SIP School | [SIP training and certification](https://www.thesipschool.com/) | SIP fundamentals, trunking, NAT/firewalls/SBCs and media security. Paid content remains under its own terms. |
| SIPsense | [SIPsense](https://www.sipsense.com/) · [Enterprise](https://www.sipsense.com/enterprise) | Interactive SIP exercises and enterprise training analytics. |
| Packet Pioneer / Chris Greer | [Packet Pioneer](https://packetpioneer.com/) | Practical Wireshark and packet-analysis education. |
| SIPp | [SIPp documentation](https://sipp.readthedocs.io/en/latest/) | SIP traffic generation and reproducible call-flow scenarios in authorized labs. |

## Cross-vendor SBC troubleshooting matrix

1. **SIP sequence:** method, status, Call-ID, tags, CSeq, Via, Route/Record-Route, Contact, Reason and identity headers.
2. **Normalization:** what URIs/headers are changed, removed or regenerated across the two legs?
3. **Authentication and trust:** digest challenges, IP trust, TLS peer identity, certificate chain and policy.
4. **DNS and routing:** destination resolution, SRV/NAPTR where used, route selection, failover and timers.
5. **SDP and media:** addresses/ports, codec list, direction, DTMF, early media, SRTP profile and media anchoring.
6. **Interworking:** REFER/transfer, 18x/PRACK/100rel, session timers, UPDATE/re-INVITE, identity and cause-code mapping.
7. **Evidence:** simultaneous captures on both sides, aligned timestamps, SBC logs and actual RTP flow.

Do not transfer one vendor's syntax or default to another vendor. Build a behavior matrix and confirm the equivalent feature in the target release's official manual.

## Terminology note

The open-source SIP traffic generator is **SIPp**. SIPsense is a separate interactive SIP learning resource. If another tool is intended by a similar name, verify the exact URL before adding it to the source list.
