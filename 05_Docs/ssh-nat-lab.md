# SSH NAT Port Forwarding Lab – VM to macOS Validation

## Objective
Configure SSH access from macOS host to Ubuntu VM using VirtualBox NAT port forwarding.

## Environment
- Host: macOS
- Guest: Ubuntu 22.04 LTS
- Hypervisor: VirtualBox
- Forwarded Port: Host 2222 → Guest 22

## Steps Performed

### 1. Configure NAT Port Forwarding
Host Port: 2222  
Guest Port: 22  

### 2. Validate SSH Service on VM
```bash
ss -tulpn | grep ssh
