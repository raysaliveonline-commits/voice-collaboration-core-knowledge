---
title: VoIP to TDM / PRI
---

# VoIP-to-TDM integration: concepts and verification

A VoIP-to-TDM lab joins packet voice signaling/media to a physical telephony interface such as E1/T1 PRI or an analog port. The exact gateway hardware, DSP resources, country signaling, provider demarcation and service type determine what is possible.

## Separate the planes

- **SIP signaling:** call setup and teardown between CUCM, CUBE/SBC and the service provider.
- **RTP media:** packet voice between IP endpoints and the gateway/SBC.
- **TDM bearer:** timeslots on the digital interface or an analog audio circuit.
- **Call control:** PRI/Q.931 and ISDN cause information or analog supervisory signaling, depending on the interface.

## Bring-up checklist

1. Confirm provider handoff, demarcation, circuit type, framing/line coding, clocking, signaling and channel plan.
2. Confirm gateway platform/module support, DSP resources and country requirements.
3. Establish physical/link and controller status before configuring call routing.
4. Validate PRI signaling and channel availability using release-specific commands.
5. Test a controlled inbound/outbound call, capture SIP, inspect gateway call legs, and confirm two-way audio.
6. Record cause codes, codec/transcoding requirements, echo, DTMF, fax and emergency-call restrictions.

Do not connect or configure a carrier circuit based only on a generic template. Obtain the provider's handoff specification and verify electrical/interface compatibility before connecting hardware.
