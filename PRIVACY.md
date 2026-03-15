# Hackboard — Privacy Policy

**Effective Date:** 16 February 2026

---

## 1. Introduction and Data Controller

This Privacy Policy explains what data we collect, why we collect it, how we process and store it, and what rights you have regarding your data when you use **Hackboard**, a keyboard customization application for macOS. Terms used in this Privacy Policy (such as "Company", "Software", and "Configurations") have the meanings defined in our [Terms of Service](TERMS.md), Section 2.

The data controller responsible for processing your data is:

**Farbe Software UG (haftungsbeschränkt)**\
Brauhausstr. 16\
13086 Berlin, Germany

Managing Director (Geschäftsführer): Arndt Haßel-Kurz\
Commercial Register: Amtsgericht Charlottenburg, HRB 277917\
Email: contact@farbe-software.com

(Information provided in accordance with § 5 DDG.)

For the terms governing your use of Hackboard, see our [Terms of Service](TERMS.md).

**Data Protection Officer.** The Company has not appointed a Data Protection Officer, as it does not meet the applicable thresholds under Art. 37 GDPR or § 38 BDSG (fewer than 20 persons regularly engaged in automated data processing).

---

## 2. What Data We Collect

### 2.1. Crash Reports and Error Logs

Hackboard can collect crash reports and error logs to help us identify and fix bugs, improve software quality, and ensure stability. **Crash reporting is optional and disabled by default.** You can enable or disable it at any time in the Hackboard settings.

The following data is collected when a crash or error occurs:

- Crash stack traces and error messages
- Operating system version and macOS version
- Device model
- Hackboard application version
- Locale and timestamp
- A log of recent app interactions and system events leading up to the crash (such as navigation events and network request metadata)
- Device context (device type, screen resolution, memory — no user-identifiable device IDs)
- Error context messages added by the application's internal logging

Crash reports do not intentionally collect personal data such as your name, email address, or the content of your keyboard configurations. However, crash data may incidentally contain technical identifiers or configuration fragments in stack traces. We process any such data in accordance with this Privacy Policy.

Crash reports are collected only in release builds. Debug and development builds do not transmit any data.

Crash reporting is entirely voluntary and has no effect on your use of Hackboard. The Software is fully functional without crash reporting enabled.

### 2.2. User Feedback

You may voluntarily submit feedback through the feedback dialog within Hackboard. No feedback data is ever collected without your affirmative action — you must open the dialog, write a message, and explicitly click "Send."

When you submit feedback, the following data is collected:

- **Feedback message** (free-text, always required)
- **Contact email address** (optional — you may leave this blank)
- **Configuration file attachments** (opt-in via a separate checkbox):
  - `karabiner.json` — your Karabiner Elements configuration file
  - `hb_keymaps.json` — your Hackboard keymaps configuration file

**Note on configuration files.** Your keyboard configurations belong to you (see [Terms of Service](TERMS.md), Section 8.2). Depending on your setup, configuration files may contain shell commands, file paths, or other data that could be personally identifiable. We recommend reviewing your configuration files before attaching them. Configuration files are only attached when you explicitly opt in via the checkbox.

Submitting feedback is entirely voluntary and has no effect on your use of Hackboard.

### 2.3. Update Checks

Hackboard uses Sparkle, an open-source update framework, to check for new versions. **Automatic update checks are optional.** On second launch, Hackboard asks whether you want to check for updates automatically. You can change this choice at any time in the Hackboard settings. You can also check for updates manually via the "Check for Updates" menu item.

When an update check occurs (whether automatic or manual), the following data is transmitted:

- Your **IP address** (as part of the standard HTTP request)
- **User-Agent string** (Hackboard version, macOS version, and machine architecture)

This data is sent to **GitHub Pages** (`farbe-software.github.io`), where the update feed is hosted. No data is stored by us as part of this process — any server logs are controlled by GitHub (see Section 4.2).

### 2.4. What We Do Not Collect

Hackboard does **not** collect:

- Usage analytics or behavioural telemetry
- Advertising trackers, pixels, or third-party tracking scripts
- Cookies or similar tracking technologies
- Personal identifiers such as names, usernames, or account data (no accounts exist)
- Keystroke data, keyboard input content, or typing patterns
- IP addresses in crash reports (scrubbed before storage)

**Note on keyboard input processing.** Hackboard's keyboard remapping component processes all keyboard input locally on your device in real time. This processing is entirely ephemeral — no keystroke data is stored, logged, or transmitted. This local processing is necessary for the core keyboard remapping functionality and does not trigger data protection obligations, as no personal data leaves your device.

