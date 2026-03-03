# 🛡️ Security Portfolio — SOC / Blue Team Practice

Hands-on cybersecurity portfolio showcasing **phishing investigations, incident response documentation, SIEM monitoring labs, and automation scripts**.  
Built to demonstrate practical, job-ready skills for SOC / Security Analyst roles.

---

## 🚀 Highlights
- ✅ Phishing analysis + evidence preservation (headers, URLs, artifacts)
- ✅ Incident-response style reporting and documentation
- ✅ SOC lab projects (Wazuh / Splunk practice)
- ✅ Scripting to support investigations (Bash / Python / PowerShell)
- ✅ Clean Git workflow and repo hygiene (.gitignore, repeatable structure)

---
## 🔐 AWS OIDC Federation (GitHub → AWS)

Implemented secure CI/CD authentication using OpenID Connect (OIDC) between GitHub Actions and AWS.

### What Was Built

- GitHub OIDC identity provider in AWS IAM  
- IAM role with trust policy restricted to this repository  
- Role assumption via `sts:AssumeRoleWithWebIdentity`  
- No static access keys stored  

### Security Controls Demonstrated

- Least-privilege IAM role  
- Short-lived temporary credentials (STS)  
- Keyless CI/CD authentication  
- Federated identity trust validation  

### Proof of Implementation

Successful `aws sts get-caller-identity` call from GitHub Actions  
Assumed role: `GitHubActions-SecurityPortfolio`

---

## 🔐 Command History Prevention (Amazon Linux 2023 – EC2 Hardening)

To reduce the risk of exposing sensitive operational commands (tokens, IAM queries, internal paths), I implemented shell history suppression on my EC2 instance.

### Immediate Session Suppression

```bash
export HISTFILE=/dev/null
export HISTSIZE=0
export HISTFILESIZE=0
history -c
```

### Logout Hardening (`~/.bash_logout`)

```bash
history -c
history -w
rm -f ~/.bash_history
```

### Verification After Reconnect

```bash
cat ~/.bash_history
```

**Result**

No such file or directory


Security Impact

Prevents accidental AWS credential exposure

Reduces post-compromise artifact retention

Mirrors SOC jump-host hardening practices

---

## 📁 Repository Structure

| Folder | What’s inside | Skills shown |
|---|---|---|
| **01_Case_Reports/** | Investigation writeups and findings | Documentation, analysis, reporting |
| **02_Lab_Projects/** | Monitoring / SOC lab exercises | Detection, logging, validation |
| **03_Tools_and_Scripts/** | Helper scripts + tooling notes | Automation, repeatability |
| **04_Screenshots_and_Evidence/** | Supporting screenshots / evidence | Evidence handling, clarity |

---

## 🧪 Featured Work

### 📌 Email Investigation (Open Enrollment / Benefits)
**Goal:** Determine whether the email was legitimate or malicious using structured analysis.  
**Process included:**
- Message review + sender validation checks  
- Artifact collection (attachments, trackers, screenshots)  
- Documentation of findings and next-step recommendations

📄 **Report:** `01_Case_Reports/Email_Investigations/2026-02-22_Open_Enrollment_Email_Investigation.pdf`  
🧾 **Artifacts:** `01_Case_Reports/Email_Investigations/Raw_Email_Artifacts/`

---

## 🛠️ Tools Used
- **macOS Terminal**, Git/GitHub
- **VirtualBox** (lab environments)
- **Wazuh / Splunk (learning + practice)**
- Basic OSINT + safe link handling (in isolated environments)

---

## 🔒 Notes on Safety & Privacy
This portfolio is designed to avoid exposing sensitive information.
- Personal identifiers should be redacted before upload.
- Investigation content is presented for educational and professional demonstration.

---

## 📬 Contact
If you’d like to discuss my work or request a walkthrough, feel free to connect via GitHub.


