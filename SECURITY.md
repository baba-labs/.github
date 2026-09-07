# Security Policy

BaBa Labs builds software that runs in other organisations' production environments. We
treat vulnerability reports as a priority, and we would rather hear about a problem from
you than from a client.

## Reporting a vulnerability

**Do not open a public issue, pull request or discussion for a security problem.**

Report privately by either route:

- **GitHub private vulnerability reporting** — the **Report a vulnerability** button on
  the Security tab of the affected repository. Preferred, because it keeps the report,
  the discussion and the eventual advisory in one place.
- **Email** — <security@baba-labs.com>. If you would rather encrypt, say so in a first
  message with no detail and we will send a key.

Please include, as far as you can:

- The affected product, component and version or commit
- What an attacker can achieve — the impact, not only the defect
- Steps to reproduce, or a proof of concept
- Any configuration needed to trigger it
- Whether the issue is already public, and any disclosure deadline you intend to apply

You do not need a complete write-up. A short report we can reproduce is worth more than
a polished one we cannot.

## What happens next

We are a small team and these targets are set to be ones we can actually meet rather
than ones that sound impressive.

| Stage | Target |
|---|---|
| Acknowledge receipt | 3 business days |
| Initial assessment and severity | 10 business days |
| Regular updates until resolution | At least every 10 business days |

Remediation targets once a report is confirmed, measured from assessment:

| Severity | Target |
|---|---|
| Critical | 14 days |
| High | 30 days |
| Medium | 90 days |
| Low | Next scheduled release |

If we are going to miss a target we will tell you before it passes, with a reason.

## Disclosure

We work to coordinated disclosure. We will agree a timeline with you, credit you in the
advisory unless you prefer otherwise, and publish a GitHub Security Advisory for the
affected repository once a fix is available to customers.

If you believe a problem is being handled too slowly, say so — we would rather be pushed
than have you disclose out of frustration.

## Safe harbour

If you make a good-faith effort to comply with this policy while researching a
vulnerability, we will not pursue or support legal action against you, and we will
treat your research as authorised.

Good faith means:

- Only interacting with systems and accounts you own or have explicit permission to test
- Not accessing, modifying, or retaining data belonging to anyone else — if you encounter
  personal data, stop and tell us
- Not degrading, disrupting or denying service to others
- Giving us reasonable time to remediate before public disclosure

This is not permission to test a client's systems. Where our software is deployed into a
client's own environment, testing an instance you do not own is testing their system, not
ours, and this safe harbour does not extend to it.

## Scope

**In scope:** source code, container images, deployment templates and released artefacts
in repositories owned by baba-labs, and services BaBa Labs operates.

**Out of scope:**

- Third-party services we consume — report those to the vendor
- Findings from automated scanners with no demonstrated exploitability
- Social engineering of staff or customers, physical attacks, and denial of service
- Missing hardening headers or best-practice deviations with no demonstrated impact
- Vulnerabilities requiring a compromised device or a privileged local attacker, unless
  the result exceeds what that access already grants

## Supported versions

Security fixes are provided for the current major version of anything we release. Where
software is deployed into a client's own environment, a fix is a release they must deploy;
we notify affected clients directly and state the severity and the deployment urgency.
