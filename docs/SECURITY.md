# Security Policy

## Supported Versions

We provide security fixes for the following versions:

| Version                                | Supported |
| -------------------------------------- | --------- |
| Latest released version (e.g., vX.Y.Z) | ✅        |
| Previous minor release line            | ❌        |
| All older versions                     | ❌        |

Notes:

- If you are running an unsupported version, please upgrade to a supported version before reporting (or include upgrade constraints in your report).
- For pre-1.0 projects without formal releases, we generally support the default branch and the most recent tagged release (if any).

## Reporting a Vulnerability

Please **do not** open a public GitHub Issue for security vulnerabilities.

### Preferred: Private Vulnerability Reporting (GitHub Security Advisories)

If enabled for this repository, report vulnerabilities privately via GitHub:

1. Go to the repository **Security** tab.
2. Select **Advisories**.
3. Click **Report a vulnerability** and submit the form.

Direct link (replace placeholders):
https://github.com/hamashou74/bookshelf/security/advisories/new

This channel keeps details private while maintainers investigate and prepare a fix.

## What to Include in a Report

To help us triage quickly, please include:

- A clear description of the vulnerability and its impact
- Affected area: Backend / Frontend / Infrastructure (and relevant component/path)
- Affected version(s), commit SHA, and deployment environment (prod/staging/dev)
- Step-by-step reproduction instructions or a proof of concept (PoC)
- Any relevant logs, stack traces, or screenshots (redact secrets)
- Suggested remediation, if you have one
- Whether the issue is known to be publicly disclosed or actively exploited

Please do not include:

- Credentials, private keys, access tokens, or personal data (unless strictly necessary and minimized)
- Details that materially increase exploitation risk beyond what is required to reproduce

## Our Response Process

After receiving a report, we typically follow this process:

1. **Acknowledgement**: We will acknowledge receipt of your report as soon as reasonably possible.
2. **Triage**: We will validate the report, assess severity/impact, and identify affected components/versions.
3. **Remediation**: We will develop and test a fix. For urgent cases, we may prioritize an expedited patch release.
4. **Coordinated Disclosure**: We will coordinate a disclosure timeline with the reporter. We ask that details remain confidential until a fix is available and an advisory is published.
5. **Publication**: We will publish a GitHub Security Advisory (GHSA). If eligible and appropriate, we may request a CVE.

## Coordinated Disclosure (Embargo)

We support coordinated vulnerability disclosure:

- Please allow us time to investigate and remediate before public disclosure.
- We will work with you on a mutually agreeable disclosure date, considering severity and exploitability.
- If you believe there is active exploitation, indicate this clearly in the report so we can accelerate remediation.

## Security Updates and Notifications

- Security fixes will be communicated via GitHub Security Advisories and release notes.
- Users should monitor:
  - GitHub Releases (tags)
  - GitHub Security Advisories for this repository

## Scope

This policy applies to:

- Code and configurations in this repository (backend, frontend, infrastructure as committed here)

Out of scope (examples):

- Third-party services/providers not controlled by the project
- Social engineering, phishing, or physical attacks
- Denial of Service (DoS) via traffic flooding (unless it is a vulnerability in code that materially enables DoS)

## Safe Harbor (Good-Faith Research)

We value good-faith security research. If you:

- Make a good-faith effort to avoid privacy violations, data destruction, and service disruption
- Only access data necessary to demonstrate impact (and do not exfiltrate more than needed)
- Report the issue promptly and keep details confidential until remediation

…we will treat your report as authorized and work with you to resolve the issue.

## Credit

We are happy to acknowledge researchers in the advisory/release notes unless you request otherwise.
