# Contributing

Thank you for helping improve Voice Collaboration Core Knowledge.

## Contribution rules

- Prefer official RFC Editor, Cisco, Wireshark and SBC-vendor references.
- State product, platform, release and feature scope when behavior is version-sensitive.
- Distinguish normative protocol behavior from vendor implementation details.
- Never claim a capture, command or configuration was tested unless it was.
- Use synthetic addresses, domains and telephone numbers.
- Do not submit credentials, customer PCAPs, private keys, tokens, private configurations or paid course content.
- Add a source link and explain what it supports.
- For filter changes, check the current Wireshark display-filter reference.

## Run locally

Install Python and the dependencies from requirements.txt, then run:

    python -m pip install -r requirements.txt
    mkdocs serve

Build with:

    mkdocs build --strict

## Suggested issue report

Include topic, product/version, expected behavior, observed behavior, minimal redacted evidence, primary sources consulted, and what remains uncertain.
