# cybersecurity-project
# The 2022 Uber Cyber Attack: MFA Fatigue & Social Engineering Analysis

#### Video URL: [https://youtu.be/C26kSc3u0Dc]

#### Description:
This final project for CS50's Introduction to Cybersecurity analyzes the high-profile 2022 cyber attack on Uber. The incident serves as a primary example of how human vulnerabilities, combined with flawed Multi-Factor Authentication (MFA) implementations and poor secrets management, can lead to a total corporate network breach.

### Case Overview
In September 2022, an 18-year-old threat actor associated with the Lapsus$ group successfully breached Uber's internal corporate environment. The attacker acquired the corporate credentials of an external contractor through dark-web credential dumps. However, because Uber enforced MFA, the password alone was insufficient.

### Attack Vector & Exploitation
1. **MFA Fatigue:** The attacker repeatedly triggered MFA push notifications to the victim's smartphone late at night.
2. **Social Engineering:** Impersonating Uber's IT security team on WhatsApp, the attacker convinced the contractor to approve the MFA prompt to resolve the notification spam.
3. **Privilege Escalation:** Once inside the internal network, the attacker scanned network shares and discovered a PowerShell script containing hardcoded plain-text credentials for Uber's Privileged Access Manager (Thycotic).
4. **Infrastructure Compromise:** Using these domain admin credentials, the attacker gained full access to critical services including Google Workspace, AWS, Slack, and financial systems.

### Cybersecurity Concepts & Countermeasures
This breach highlights several key concepts taught in CS50 Cybersecurity:
* **MFA Vulnerabilities & Mitigation:** Traditional push notifications can be exploited via fatigue. Organizations should adopt FIDO2 security keys or MFA Number Matching to ensure physical proximity.
* **Secrets Management:** Hardcoded credentials in internal scripts violate secure coding standards. Privileged credentials should be stored in secure vaults with strict access controls.
* **Zero Trust & Network Segmentation:** Implementing strict network segmentation and least-privilege access controls limits lateral movement even after initial access is gained.
