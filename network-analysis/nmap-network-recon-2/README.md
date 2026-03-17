 ## Technical Cyber Security Report – Network Analysis Using Nmap  

---

## 👤 Researcher Details  
**Name:** Adekunle A. Joseph 
**Handler:** JK_SPINN

---

## 📄 Report Information  
**Role:** Cyber Security Analyst  
**Date:** September 07, 2025  
**Stakeholder:** Vephla Uni  

---

## 📑 Report Outline  
- Executive Summary  
- Background and Objectives  
- Methodology  
- Tool Configuration  
- Execution Process  
- Monitoring and Analysis  
- Findings and Analysis  
- Indicators of Compromise (IOCs)  
- Service and Version Detection  
- Risk and Impact Assessment  
- Recommendations  
- Immediate Remediation Actions  
- Long Term Mitigation  
- Conclusion  
- Appendix  

---

## 1️⃣ Executive Summary  

### Overview  
This report presents the results of a network scan conducted using Nmap on the host system with IP address:

```
192.168.146.128
```

An additional verification scan was also performed on:

```
192.168.156.128
```

The purpose of this analysis was to assess the system’s exposure to potential network based attacks by identifying open ports, running services, and possible vulnerabilities.

---

### Key Findings  
- The host **192.168.146.128** is active and reachable  
- All 1000 commonly scanned TCP ports are **closed**  
- No services are exposed on the network  
- The host **192.168.156.128** is also active  
![Findings](network-analysis/nmap-network-recon-2/screenshots/1.png)
---

## 2️⃣ Background and Objectives  

### Project Context  
This task focuses on evaluating the security posture of a system using network scanning techniques.

---

### Objectives  
- Confirm whether the host is live  
- Identify open ports  
- Detect running services  
- Determine service versions  
- Evaluate potential security risks  

---

## 3️⃣ Methodology  

### 3.1 Tool Configuration  

**Tool Used:** Nmap (Network Mapper)  
![nmapversion](network-analysis/nmap-network-recon-2/screenshots/2.png)

---

### Scan Options Used  

| Option | Description |
|------|------------|
| -sL | List targets without scanning |
| -sn | Host discovery only |
| -sC | Default script scan |
| -sV | Service version detection |
| -vv | Verbose output |
| -Pn | Skip ping and assume host is up |

---

### 3.2 Execution Process  

The following commands were executed:

#### Target Listing
```bash
nmap -sL 192.168.146.128
```
![Target Listing](network-analysis/nmap-network-recon-2/screenshots/4.png)

#### Host Discovery
```bash
nmap -sn 192.168.146.128
```
![Host Discovery](network-analysis/nmap-network-recon-2/screenshots/5.png)

#### Service and Version Detection
```bash
nmap -sC -sV -vv 192.168.146.128
```
![Findings](network-analysis/nmap-network-recon-2/screenshots/6.png)

#### Forced Scan (Skip Ping)
```bash
nmap -Pn -sC -sV 192.168.146.128
```
![Force Scan](network-analysis/nmap-network-recon-2/screenshots/7.png)

---

### 3.3 Monitoring and Analysis  

#### System Monitoring  
- Nmap output logs were analyzed  
- Focus was placed on:
  - Port states  
  - Service detection  
  - Version information  

---

#### Network Monitoring  
- No incoming or outgoing connections detected  
- No active services responding on scanned ports  
![Findings](network-analysis/nmap-network-recon-2/screenshots/8.png)
---

## 4️⃣ Findings and Analysis  

### 4.1 Indicators of Compromise (IOCs)  

| Indicator | Value | Description |
|----------|------|------------|
| Host Status | 192.168.146.128 | Alive |
| Host Status | 192.168.156.128 | Alive |
| Open Ports | None | All ports closed |
| Suspicious Activity | None | No abnormal behavior |
![Findings](network-analysis/nmap-network-recon-2/screenshots/9.png)

---

### 4.2 Service and Version Detection  

- No services were detected  
- All scanned ports returned **closed** status  
- No version information available  
![Findings](network-analysis/nmap-network-recon-2/screenshots/10.png)
---

### 4.3 Risk and Impact Assessment  

#### Risk Level: LOW  

#### Analysis  
- No exposed services means no direct attack surface  
- System is not vulnerable to common network based attacks  
![Findings](network-analysis/nmap-network-recon-2/screenshots/11.png)
---

#### Residual Risk  
- Future services (SSH, HTTP, RDP) may introduce vulnerabilities  
- Misconfiguration can increase exposure  

---

## 5️⃣ Recommendations  

### 5.1 Immediate Remediation Actions  

- Maintain current firewall configuration  
- Keep unnecessary ports closed  
- Monitor system activity regularly  

---

### 5.2 Long Term Mitigation  

- Perform regular network scans using Nmap  
- Apply system hardening before enabling services  
- Keep operating system and software updated  
- Implement intrusion detection systems  

---

## 6️⃣ Conclusion  

### Summary  
The Nmap scan confirmed that:

- The target system is active  
- No open ports are available  
- No services are exposed  

This indicates a strong security posture at the time of testing.

---

### Next Steps  
- Maintain the current secure configuration  
- Conduct periodic security assessments  
- Monitor for any future changes in system exposure  

---

## 📎 Appendix  

Ivestigation Evidence:
        - ![screenshots](network-analysis/nmap-network-recon-2/screenshots)
        - ![video presentation](https://drive.google.com/file/d/18I1JMi48Gcwtomtsj9-7DphEmslC4mtL/view?usp=drive_link)
        ![video presentation](https://drive.google.com/file/d/1ZUFWgobjvPX-K3XQAlCxlf-TsiUaY5-D/view?usp=drive_link)
        
---

## 🧠 Notes  

- Closed ports reduce attack surface  
- No service means no direct exploitation path  
- Continuous monitoring is still required  

