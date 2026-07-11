# Metasploitable 2 Reconnaissance

## Objective
Perform network reconnaissance on the target machine to identify open ports, running services, and potential attack vectors.

## Tools Used
- Nmap

## Command nmap -sV -sC 192.168.151.128

## Key Findings
Over 20 open ports were discovered, including several with known, severe vulnerabilities:

| Port | Service | Version | Risk |
|------|---------|---------|------|
| 21   | FTP     | vsftpd 2.3.4 | Critical — known backdoor |
| 23   | Telnet  | Linux telnetd | High — unencrypted remote access |
| 445  | SMB     | Samba 3.0.20 | High — known SMB exploits |
| 3306 | MySQL   | 5.0.51a | Medium — outdated, weak default config |
| 6667 | IRC     | UnrealIRCd | High — known backdoor exploits |

Full scan results saved in `nmap-scan-results.txt`.

## Next Steps
Prioritized the vsftpd 2.3.4 backdoor (port 21) for exploitation due to its severity and ease of exploitation — see `03-metasploitable-exploitation/`.
