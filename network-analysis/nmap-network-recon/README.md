# Network Reconnaissance Using Nmap

Researcher: Adekunle A. Joseph   
Handle: JK_SPINN 
Date: 7th of August, 2025
---

# Overview

This task demonstrates how network reconnaissance can be performed using the Nmap tool to analyze a host on a local network.

The objective of this investigation is to identify:

• Open ports  
• Running services  
• Operating system fingerprints  
• Potential security risks  

Two different systems were analyzed to compare results and understand network exposure.

---

# Tools Used

Nmap (Network Mapper)

Nmap is a widely used open source network scanning tool used for:

• Network discovery  
• Port scanning  
• Service detection  
• Operating system fingerprinting  
• Vulnerability detection

---

# Step 1 – Discovering My IP Address

The local IP address was identified using the following command.

### Windows

```
ipconfig
```

### Linux / macOS

```
ifconfig
```

### Output

IPv4 Address: **192.168.146.128**  
Subnet Mask: **255.255.255.0**  
Broadcast Address: **192.168.146.255**

This address represents the system's internal network identity on the local area network.
![IP Adress Discovery](network-analysis/nmap-network-recon/screenshots/1.png)

---

# Step 2 – Conducting the Nmap Scan

The following Nmap command was executed to perform a detailed scan.

```
nmap -sV -O -A 192.168.146.128
```

### Command Explanation

| Option | Meaning |
|------|------|
| -sV | Service version detection |
| -O | Operating system detection |
| -A | Aggressive scan |

---

# Step 3 – Scan Results

### Host Information

| Feature | Result |
|------|------|
| Host Status | Host is up |
| Network Distance | 0 hops |
| Ports Scanned | 1000 |
| Open Ports | None |
![Scan Results](network-analysis/nmap-network-recon/screenshots/2.png)
### Interpretation

All scanned ports were reported as **closed**.

This may indicate:

• No services are running on the system  
• A firewall is blocking incoming connections  
• The system is configured with minimal network exposure  

Operating system detection failed due to insufficient fingerprint data.

---

# Windows System Nmap Scan

A second scan was performed on another system.

### Target IP

172.20.10.2
![Target IP](network-analysis/nmap-network-recon/screenshots/3.png)

### Command Used

```
nmap -sV -T4 -O -A 172.20.10.2
```

### Command Options

| Option | Description |
|------|------|
| -sV | Detect service versions |
| -T4 | Faster scanning |
| -O | Operating system detection |
| -A | Aggressive scan |

---

# Scan Summary

| Feature | Result |
|------|------|
| Host Status | Host is up |
| Latency | 0.00041s |
| Network Distance | 0 hops |

---

# Open Ports and Services

| Port | State | Service | Details |
|------|------|------|------|
| 135 | Open | msrpc | Microsoft Windows RPC |
| 139 | Open | netbios-ssn | NetBIOS Session Service |
| 445 | Open | microsoft-ds | SMB File Sharing |
| 903 | Open | ssl/vmware-auth | VMware Authentication Daemon |
| 5357 | Open | http | Microsoft HTTPAPI |
| 8000 | Open | http | Splunk Web Service |
| 8089 | Open | ssl/http | Splunk Management Interface |
| 16992 | Open | http | Intel AMT Web Interface |

![Scan Summary](network-analysis/nmap-network-recon/screenshots/4.png)

---

# Service Analysis

### Splunk Services

Ports **8000** and **8089** are used by Splunk.

Example interface:

http://172.20.10.2:8000/en-US/account/login

These ports allow administrative management of the Splunk platform.

---

### Intel Active Management Technology

Port **16992** exposes the Intel AMT web interface.

Intel AMT allows remote system management and is often used in enterprise environments.

If improperly secured, attackers could gain remote access.

---

### VMware Authentication Daemon

Port **903** indicates a VMware service that may be used for remote console or virtual machine authentication.

---

# Operating System Detection

Nmap was unable to determine an exact OS match but identified characteristics consistent with **Microsoft Windows**.

Detected identifiers:

cpe:/o:microsoft:windows  
cpe:/h:intel:active_management_technology:11.8.79.3722

---

# Security Risk Analysis

| Port | Issue | Risk Level | Recommendation |
|------|------|------|------|
| 135 | RPC exposed | High | Restrict access via firewall |
| 139 | NetBIOS exposed | High | Disable if unnecessary |
| 445 | SMB exposed | High | Patch SMB vulnerabilities |
| 5357 | UPnP exposed | Medium | Disable externally |
| 8000 | Splunk interface exposed | Medium | Require authentication |
| 8089 | Splunk management port | Medium | Restrict network access |
| 16992 | Intel AMT exposed | High | Disable or secure with firewall |
| 903 | VMware service exposed | Medium | Limit trusted hosts |

---

# Vulnerability Scanning

Nmap can also detect vulnerabilities using NSE scripts.

Example command:

```
nmap -sV --script=vuln 192.168.146.128
nmap -sV --script=vuln 172.20.10.2
```
![Evidencea](network-analysis/nmap-network-recon/screenshots/5.png)

![Evidencea](network-analysis/nmap-network-recon/screenshots/6.png)

![Evidencea](network-analysis/nmap-network-recon/screenshots/7.png)

---

# Defensive Security Measures

### Network Protection

Implement firewall rules to restrict access to sensitive ports.

### Service Hardening

Disable unnecessary services such as NetBIOS or SMB if not required.

### Access Control

Restrict administrative services like Splunk and Intel AMT to trusted networks.

### Continuous Monitoring

Perform routine network scans to detect newly exposed services.

---

# Conclusion

The Nmap reconnaissance scan successfully identified active hosts and services within the network.

The first system showed a secure configuration with no open ports, while the second system exposed multiple services including SMB, Splunk, VMware authentication, and Intel AMT.

These findings highlight the importance of network reconnaissance in identifying potential attack surfaces and improving security posture.

---

# Evidence

## Scan Output Screenshots

