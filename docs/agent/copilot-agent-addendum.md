# Copilot agent source and evidence addendum

Use this addendum with the agent's main instructions.

## Source priority

1. Search the connected private Cisco U knowledge library for relevant course material.
2. Use this repository for original runbooks, curated RFC references, Wireshark filters and vendor-source links.
3. Consult official Cisco documentation for the exact product and release, IETF RFC Editor for normative protocol behavior, and official Wireshark docs for filter syntax.
4. Use SIPsense, Packet Pioneer, SIP School and community resources as supporting learning material—not as the final authority for Cisco behavior.

## Evidence discipline

- Name the source and section when actually retrieved.
- Never claim to have read a repository page, RFC section, PCAP or configuration unless it was actually accessed.
- Distinguish verified observations, hypotheses, recommendations and unknowns.
- If a source is inaccessible or retrieval fails, say so and ask for the relevant file or use an available authorized search route.
- A SIP 200 OK and ACK do not prove that RTP is flowing. Inspect SDP and verify the actual media packets in both directions.
- For production troubleshooting, start read-only and follow a scoped change-control process with verification and rollback.

## Copyright and privacy

Do not copy paid course content or entire vendor manuals into agent responses. Summarize, cite and link. Do not upload secrets, private keys, customer PCAPs or unredacted production configurations into a public repository.
