---
title: Source and licensing policy
---

# Source and licensing policy

## Source hierarchy

1. **IETF RFC Editor / Datatracker** for protocol standards, status, errata, updates and obsoletes.
2. **Cisco official documentation** matching product, software release, model and feature.
3. **Official Wireshark documentation** for display-filter syntax and dissector behavior.
4. **Official SBC-vendor documentation** for AudioCodes, Ribbon, Oracle and other deployed systems.
5. Reputable training providers and community resources as explanatory aids—not final authority for vendor behavior.

## Cite sources in technical notes

Include the source name and direct URL, product/software version or RFC number, what the reference supports, and known caveats or updates. For version-sensitive material, record when it was checked.

## Rights and redistribution

- This repository contains original summaries, lab procedures, filter examples and source links.
- Link to RFCs at the RFC Editor; do not assume every third-party document can be republished just because it is publicly viewable.
- Link to Cisco configuration guides; do not commit full PDFs or copy substantial sections.
- Keep Cisco U course documents and paid SIPsense/SIP School/other training material out of a public repository unless the licence explicitly permits redistribution.
- Do not scrape, bulk-mirror or re-host paid courses or vendor manuals.

## Confidentiality

Never commit production PCAPs, customer configuration exports, dial plans, real caller IDs, credentials, private keys, access tokens or sensitive internal IP/host details. Use synthetic values such as `192.0.2.0/24`, `198.51.100.0/24` and `example.com`.
