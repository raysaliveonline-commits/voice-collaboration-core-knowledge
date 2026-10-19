---
title: Voice security
---

# Voice security: signaling, media and identity

## Keep security planes separate

- **SIP TLS** protects signaling in transit on a particular hop; it does not automatically encrypt RTP.
- **SRTP** protects media when negotiated and configured; do not infer it from SIP TLS.
- **Certificate validation** includes chain trust, validity dates, identity/SAN matching, usage, algorithm policy and the configured trust store.
- **Identity headers** such as P-Asserted-Identity are meaningful only within the applicable trust model and provider policy.

## Troubleshooting checklist

1. Identify the exact SIP transport and endpoints for each hop.
2. Inspect certificate chain and peer identity at both sides of the TLS connection.
3. Separate TCP connectivity, TLS handshake, SIP transaction and media outcomes.
4. Verify the SDP profile and security attributes that were actually negotiated.
5. Confirm whether the media packets are RTP or SRTP and whether authorized decoding material exists.
6. Record any security exception as lab-only, with a rollback and expiration plan.

## Standards starting points

- [RFC 3711 — SRTP](https://www.rfc-editor.org/rfc/rfc3711)
- [RFC 5922 — Domain Certificates for SIP](https://www.rfc-editor.org/rfc/rfc5922)
- [RFC 8996 — Deprecating TLS 1.0 and TLS 1.1](https://www.rfc-editor.org/rfc/rfc8996)
- [RFC 8446 — TLS 1.3](https://www.rfc-editor.org/rfc/rfc8446)

Use the deployed product's official security guide to determine what is supported and how it is configured. Do not disable certificate checks or lower cryptographic standards in production to work around a mismatch.
