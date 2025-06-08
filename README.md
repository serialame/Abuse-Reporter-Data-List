# Abuse Reporter Data List

A community-sourced list categorizing abuse reporters to help network administrators triage reports efficiently, based on specific operational hallmarks.

---

### Hallmarks of a Good Reporter (High-Signal, Actionable)

* **Evidence Integrity:** Provides **conclusive, self-contained proof**. This includes full packet captures (PCAPs) for network attacks, complete SMTP session transcripts for spam, malware hashes, or full web server logs with request and response headers.
* **Intelligent Attack Classification:** Accurately distinguishes between different types of malicious activity (e.g., "SSH Brute-force," "SQL Injection Attempt," "RDP Credential Stuffing"). It does **not** misrepresent passive scanning as an active attack.
* **Threshold-Based Reporting:** The system uses intelligent thresholds to avoid noise. For example, it only reports after >5 failed SSH logins from an IP in 10 minutes, not on the first attempt.
* **Procedural Excellence:** Strictly adheres to industry standards. This means using the **Abuse Reporting Format (ARF)**, correctly parsing RIR/WHOIS data to use the designated `abuse@` contact, and respecting mailer-daemon bounces.
* **Contextual Awareness:** Demonstrates an understanding of the internet ecosystem. It does **not** report traffic from known, legitimate research projects (e.g., Shodan, Censys, university scanners) as inherently malicious.
* **Reputation & Trust:** Is a known, trusted entity within the security community (e.g., The Shadowserver Foundation, Spamhaus) whose findings carry inherent weight.

---

### Hallmarks of a Bad Reporter (Low-Signal, Noisy)

* **Evidence Misrepresentation:** **Falsifies or misinterprets evidence**. The most common example is reporting a single TCP SYN packet as a "port scan attack" or "completed connection" without proof of a three-way handshake.
* **Context Ignorance:** Lacks awareness of the internet landscape. It flags benign traffic from major cloud providers, CDNs, or well-known research projects as malicious.
* **No-Threshold Automation:** Utilizes "fire-and-forget" scripts that trigger on **any single event** (e.g., one connection to a closed port), generating massive volumes of useless reports.
* **Procedural Negligence:** Fails at basic operational procedure. This includes using outdated WHOIS data, mailing generic contacts like `noc@` or `info@`, and continuing to send reports to mailboxes that have already issued bounce notifications.
* **Burdensome Reporting ("Click-to-View"):** Offloads the burden of proof by requiring the recipient to click an external link to view the evidence. This is inefficient and a potential security risk.
* **No Recourse:** Provides no clear, functional method for an operator to report a false positive or request a correction. The reporting channel is a one-way street.

---

## Useless Reporters (Low Signal)

| Domain/Name                 | Primary Red Flag(s)                                 |
| --------------------------- | --------------------------------------------------- |
| `hetzner.com`               | No-Threshold Automation, Evidence Misrepresentation |
| `ipv6home.arpa`             | Evidence Misrepresentation                          |
| `shkron.com`                | Evidence Misrepresentation                          |
| `watchdogcyberdefense.com`  | Evidence Misrepresentation                          |
| `bitninja.com`              | No-Threshold Automation, Burdensome Reporting       |
| `cert.br`                   | Procedural Negligence, Report Spam                  |
| `abusix.com`                | No-Threshold Automation                             |
| `redfish-solutions.com`     | Evidence Misrepresentation                          |
| `egp-inc.com`               | Evidence Misrepresentation                          |
| `agouros.de`                | Evidence Misrepresentation, Context Ignorance       |
| `mhcointeam.com`            | Evidence Misrepresentation                          |
| `columbia.edu`              | Context Ignorance                                   |
| `digitaltrustcenter.nl`     | No-Threshold Automation                             |
| `netabuse.io`               | Burdensome Reporting                                |
| `csirt.org`                 | Evidence Misrepresentation (Varies by branch)       |
| `serverplan.com`            | Evidence Misrepresentation                          |
| Gert Doering (Individual)   | Evidence Misrepresentation                          |
| `shinhan.com`               | Evidence Misrepresentation                          |
| `jcloud.ik`                 | Evidence Misrepresentation                          |
| `mieweb.com`                | Evidence Misrepresentation                          |

---

## Useful Reporters (High Signal)

| Domain                | Primary Hallmark(s)                                 |
| --------------------- | --------------------------------------------------- |
| `aws.amazon.com`      | Evidence Integrity                                  |
| `nforce.com`          | Evidence Integrity                                  |
| `spamhaus.org`        | Reputation & Trust, Threshold-Based Reporting       |
| `urlhaus.abuse.ch`    | Evidence Integrity, Attack Classification           |
| `skt-telecom.com`     | Evidence Integrity                                  |
| `honeypots.tk`        | Evidence Integrity, Contextual Awareness            |
| `openthink.co`        | Threshold-Based Reporting                           |
| `blocklist.de`        | Evidence Integrity, Attack Classification           |
| `feldhost.net`        | Threshold-Based Reporting                           |
| `j0ke.net`            | Evidence Integrity                                  |
| `liquidnet.com`       | Evidence Integrity                                  |
| `linode.com`          | Evidence Integrity, Procedural Excellence           |
