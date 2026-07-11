# Lab Setup

## Objective
Build an isolated home lab environment for practicing penetration testing techniques safely, without affecting the host network.

## Tools & Technologies
- VMware Workstation Pro
- Kali Linux (attacker machine)
- Metasploitable 2 (vulnerable target)

## Steps

### 1. Network Configuration
Created an isolated Host-only virtual network (VMnet2) using VMware's Virtual Network Editor to ensure the vulnerable target machine has no exposure to the internet or home network.

### 2. Kali Linux Setup
- Downloaded the official Kali Linux VMware image
- Connected the primary network adapter to VMnet2
- Later added a second NAT adapter for internet access (package updates, GitHub), while keeping the lab-facing adapter on VMnet2

### 3. Metasploitable 2 Setup
- Downloaded Metasploitable 2
- Connected to VMnet2 only (no internet access, intentionally vulnerable)

### 4. Connectivity Verification
Confirmed both machines could communicate over VMnet2 using ping.

## Findings
- Kali IP: 192.168.151.129
- Metasploitable IP: [192.168.151.128]

## Notes
Keeping Metasploitable isolated from the internet is critical since it is intentionally vulnerable software.