We do not sell or share your personal data with third parties for advertising or marketing purposes. We will not discriminate against you or restrict your access to Hackboard for exercising any privacy right.

---

## 3. Legal Bases for Processing

### 3.1. Crash Reports and Error Logs

**Legal basis:** Art. 6(1)(a) GDPR — Consent.

Crash reporting is optional and disabled by default. When you enable crash reporting in the Hackboard settings, you consent to the processing described in Section 2.1. You may withdraw your consent at any time by disabling crash reporting in the settings (see Section 7 below). Withdrawal does not affect the lawfulness of processing carried out before withdrawal.

### 3.2. User Feedback

**Legal basis:** Art. 6(1)(a) GDPR — Consent.

Your feedback is submitted through a clear affirmative action. The consent is granular: the contact email address is optional, and the attachment of configuration files requires a separate opt-in checkbox. You may withdraw your consent at any time by contacting us to request deletion of your feedback data (see Section 7).

### 3.3. Update Checks

**Legal basis:** Art. 6(1)(a) GDPR — Consent.

Automatic update checks are enabled only if you opt in via Sparkle's permission prompt. You may disable automatic checks at any time in the Hackboard settings. Manual update checks are initiated by your deliberate action. You may withdraw your consent to automatic update checks at any time by disabling them in the settings.

### 3.4. Necessity of Data Provision

Providing personal data to Hackboard is not a statutory or contractual requirement. All data collection (crash reports, feedback, update checks) is voluntary. There are no consequences for choosing not to provide data — the Software is fully functional without any data collection enabled.

### 3.5. Device Storage and Access (TTDSG § 25)

To the extent that Hackboard or its components store information on or access information from your device, the following applies under § 25 TTDSG:

- **Crash reporting:** Consent-based (see Section 3.1). The Sentry SDK may temporarily store crash envelopes on disk before transmission. This storage occurs only when you have enabled crash reporting.
- **Update checks:** Consent-based (see Section 3.3). Sparkle stores local preferences (such as the time of the last update check) to manage the update process. These are stored only when you have opted in to automatic update checks.

### 3.6. Automated Decision-Making

Hackboard does not use automated decision-making, including profiling, within the meaning of Art. 22 GDPR.

---

## 4. How We Process and Store Data

### 4.1. Data Processor

Crash reports, error logs, and user feedback are processed by:

