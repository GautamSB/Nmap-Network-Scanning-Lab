# Nmap Network Scanning Lab

## 📖 Overview

This repository demonstrates the use of **Nmap (Network Mapper)** for performing network reconnaissance and enumeration in a controlled virtual lab environment.

The project covers the complete reconnaissance phase of a penetration test, including host discovery, port scanning, service enumeration, operating system detection, and vulnerability identification using the Nmap Scripting Engine (NSE).

---

# 🎯 Objective

The primary objectives of this lab are to:

- Discover live hosts on the network
- Identify open TCP ports
- Enumerate running services
- Detect service versions
- Identify the target operating system
- Perform vulnerability detection using NSE scripts
- Document findings and recommend security improvements

---

# 🖥️ Lab Environment

| Component | Details |
|-----------|---------|
| Attacker Machine | Kali Linux |
| Target Machine | Metasploitable2 |
| Virtualization | VMware Workstation |
| Scanner | Nmap |
| Network Type | Bridged Network |

---

# 🛠️ Tools Used

- Kali Linux
- Nmap
- VMware Workstation
- Metasploitable2

---

# 📚 Methodology

The assessment was performed using the following methodology:

1. Verify network connectivity.
2. Perform host discovery.
3. Scan for open TCP ports.
4. Detect running services and versions.
5. Identify the operating system.
6. Execute default NSE scripts.
7. Perform vulnerability scanning.
8. Analyze the results.
9. Document findings.
10. Recommend security improvements.

---

# 💻 Commands Used

### Host Discovery

```bash
nmap -sn <Target-IP> -Pn
```

Discovers whether the target host is online.
-Pn --> Disable Port Scanning

---

### TCP SYN Scan

```bash
nmap -sS <Target-IP>
```

Performs a stealth SYN scan to identify open TCP ports.

---

### Service Version Detection

```bash
nmap -sV <Target-IP>
```

Identifies the version of services running on open ports.

---

### Operating System Detection

```bash
nmap -O <Target-IP>
```

Attempts to identify the target operating system.

---

### Aggressive Scan

```bash
nmap -A <Target-IP>
```

Performs:

- OS Detection
- Version Detection
- Script Scanning
- Traceroute

---

### Default NSE Scripts

```bash
nmap -sC <Target-IP>
```

Executes the default Nmap Scripting Engine scripts.

---

### Vulnerability Scan

```bash
nmap --script vuln <Target-IP>
```

Runs vulnerability detection scripts against the target.

---

# 📊 Results

The assessment successfully identified:

- Live target host
- Open TCP ports
- Running network services
- Service versions
- Operating system details
- Potential vulnerabilities detected through NSE scripts

---

# 📷 Screenshots

Screenshots will be added after completing the assessment.

Example:

```
screenshots/
│── host-discovery.png
│── syn-scan.png
│── version-detection.png
│── os-detection.png
│── aggressive-scan.png
│── vulnerability-scan.png
```

---

# 📖 Learning Outcomes

This project helped me understand:

- Network reconnaissance
- Host discovery techniques
- TCP SYN scanning
- Service enumeration
- Version detection
- Operating system fingerprinting
- Nmap Scripting Engine (NSE)
- Basic vulnerability identification
- Security reporting and documentation

---

## 👨‍💻 Author

**Gautam S B**

Aspiring Cybersecurity Engineer | VAPT Enthusiast

GitHub: https://github.com/GautamSB
