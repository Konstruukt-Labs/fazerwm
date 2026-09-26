# Security Policy

## Reporting a vulnerability

Please report vulnerabilities through GitHub's **private vulnerability
reporting** on this repo (Security tab → "Report a vulnerability"), or email
the address on [fazerwm.app](https://fazerwm.app) if it's listed there.

Do **not** open a public issue for anything security-sensitive, including:

- License/trial bypasses (local or server-side)
- Update-feed weaknesses (appcast signature, key handling)
- Privilege or permission escalation (Accessibility, Screen Recording abuse)

Include the FazerWM version, macOS version, and a description or proof of
concept. You'll get an acknowledgement within a few days; a fix timeline
follows once the report is triaged.

## Scope

The shipped app binary, the Sparkle update feed on this repo, and the
licensing flow between the app and FazerWM's license server. Reports about
third-party dependencies should go upstream, with a heads-up here if they
affect shipped builds.