**Functional Software, Inc.** (trading as "Sentry")\
45 Fremont Street, 8th Floor\
San Francisco, CA 94105, USA\
Website: [sentry.io](https://sentry.io)

Sentry acts as a data processor on our behalf. A Data Processing Agreement (DPA) is in place, available at [sentry.io/legal/dpa/](https://sentry.io/legal/dpa/).

### 4.2. Update Check Hosting

Update checks are served from **GitHub Pages**, a hosting service operated by **GitHub, Inc.** (a subsidiary of Microsoft Corporation). When an update check occurs, your IP address and User-Agent string are transmitted to GitHub's servers as part of the HTTP request. We do not control or have access to any server logs GitHub may retain. GitHub's privacy practices are governed by the [GitHub Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement).

### 4.3. Storage Location

All data processed through Sentry is stored in the **EU (Germany)** using Sentry's DE region (`de.sentry.io`). No data is transferred to the United States or any other country outside the EU/EEA (see Section 6).

### 4.4. Security Measures

**Sentry-side measures:**

- Data encrypted in transit (TLS) and at rest
- SOC 2 Type II certified
- Access controls and audit logging
- Full security and compliance details: [sentry.io/security/](https://sentry.io/security/)

**Company-side measures:**

- Configured to not send personally identifiable information (`sendDefaultPii = false`)
- No personal identifiers collected by design
- No Sentry performance monitoring or session replay enabled

---

## 5. Data Retention

- **Crash reports and error logs:** Retained for **30 days**, after which they are automatically and permanently deleted by Sentry.
- **User feedback:** Retained for **30 days**, following the same automatic deletion cycle. After deletion, no personal data from your feedback remains in our systems. Any ideas or suggestions from your feedback that have been incorporated into Hackboard's development persist only as part of the Software itself — not as stored personal data.

---

## 6. International Data Transfers

**Crash reports, error logs, and user feedback** are processed and stored in **Germany (EU)** using Sentry's DE region. No crash or feedback data is transferred to the United States or any other country outside the EU/EEA. Sentry's parent company (Functional Software, Inc.) is incorporated in the United States, but all Hackboard data remains in Sentry's EU infrastructure. Sentry's DPA includes Standard Contractual Clauses (SCCs) as a fallback safeguard.

**Update checks** are served from GitHub Pages. GitHub's infrastructure is global, and your IP address and User-Agent string may be processed on servers located outside the EU/EEA, including in the United States. The EU–US Data Privacy Framework provides an adequacy basis for these transfers. GitHub's privacy practices are described in the [GitHub Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement).

If you are located outside the EU/EEA, your crash and feedback data is transferred to and stored in Germany, where it is protected under the GDPR.

---

## 7. Your Rights Under GDPR

You have the following rights regarding your personal data:

- **Right of access** (Art. 15 GDPR) — You may request confirmation of whether your data is processed and access to that data.
- **Right to rectification** (Art. 16 GDPR) — You may request correction of inaccurate data.
- **Right to erasure** (Art. 17 GDPR) — You may request deletion of your data.
- **Right to restriction of processing** (Art. 18 GDPR) — You may request restriction of processing in certain circumstances.
- **Right to data portability** (Art. 20 GDPR) — You may request your data in a structured, commonly used, machine-readable format.
- **Right to object** (Art. 21 GDPR) — You may object to processing based on legitimate interest.
- **Right to withdraw consent** (Art. 7(3) GDPR) — Where processing is based on consent (crash reporting, automatic update checks, user feedback), you may withdraw your consent at any time. Withdrawal does not affect the lawfulness of processing carried out before withdrawal.
- **Right to lodge a complaint** (Art. 77 GDPR) — You may file a complaint with a supervisory authority.

To exercise any of these rights, please contact us at **contact@farbe-software.com**. We will respond without undue delay and in any event within **one month** of receipt. If your request is complex or we receive a large number of requests, we may extend this period by up to two further months, in which case we will inform you of the extension and the reasons within the first month (Art. 12(3) GDPR).

**Note on identification of data (Art. 11 GDPR).** Crash report data is collected without personal identifiers — no IP addresses, no user IDs, and no account information. As a result, we may not be able to identify your specific data within our systems. We make best efforts to fulfil your requests, but where we cannot identify you as the data subject, we may be unable to fulfil access, rectification, erasure, restriction, or portability requests for that data, in accordance with Art. 11 GDPR. If you provide details about your device and the approximate time of a crash, we will search for matching records. If you submitted user feedback with your email address, we can identify and process requests relating to that data.

**Right to withdraw consent for crash reporting.** You may withdraw your consent to crash reporting at any time by disabling it in the Hackboard settings. Once disabled, no further crash data will be collected or transmitted. Withdrawal does not affect the lawfulness of data processed before withdrawal.

**Supervisory authority.** You have the right to lodge a complaint with the competent data protection authority:

Berliner Beauftragte für Datenschutz und Informationsfreiheit\
Alt-Moabit 59–61\
10555 Berlin, Germany\
Website: [www.datenschutz-berlin.de](https://www.datenschutz-berlin.de)

If you are located in the United Kingdom, you may also lodge a complaint with the Information Commissioner's Office (ICO) at [ico.org.uk](https://ico.org.uk).

---

## 8. Children's Data

Hackboard does not target children and does not knowingly collect personal data from children under 16 years of age. Under Art. 8 GDPR, the minimum age for consenting to data processing is 16 in Germany. Our [Terms of Service](TERMS.md) (Section 3.3) separately require users under 18 to have parental consent for the contractual agreement itself, as required by § 107 BGB. The different thresholds reflect different legal requirements: 16 for data processing consent, 18 for contractual capacity.

If you are a parent or guardian and believe that your child has provided personal data to us, please contact us at **contact@farbe-software.com** and we will take steps to delete that data.

---

## 9. Changes to This Policy

We may update this Privacy Policy from time to time. Updated versions will be posted in this repository with a revised effective date.

For changes that materially affect your rights, we will provide at least **14 days' advance notice** before the changes take effect. Notice may be given through this repository, within the Software, or through other appropriate channels.

We encourage you to review this Privacy Policy periodically. The current version is always available in this repository as [PRIVACY.md](PRIVACY.md).

---

## 10. Contact Information

For questions about this Privacy Policy or to exercise your data protection rights, please contact:

**Farbe Software UG (haftungsbeschränkt)**\
Brauhausstr. 16\
13086 Berlin, Germany

Managing Director (Geschäftsführer): Arndt Haßel-Kurz\
Commercial Register: Amtsgericht Charlottenburg, HRB 277917\
Email: contact@farbe-software.com

---

*This Privacy Policy was last updated on 16 February 2026.*
