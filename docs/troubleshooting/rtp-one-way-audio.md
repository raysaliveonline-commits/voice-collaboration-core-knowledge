---
title: RTP and one-way audio troubleshooting
---

# RTP and one-way audio troubleshooting

## Start with evidence, not assumptions

One-way audio can result from routing, NAT, firewall policy, incorrect SDP, asymmetric media, codec or security mismatch, endpoint behavior, media-resource selection, or a capture taken at the wrong location. Do not assume the cause before testing.

## Phase 1 — establish negotiated media

Inspect the applicable SDP offer/answer and any early-media exchanges. Record each leg's media address, port, codec/payload mapping, direction attributes and RTP/SRTP profile. A B2BUA may use different SDP on each leg.

## Phase 2 — prove packet direction

Capture near both media endpoints. Filter on the observed media addresses and ports, then verify actual RTP packets in both directions. If only one side sees packets, compare routing, NAT, firewall state and capture points.

## Phase 3 — inspect stream quality

Use **Telephony → RTP → RTP Streams / RTP Stream Analysis**. Compare packet counts, sequence gaps, timestamps, jitter, loss and payload type. Confirm the payload type maps to the codec negotiated in SDP.

## Phase 4 — inspect media resources and policy

If CUCM or a gateway inserts MTP, transcoder or conference resources, inspect the allocation and actual media legs. A resource can change media addresses/ports and codec paths. Verify the observed call rather than inferring from a checkbox.

## Phase 5 — change only with evidence

Propose one scoped change, explain protocol effect, define expected output, verify after the change, and document rollback. Avoid broad firewall openings, disabling security or restarting services as first-line actions.

## Report format

- Verified facts:
- Hypotheses ranked:
- Next read-only check:
- Expected result:
- What would falsify the hypothesis:
- Change/rollback (only if justified):
