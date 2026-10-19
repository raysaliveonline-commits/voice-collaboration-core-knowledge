---
title: Packet-by-packet SIP analysis
---

# Packet-by-packet SIP analysis

## 1. Build the timeline first

Filter with `sip`, then identify the initial INVITE, provisional responses, final response, ACK and any BYE/CANCEL. Correlate by Call-ID, tags, CSeq, Via branch and timestamps. If an SBC is present, track ingress and egress legs separately.

## 2. Read each transaction in context

For each message record: source/destination, method or status, Call-ID, From/To tags, CSeq, Via branch, Request-URI, Contact, Route/Record-Route, authentication and relevant reason headers. A single packet rarely tells the whole story.

## 3. Inspect SDP as a negotiated contract

For each offer and answer compare:

- Session/media `c=` address and `m=audio` port.
- RTP profile and payload types.
- `a=rtpmap`, `a=fmtp`, packetization time and direction attributes.
- DTMF payload mapping and SRTP/security attributes.
- Whether early media changes the timing or media parameters.

## 4. Verify media independently

Use the negotiated address/port to find media candidates, then verify actual RTP in both directions. If Wireshark has not decoded the media, use Decode As only when the traffic and SDP support it. Run RTP Stream Analysis and note capture placement, packet rate, sequence gaps, jitter and loss.

## 5. State the limits of the evidence

A 200 OK plus ACK commonly completes an INVITE exchange, but it does not prove RTP is flowing. RTP may start earlier as early media. TLS hides SIP contents unless authorized decryption is available; SRTP hides media content without authorized keys.

**Related:** [Wireshark voice filters](../wireshark/voice-display-filters.md) · [RFC catalog](../standards/rfc-catalog.md) · [TAC method](tac-method.md)
