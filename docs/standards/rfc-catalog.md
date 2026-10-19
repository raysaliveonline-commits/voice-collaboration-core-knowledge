---
title: Voice-related RFC catalog
---

# Voice-related RFC catalog

This is a curated working index, not a claim that every RFC relevant to every voice deployment is listed. Use the [RFC Editor](https://www.rfc-editor.org/) to validate the exact title, status, errata, updates and obsoletes relationship. Older RFCs may be useful for historical context but should not automatically be treated as current guidance.

## Core SIP and call control

| RFC | Topic | Why it matters |
|---|---|---|
| [3261](https://www.rfc-editor.org/rfc/rfc3261) | SIP | Core methods, transactions, dialogs, routing and responses. |
| [3262](https://www.rfc-editor.org/rfc/rfc3262) | Reliability of provisional responses | 100rel and PRACK. |
| [3263](https://www.rfc-editor.org/rfc/rfc3263) | Locating SIP servers | DNS NAPTR/SRV/A discovery. |
| [3264](https://www.rfc-editor.org/rfc/rfc3264) | Offer/answer model | SDP negotiation semantics. |
| [3311](https://www.rfc-editor.org/rfc/rfc3311) | UPDATE method | Session modification before final response. |
| [3325](https://www.rfc-editor.org/rfc/rfc3325) | Asserted identity | Trusted-domain identity handling. |
| [3326](https://www.rfc-editor.org/rfc/rfc3326) | Reason header | Cause/reason signaling. |
| [3515](https://www.rfc-editor.org/rfc/rfc3515) | REFER method | Transfer and referral signaling. |
| [4028](https://www.rfc-editor.org/rfc/rfc4028) | Session timers | Session refresh and expiration. |
| [4488](https://www.rfc-editor.org/rfc/rfc4488) | Suppression of REFER implicit subscription | Transfer interoperability details. |
| [4566](https://www.rfc-editor.org/rfc/rfc4566) | SDP | Original SDP specification; see RFC 8866 for the revised specification. |
| [6026](https://www.rfc-editor.org/rfc/rfc6026) | SIP INVITE transaction fixes | Corrected INVITE transaction behavior. |
| [6141](https://www.rfc-editor.org/rfc/rfc6141) | Re-INVITE behavior | Dialog/session modification edge cases. |
| [6665](https://www.rfc-editor.org/rfc/rfc6665) | Event framework | SIP event subscriptions and notifications. |
| [7044](https://www.rfc-editor.org/rfc/rfc7044) | History-Info | Request history across retargeting. |
| [8224](https://www.rfc-editor.org/rfc/rfc8224) | Authenticated Identity Management | SIP identity and PASSporT context. |

## SDP, RTP and real-time media

| RFC | Topic | Why it matters |
|---|---|---|
| [3550](https://www.rfc-editor.org/rfc/rfc3550) | RTP/RTCP | Real-time media transport and control reports. |
| [3551](https://www.rfc-editor.org/rfc/rfc3551) | RTP audio/video profile | Static payload types and RTP/AVP conventions. |
| [3711](https://www.rfc-editor.org/rfc/rfc3711) | SRTP | Confidentiality, authentication and replay protection for RTP. |
| [4733](https://www.rfc-editor.org/rfc/rfc4733) | DTMF / telephony events | RTP telephone-event payloads; commonly called RFC 2833 historically. |
| [5761](https://www.rfc-editor.org/rfc/rfc5761) | RTP/RTCP multiplexing | RTP and RTCP on a shared port. |
| [5764](https://www.rfc-editor.org/rfc/rfc5764) | DTLS-SRTP | Key establishment for WebRTC-style media. |
| [6189](https://www.rfc-editor.org/rfc/rfc6189) | ZRTP | Media-path key agreement mechanism. |
| [6464](https://www.rfc-editor.org/rfc/rfc6464) | Client-to-mixer audio level | RTP header extension for audio levels. |
| [7587](https://www.rfc-editor.org/rfc/rfc7587) | Opus RTP payload | Opus payload format. |
| [8866](https://www.rfc-editor.org/rfc/rfc8866) | SDP | Revised Session Description Protocol specification. |
| [8872](https://www.rfc-editor.org/rfc/rfc8872) | RTP media congestion control feedback | RTP feedback framework. |

## DNS, numbering and PSTN interworking

| RFC | Topic | Why it matters |
|---|---|---|
| [2782](https://www.rfc-editor.org/rfc/rfc2782) | DNS SRV | Service discovery record. |
| [3403](https://www.rfc-editor.org/rfc/rfc3403) | DDDS / NAPTR | Naming and service discovery framework. |
| [3966](https://www.rfc-editor.org/rfc/rfc3966) | tel URI | Telephone-number URI structure. |
| [3372](https://www.rfc-editor.org/rfc/rfc3372) | SIP-T architecture | SIP/PSTN interworking context. |
| [3398](https://www.rfc-editor.org/rfc/rfc3398) | ISUP-to-SIP mapping | Mapping PSTN signaling to SIP. |
| [3666](https://www.rfc-editor.org/rfc/rfc3666) | SIP PSTN call flows | Example call flows for gateway scenarios. |

## Security and transport

| RFC | Topic | Why it matters |
|---|---|---|
| [3265](https://www.rfc-editor.org/rfc/rfc3265) | SIP event notification | Historical event framework; consult RFC 6665 for revised behavior. |
| [3329](https://www.rfc-editor.org/rfc/rfc3329) | Security mechanism agreement | Negotiating supported security mechanisms. |
| [5630](https://www.rfc-editor.org/rfc/rfc5630) | SIPS URI scheme | Secure SIP URI handling. |
| [5922](https://www.rfc-editor.org/rfc/rfc5922) | Domain certificates for SIP | Certificate identity for SIP domains. |
| [8445](https://www.rfc-editor.org/rfc/rfc8445) | ICE | NAT traversal connectivity checks. |
| [8996](https://www.rfc-editor.org/rfc/rfc8996) | Deprecating TLS 1.0/1.1 | Modern TLS baseline considerations. |

## Presence and messaging

| RFC | Topic | Why it matters |
|---|---|---|
| [3856](https://www.rfc-editor.org/rfc/rfc3856) | Presence event package | SIP presence subscriptions. |
| [3863](https://www.rfc-editor.org/rfc/rfc3863) | PIDF | XML presence data format. |
| [3903](https://www.rfc-editor.org/rfc/rfc3903) | PUBLISH method | Publishing event state. |
| [4662](https://www.rfc-editor.org/rfc/rfc4662) | Resource lists | List-based event subscriptions. |

## How to use this index

1. Read the RFC Editor page and check updates/obsoletes before relying on an older RFC.
2. Separate normative protocol behavior from a vendor's specific implementation.
3. For a packet question, cite the exact RFC section when possible and verify the actual trace.
4. Use the companion [Wireshark voice filter guide](../wireshark/voice-display-filters.md) and [SIP analysis method](../troubleshooting/sip-call-analysis.md).

The catalog is intentionally curated and should be expanded through review, not by blindly treating keyword matches as authoritative.
