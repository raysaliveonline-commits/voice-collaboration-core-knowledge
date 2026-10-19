---
title: Home
description: Start here for SIP, SDP, RTP, Cisco CUBE, Wireshark and evidence-led voice troubleshooting.
---

<img class="vck-hero" src="assets/voice-collaboration-banner.svg" alt="Voice Collaboration Core Knowledge banner" />

<div class="vck-kicker">Standards first · Evidence driven · Version aware</div>

# Voice Collaboration Core Knowledge

A curated engineering reference and lab playbook for enterprise voice, collaboration, SBC interoperability and packet-level troubleshooting. Follow primary-source links for normative detail, then apply the runbooks to a lab capture or deployment scenario.

<div class="grid cards" markdown>

-   :material-book-open-variant:{ .lg .middle } **Explore the RFC catalog**

    ---

    SIP, SDP, RTP/RTCP, SRTP, DNS discovery, telephony events, presence and PSTN interworking—with links to the RFC Editor.

    [Browse standards](standards/rfc-catalog.md)

-   :material-router-network:{ .lg .middle } **Build with Cisco CUBE**

    ---

    Release-aware documentation links and call-routing, signaling and media troubleshooting context.

    [Open Cisco CUBE guide](vendors/cisco-cube-ios-xe-17-6.md)

-   :material-magnify-scan:{ .lg .middle } **Analyze packets**

    ---

    Filter SIP and SDP, follow the call timeline, then validate RTP/RTCP from actual packets.

    [Open Wireshark guide](wireshark/voice-display-filters.md)

-   :material-account-network:{ .lg .middle } **Troubleshoot SBCs**

    ---

    Compare ingress and egress legs, routing, identity, header manipulation, TLS, SDP and media.

    [Open SBC map](vendors/sbc-training-map.md)

-   :material-shield-check:{ .lg .middle } **Secure voice**

    ---

    Certificates, SIP TLS, SRTP, authentication, trust boundaries, and evidence-based security checks.

    [Open security guide](security/voice-security.md)

-   :material-console:{ .lg .middle } **Troubleshoot like TAC**

    ---

    Current state, minimal change, protocol effect, expected result, verification, failure symptoms and rollback.

    [Open TAC method](troubleshooting/tac-method.md)

</div>

## A reliable mental model

```mermaid
flowchart LR
  A[Call intent] --> B[SIP transaction / dialog]
  B --> C[SDP offer / answer]
  C --> D[Negotiated media parameters]
  D --> E[Actual RTP / SRTP packets]
  E --> F[Quality and application behavior]
  style B fill:#0f766e,color:#fff,stroke:#5eead4
  style C fill:#1d4ed8,color:#fff,stroke:#93c5fd
  style E fill:#4338ca,color:#fff,stroke:#c4b5fd
```

!!! warning "Do not infer media from signaling alone"
    A 200 OK and ACK commonly complete an INVITE exchange, but do not prove RTP is flowing. Early media can occur before that point. Read SDP and verify actual media packets in both directions.

## A disciplined troubleshooting loop

1. **Scope** — intended behavior, actual symptom, impact, topology, product/version, recent changes.
2. **Observe** — collect read-only commands, logs, captures and timestamps.
3. **Hypothesize** — rank likely causes and state what would confirm or reject each.
4. **Test** — make one controlled change only when evidence justifies it.
5. **Verify and document** — compare the result to success criteria; retain rollback and lessons learned.

## Primary-source hierarchy

1. [RFC Editor](https://www.rfc-editor.org/) / IETF Datatracker for standards and status.
2. Official Cisco docs matching exact product, software version, platform and feature.
3. [Wireshark documentation](https://www.wireshark.org/docs/) for display-filter syntax and dissector behavior.
4. Official SBC vendor manuals for the deployed vendor and release.
5. Training material and community discussions as supporting explanations—not the final authority for vendor behavior.

## Explore the library

- [Voice-related RFC catalog](standards/rfc-catalog.md)
- [Cisco CUBE IOS XE 17.6 and onward](vendors/cisco-cube-ios-xe-17-6.md)
- [Wireshark voice display filters](wireshark/voice-display-filters.md)
- [Packet-by-packet SIP call analysis](troubleshooting/sip-call-analysis.md)
- [RTP and one-way audio](troubleshooting/rtp-one-way-audio.md)
- [TAC-style change control](troubleshooting/tac-method.md)
- [VoIP-to-TDM / PRI integration](pstn/voip-to-tdm.md)
- [Voice automation](automation/voice-automation.md)
- [Glossary](glossary.md) · [Source policy](source-policy.md)
