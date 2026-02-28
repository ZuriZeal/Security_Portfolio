# Fail2Ban Intrusion Prevention (AWS EC2)

This folder contains evidence from my AWS EC2 security lab where I configured Fail2Ban to permanently ban attacker IPs and enforce blocking using firewalld rich rules.

## Evidence Included
- Fail2Ban jail status (apache-auth, apache-badbots, apache-recon)
- Permanent ban confirmation (bantime = -1)
- Firewalld rich rules proving network-layer blocking
- Fail2Ban log showing ban events
- Service status verification
