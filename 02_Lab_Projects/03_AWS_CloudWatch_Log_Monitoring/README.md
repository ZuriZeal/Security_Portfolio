# AWS CloudWatch Log Monitoring Lab

## Objective

Configure and validate AWS CloudWatch log ingestion from an Amazon Linux 2023 EC2 instance.  
Demonstrate cloud logging visibility and audit readiness aligned with SOC monitoring practices.

---

## Environment

- AWS Region: US East (Ohio) – us-east-2
- EC2 OS: Amazon Linux 2023
- Services Used:
  - CloudWatch Logs
  - EC2
  - IAM
- Access Method: SSH via macOS Terminal

---

## Implementation Steps

### 1️⃣ EC2 Instance Access

Connected via SSH:

```bash
ssh soc-lab
```

---

### 3️⃣ CloudWatch Log Group Verification

Validated the following log groups in AWS CloudWatch:

- `/soc/auditd`
- `ec2-audit-logs`
- `ec2-auth-logs`

Navigation path:

CloudWatch → Logs → Log groups → Log stream

Confirmed:
- Log groups indexed
- Log streams active
- Event entries visible
- Ingestion functioning properly