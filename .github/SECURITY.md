# Security Policy for MomentumTracker-Web-Performance-Monitoring-HTML

As the Apex Technical Authority, this project adheres to a **Zero-Defect Security Posture**. We treat all code, especially client-facing visualization layers, as critical infrastructure. This policy outlines how vulnerabilities are reported, triaged, and remediated.

## Supported Versions

This project follows a **rolling standard**. We only actively support the latest version of the core technology stack (HTML5, modern JavaScript/DOM APIs). Patches for critical vulnerabilities (CVSS >= 9.0) will be applied immediately to the primary branch and backported to any release tags within the last 90 days, provided the existing structure allows for mitigation without a complete architectural overhaul.

## Reporting a Vulnerability

We deeply appreciate responsible disclosure. Please report all security concerns directly to the maintainer rather than opening a public issue.

**Reporting Channel:**

1.  **Preferred Method (Encrypted):** Email security reports to `security@chirag127.dev` (or the primary contact listed in `CONTRIBUTING.md`).
2.  **Alternative (Public but Private):** Open a temporary, private issue labeled `security-report` via the GitHub Security Tab. **Do not include exploit details in the initial description.**

### Disclosure Timeline Expectation

Upon receiving a report, we commit to the following timeline:

| Step | Target Timeframe (From Report Receipt) |
| :--- | :--- |
| Acknowledge Receipt | 24 Hours |
| Initial Triage & Validation | 3 Business Days |
| Patch Development Start | 5 Business Days |
| Patch Release (or Public Disclosure) | 14 Business Days (Maximum) |

**Note:** Timelines may extend only if a dependency vendor requires longer coordination.

## Vulnerability Disclosure Policy (VDP)

We adhere to a strict coordinated vulnerability disclosure process. Public disclosure will **only** occur after:

1.  A stable patch has been released and tagged in the repository.
2.  The required coordination time with any affected third-party library vendors has elapsed.

## Development and Code Standards

To minimize risk, all code committed to the main branch must pass the following checks, as mandated by the CI pipeline (`.github/workflows/ci.yml`):

*   **Static Analysis:** Adherence to strict HTML/DOM security best practices. Client-side code (JavaScript injected into the dashboard) must be vetted for XSS vectors.
*   **Dependency Scanning:** Automated checks for known vulnerabilities in any included third-party scripts or libraries.
*   **Principle Enforcement:** All feature development must adhere to **DRY** (Don't Repeat Yourself) and **SOLID** principles to maintain architectural clarity and reduce unexpected attack surfaces.

## Security Audit & Review

Due to the project's reliance on client-side HTML rendering, security reviews prioritize data sanitization and DOM manipulation safety. Regular architectural reviews (per the **AGENTS.md** directives) ensure that no unauthorized tracking scripts or insecure rendering patterns are introduced.