# Nmap Network Scanning Assessment Report

## Assessment Information

| Item | Details |
|------|---------|
| Assessment Type | Network Reconnaissance & Enumeration |
| Scanner | Nmap 7.99 |
| Attacker Machine | Kali Linux |
| Target Machine | Metasploitable2 |
| Target IP | 192.168.0.9 |
| Network | VMware Bridged Network |
| Date | 11 July 2026 |

---

# Objective

The objective of this assessment was to identify active hosts, discover open ports, enumerate services, determine the operating system, and identify potential vulnerabilities using Nmap and the Nmap Scripting Engine (NSE).

---

# Scan Summary

The following scans were performed during the assessment:

| Scan | Command |
|------|---------|
| Host Discovery | `nmap -sn 192.168.0.9` |
| TCP SYN Scan | `nmap -sS 192.168.0.9` |
| Service Version Detection | `nmap -sV 192.168.0.9` |
| Operating System Detection | `nmap -O 192.168.0.9` |
| Aggressive Scan | `nmap -A 192.168.0.9` |
| UDP Fast Scan | `nmap -sU -F 192.168.0.9` |
| Vulnerability Scan | `nmap --script vuln 192.168.0.9` |

---

# Host Discovery

## Command

```bash
nmap -sn 192.168.0.9
```

## Observation

- Host is reachable.
- MAC Address belongs to VMware virtual machine.
- Network latency approximately 0.7 ms.

---

# TCP SYN Scan

## Command

```bash
nmap -sS 192.168.0.9
```

## Open TCP Ports

| Port | Service |
|------|---------|
|21|FTP|
|22|SSH|
|23|Telnet|
|25|SMTP|
|53|DNS|
|111|RPCBind|
|139|NetBIOS|
|445|SMB|
|512|Exec|
|513|Login|
|514|Shell|
|1099|Java RMI|
|1524|Bind Shell|
|2049|NFS|
|2121|FTP|
|3306|MySQL|
|5432|PostgreSQL|
|5900|VNC|
|6000|X11|
|6667|IRC|
|8009|AJP13|
|8180|HTTP|

---

# Service Version Detection

## Command

```bash
nmap -sV 192.168.0.9
```

## Detected Services

| Port | Service | Version |
|------|---------|---------|
|21|FTP|vsftpd 2.3.4|
|22|SSH|OpenSSH 4.7p1|
|23|Telnet|Linux Telnet|
|25|SMTP|Postfix|
|53|DNS|ISC BIND 9.4.2|
|139|SMB|Samba 3.x–4.x|
|445|SMB|Samba 3.x–4.x|
|2121|FTP|ProFTPD 1.3.1|
|3306|MySQL|5.0.51a|
|5432|PostgreSQL|8.3.x|
|6667|IRC|UnrealIRCd|
|8180|HTTP|Apache Tomcat 5.5|

---

# Operating System Detection

## Command

```bash
nmap -O 192.168.0.9
```

## Result

- Device Type: General Purpose
- Operating System: Linux
- Kernel Version: 2.6.x
- Network Distance: 1 Hop

---

# UDP Scan

## Command

```bash
nmap -sU -F 192.168.0.9
```

## Open UDP Ports

| Port | Service |
|------|---------|
|53|DNS|
|111|RPCBind|
|137|NetBIOS|
|2049|NFS|

---

# Aggressive Scan

## Command

```bash
nmap -A 192.168.0.9
```

## Information Gathered

- Anonymous FTP login enabled
- SSH Host Keys identified
- SMTP supports STARTTLS
- DNS version detected
- Samba version identified
- MySQL version detected
- Apache Tomcat identified
- NetBIOS information collected
- SMB Security Mode identified
- VNC service detected

---

# Vulnerability Scan

## Command

```bash
nmap --script vuln 192.168.0.9
```

## Important Findings

| Vulnerability | Severity |
|--------------|----------|
|vsFTPd 2.3.4 Backdoor (CVE-2011-2523)|Critical|
|SSL POODLE|High|
|Weak Diffie-Hellman Parameters|High|
|Logjam|High|
|RMI Remote Code Execution|Critical|
|SSL CCS Injection|High|
|UnrealIRCd Backdoor|Critical|
|Slowloris DoS|Medium|
|Tomcat Administrative Interface|Medium|

---

# Security Recommendations

- Disable Telnet and use SSH instead.
- Remove anonymous FTP access.
- Upgrade outdated services.
- Patch vulnerable software versions.
- Disable obsolete SSL protocols.
- Use stronger TLS cipher suites.
- Restrict administrative interfaces.
- Disable unnecessary network services.
- Apply firewall rules to limit exposed ports.
- Perform periodic vulnerability assessments.

---

# Conclusion

The assessment successfully demonstrated the use of Nmap for reconnaissance and service enumeration in a controlled laboratory environment. Multiple outdated services and intentionally vulnerable applications were identified on the Metasploitable2 target machine, making it an excellent platform for learning penetration testing techniques.

---
