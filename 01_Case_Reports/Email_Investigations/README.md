# 🛡 Email Phishing Investigation – Open Enrollment Case

**Investigator:** Zuri  
**Date:** 2026-02-22  
**Category:** Email Security / Phishing Analysis  
**Environment:** macOS Terminal + Manual Header Analysis  

---

## 📌 Executive Summary

An email titled **“Your Benefits Open Enrollment is Now Open!”** was received and flagged for potential phishing activity.

This investigation analyzed the domain, SSL certificate, authentication headers (SPF/DKIM/DMARC), and embedded tracking artifacts to determine legitimacy.

---

## 🎯 Objectives

- Validate sender authenticity
- Investigate domain registration (WHOIS)
- Inspect SSL certificate details
- Analyze email headers
- Identify tracking or malicious artifacts

---

## 🔎 Investigation Workflow

### 1️⃣ Domain Analysis
- Performed WHOIS lookup on `enrollment123.com`
- Reviewed domain age and registration transparency
- Assessed ownership visibility

### 2️⃣ SSL Certificate Inspection
- Pulled certificate metadata
- Verified issuer and validity period
- Confirmed encryption configuration

### 3️⃣ Email Header Analysis
- Reviewed SPF results
- Checked DKIM signature status
- Evaluated DMARC policy
- Analyzed sending IP infrastructure

### 4️⃣ Artifact Examination
- Extracted `.eml` file
- Reviewed `.rtfd` contents
- Identified tracking pixel (`track.cfm.gif`)
- Examined embedded images

---

## 🚨 Indicators of Concern

- Tracking pixel detected
- Domain registration characteristics require validation
- Social engineering theme (HR / Benefits)
- Potential credential harvesting vector

---

## 📊 Risk Assessment

| Category | Rating |
|----------|--------|
| Threat Type | Phishing |
| Likely Objective | Credential Harvesting |
| Impact Level | Moderate |
| Confidence | Medium |

---

## 🧰 Tools Used

- `whois`
- `openssl`
- macOS Terminal (`cd`, `ls`, `tree`, `mv`)
- Manual header inspection

---

## 📂 Evidence Structure

Email_Investigations
├── 2026-02-22_Open_Enrollment_Email_Investigation.pdf
├── Raw_Email_Artifacts
│ ├── Your Benefits Open Enrollment is Now Open!.eml
│ └── Your Benefits Open Enrollment is Now Open!.rtfd


---

## 📘 Lessons Learned

- Always verify domain age and registration transparency
- Tracking pixels are common in phishing campaigns
- Header authentication checks are critical
- Never respond before validating infrastructure

---

## 💼 Portfolio Note

This case demonstrates:

- Structured incident documentation
- Command-line evidence handling
- Email security analysis
- Entry-level SOC investigative methodology

---
