---
title: Wireshark voice display filters
---

# Wireshark voice display filters

**Official references:** [SIP fields](https://www.wireshark.org/docs/dfref/s/sip.html) · [RTP fields](https://www.wireshark.org/docs/dfref/r/rtp.html) · [RTCP fields](https://www.wireshark.org/docs/dfref/r/rtcp.html) · [Display-filter manual](https://www.wireshark.org/docs/man-pages/wireshark-filter.html)

These are **display filters**, applied after capture. Field names can change with dissector versions. Replace sample values with those from your capture.

## SIP signaling

| Goal | Filter | Interpretation |
|---|---|---|
| All decoded SIP | `sip` | Messages recognized by the SIP dissector. |
| INVITE | `sip.Method == "INVITE"` | Inspect Call-ID, tags, CSeq and SDP. |
| REGISTER | `sip.Method == "REGISTER"` | Registration and authentication challenge flow. |
| ACK | `sip.Method == "ACK"` | Correlate with the matching INVITE transaction/dialog. ACK alone does not prove RTP flows. |
| BYE | `sip.Method == "BYE"` | Session teardown request. |
| CANCEL | `sip.Method == "CANCEL"` | Cancellation of a pending INVITE transaction. |
| Error responses | `sip.Status-Code >= 400` | Inspect response code and preceding messages. |
| Redirects | `sip.Status-Code >= 300 && sip.Status-Code < 400` | SIP 3xx response behavior. |
| Specific Call-ID | `sip.Call-ID == "replace-with-call-id"` | A B2BUA may use different Call-IDs on its two legs. |
| SIP over common ports | `udp.port == 5060 || tcp.port == 5060` | Convention only; SIP can use other ports. |
| Common SIP TLS port | `tcp.port == 5061` | Port alone does not prove traffic is SIP. |

## TCP behavior

| Goal | Filter | Caution |
|---|---|---|
| One TCP stream | `tcp.stream eq 12` | Replace 12 with the observed stream index. |
| Retransmissions | `tcp.analysis.retransmission` | TCP analysis only; not SIP application retransmissions over UDP. |
| Lost-segment indication | `tcp.analysis.lost_segment` | Capture loss/offload can affect interpretation. |
| Out-of-order indication | `tcp.analysis.out_of_order` | Interpret the complete stream and capture point. |
| TCP reset | `tcp.flags.reset == 1` | Correlate with FIN/RST timing and both endpoints. |

## SDP and media negotiation

| Goal | Filter | How to use it |
|---|---|---|
| SDP decoded | `sdp` | Inspect the SDP protocol tree. |
| SIP with SDP | `sip && sdp` | SIP messages with a decoded SDP body. |
| Broad search for audio line | `frame contains "m=audio"` | Byte/text search only; inspect parsed SDP instead of relying on this alone. |

For every offer/answer, record session/media-level `c=` addresses, `m=audio` port and profile, `a=rtpmap`, `a=fmtp`, `a=ptime`, direction attributes, and security attributes. Dynamic RTP payload types must be mapped from SDP; do not guess their codecs from the payload number.

## RTP and RTCP

| Goal | Filter | Interpretation |
|---|---|---|
| RTP recognized by dissector | `rtp` | If missing, use **Decode As → RTP** only when packet evidence supports it. |
| RTCP | `rtcp` | RTCP reports/control messages when decoded. |
| Sequence field | `rtp.seq` | For stream analysis, use **Telephony → RTP → RTP Streams / RTP Stream Analysis**. |
| PCMU payload type 0 | `rtp.p_type == 0` | Standard static RTP/AVP mapping; confirm negotiated profile. |
| PCMA payload type 8 | `rtp.p_type == 8` | Standard static RTP/AVP mapping; confirm negotiated profile. |
| One SSRC | `rtp.ssrc == 0x12345678` | Replace with observed SSRC; it may change across legs/restarts. |
| TLS handshake | `tls.handshake` | Handshake metadata, not decrypted SIP contents. |
| TLS alerts | `tls.alert_message` | Correlate with handshake and endpoint logs. |

## DNS service discovery

- DNS packets: `dns`
- SRV query type: `dns.qry.type == 33`
- NAPTR query type: `dns.qry.type == 35`

## Capture filters are different

Display filter: `sip.Method == "INVITE"`

Capture filter (BPF): `host 192.0.2.10` or `udp port 5060 or tcp port 5060`

Do not use application display-filter syntax as a capture filter. Capture filters are applied before packets are saved.

## A repeatable call-analysis sequence

1. Identify the call direction, signaling legs and complete timeline.
2. Follow INVITE, provisional responses, any early-media SDP, final response, ACK and teardown.
3. Compare SDP offer/answer: addresses, ports, codecs, direction and security.
4. Verify actual RTP/SRTP packets in both directions; compare the capture point with negotiated endpoints.
5. Inspect sequence gaps, packet rate, timestamps, jitter/loss statistics and payload mapping.
6. If signaling is TLS or media is SRTP, state what is encrypted. Use authorized endpoint logs/decryption material; never claim to have seen hidden content.

!!! warning "Protocol truth"
    A 200 OK plus ACK commonly completes INVITE signaling, but is not a universal “RTP must start immediately” marker. Early media may begin earlier; endpoint state, negotiation, media resources, routing and policy determine actual media behavior.
