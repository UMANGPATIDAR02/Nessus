# Nessus Vulnerability Assessment Lab

## 📌 Overview

This project demonstrates a **vulnerability assessment lab** using **Tenable Nessus Essentials** to identify, analyze, and remediate security vulnerabilities in a controlled environment. The lab simulates a real‑world penetration testing workflow on intentionally vulnerable hosts (e.g., Metasploitable / legacy Linux services) within a local network.

The objective is to:

* Perform authenticated and unauthenticated scans
* Identify critical and high‑risk vulnerabilities
* Analyze CVSS severity and affected services
* Provide remediation recommendations
* Generate professional security reports

---

## 🧰 Tools & Technologies

* **Scanner:** Tenable Nessus Essentials
* **OS (Scanner):** Kali Linux
* **Target Hosts:** Vulnerable Linux VM(s)
* **Virtualization:** VirtualBox / VMware
* **Network:** Host‑Only / NAT Lab Network

---

## 🏗️ Lab Architecture

```
+----------------------+        +----------------------+
|  Kali Linux (Nessus) | -----> |  Vulnerable Target   |
|  192.168.241.x       |        |  192.168.241.128     |
+----------------------+        +----------------------+
```

* Nessus scanner deployed on Kali Linux
* Target host exposed vulnerable services (SSH, HTTP, SSL, DB, etc.)
* Local isolated subnet for safe testing

---

## ⚙️ Nessus Configuration

**Scan Type:** Basic Network Scan
**Scanner:** Local Scanner
**Severity Base:** CVSS v3.0
**Scan Duration:** ~7–30 minutes
**Authentication:** Enabled (where applicable)

Steps:

1. Install Nessus Essentials on Kali Linux
2. Activate license (free Essentials key)
3. Create new scan → Basic Network Scan
4. Add target IP (e.g., `192.168.241.128`)
5. Launch scan
6. Review vulnerabilities & remediation

---

## 🔍 Scan Results Summary

Example results from lab scans:

| Severity | Count    |
| -------- | -------- |
| Critical | Multiple |
| High     | Multiple |
| Medium   | Several  |
| Low      | Few      |
| Info     | Many     |

### Key Findings

* Bash Remote Code Execution (Shellshock)
* Outdated CentOS packages
* SSL/TLS configuration issues
* Apache HTTP vulnerabilities
* Ruby / Python library DoS issues
* Weak or legacy cryptographic settings

---

## 🚨 Example Critical Vulnerabilities

### 1. Bash Remote Code Execution (Shellshock)

**Severity:** Critical
**Impact:** Remote attackers can execute arbitrary commands via crafted environment variables.
**Affected:** Bash on legacy Linux systems
**Risk:** Full system compromise

**Remediation:**

* Update Bash to patched version
* Apply vendor security patches
* Restart affected services

---

### 2. Outdated CentOS Packages

**Severity:** Critical
**Impact:** Multiple known CVEs exploitable
**Affected:** Firefox, Java, Samba, Kerberos, etc.

**Remediation:**

```bash
yum update -y
```

---

### 3. SSL/TLS Weak Configuration

**Severity:** Medium–High
**Impact:** MITM / downgrade attacks
**Issues:**

* Weak ciphers
* Deprecated TLS versions

**Remediation:**

* Disable SSLv2/SSLv3/TLS1.0
* Enable TLS1.2+
* Use strong cipher suites

---

## 🛠️ Remediation Strategy

Priority‑based remediation approach:

1. Patch critical RCE vulnerabilities
2. Update OS packages
3. Harden network services
4. Strengthen cryptography
5. Remove unnecessary services

---

## 📊 Risk Assessment

**Overall Risk Level:** High
Reason:

* Presence of remote code execution
* Legacy OS versions
* Multiple high CVSS scores
* Publicly exploitable vulnerabilities

---

## 📄 Reporting

Nessus reports exported in:

* HTML
* PDF
* CSV

Report includes:

* CVSS score
* Description
* Affected host
* Proof of detection
* Remediation steps

---

## ✅ Conclusion

The Nessus lab successfully identified numerous critical and high‑risk vulnerabilities in the target environment. The assessment demonstrates how automated vulnerability scanning can:

* Detect exploitable weaknesses
* Prioritize remediation
* Improve system hardening
* Support penetration testing workflows

This project reflects practical vulnerability assessment skills aligned with SOC / VAPT roles.

---

## 👨‍💻 Author

**Name:** Umang Patel
**Role:** Cybersecurity Student / VAPT Enthusiast
**Tools:** Kali Linux, Nessus, Metasploit, Burp Suite

---

## 📚 Learning Outcomes

* Nessus installation & configuration
* Network vulnerability scanning
* CVSS severity analysis
* Linux security patching
* Vulnerability remediation planning
* Security reporting

---

