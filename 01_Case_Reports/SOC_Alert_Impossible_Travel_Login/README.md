# SOC Alert Investigation — Impossible Travel Login

## Alert Summary

A SIEM alert detected two login events for the same user account from geographically distant locations within a short time window.

This pattern is commonly referred to as **“impossible travel”** and may indicate account compromise.

---

## Alert Details

User: j.smith

Login Event 1
Location: Austin, Texas, USA
IP: 172.58.41.22

Login Event 2
Location: Moscow, Russia
IP: 185.220.101.45

Time difference: 5 minutes

---

## Investigation Process

### 1. Review Login Activity

Login records show two authentication events from locations separated by approximately **9,400 km** within five minutes.

Travel between these locations within this timeframe is not physically possible.

---

### 2. Historical Login Behavior

Review of past login records indicates the user normally logs in from Texas.

The Russia login is inconsistent with the user’s normal behavior.

---

### 3. IP Reputation Analysis

The Russian IP address was checked using threat intelligence tools.

The address has previously been associated with suspicious activity.

---

## Conclusion

The alert likely indicates **compromised credentials** due to:

• Impossible travel pattern  
• Login from unfamiliar geographic location  
• Suspicious IP reputation

---

## Recommended Response

• Reset affected user credentials  
• Enable multi-factor authentication (MFA)  
• Review recent account activity  
• Block suspicious IP address

---

## Evidence Collected

- `login_logs.txt`
- `investigation_notes.txt`
