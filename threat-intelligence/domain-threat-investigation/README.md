# Threat Intelligence Investigation Report
## Domain Malware Infrastructure Analysis

**Researcher:** Adekunle A Joseph  
**Handle:** JK_spinnn  
**Institution:** VEPHLA University  

**Investigation Date:** 2025-07-20

---

# Executive Summary

This investigation analyzes three suspicious domains:

- gumblar.cn  
- martuz.cn  
- beladen.net  

The analysis was conducted using VirusTotal threat intelligence tools including URL scanning, malware sandbox analysis, DNS infrastructure monitoring, and threat intelligence graph relationships.

The objective of this investigation is to determine whether these domains are associated with malware distribution, phishing campaigns, or malicious infrastructure.

Evidence collected shows historical connections to malware delivery, suspicious DNS infrastructure, and multiple indicators of compromise.

---

# Investigation Methodology

### Tools Used

- VirusTotal Threat Intelligence Platform

### Analysis Techniques

- URL multi-engine scanning  
- Passive DNS investigation  
- Malware file relationship analysis  
- Subdomain infrastructure mapping  
- Threat intelligence graph correlation  
- Historical detection monitoring

---

# Domain Investigation

## 1 Domain Analysis: gumblar.cn

### Detection Summary

- Detection Rate: 13 / 94 vendors  
- Reputation Score: -9

**Vendors Detecting:**  
alphaMountain.ai, CRDF

**Categories:**  
Malware site, Malicious infrastructure

### Evidence Screenshot

![gumblar detection](threat-intelligence/domain-threat-investigation/screenshots/gumblar.cn.png)

### Passive DNS Infrastructure

| Date | IP Address | Detection |
|-----|-----|-----|
| 2015-07-10 | 217.160.0.187 | 2/94 |
| 2012-03-21 | 91.195.240.40 | 1/94 |
| 2011-05-15 | 210.188.201.7 | 1/94 |
| 2010-03-18 | 210.188.201.7 | 0/94 |
| 2009-08-06 | 210.188.201.7 | 0/94 |

### Behavioral Analysis

- Drive-by malware download campaigns  
- Browser exploit redirections  
- Hosting of trojans and rootkits  
- JavaScript-based exploit kits

### Threat Intelligence Insight

gumblar.cn is historically linked to the **Gumblar malware campaign**, which injected malicious scripts on thousands of websites, distributing trojans and performing credential theft attacks.

---

## 2 Domain Analysis: martuz.cn

### Detection Summary

- Detection Rate: 15 / 94 vendors  
- Reputation Score: 0

**Vendors Detecting:**  
alphaMountain.ai, Antiy AVL, BitDefender, CyRadar, DrWeb, Fortinet, Kaspersky, Sophos, VIPRE, Webroot, Yandex Safebrowsing

### Evidence Screenshot

![martuz detection](threat-intelligence/domain-threat-investigation/screenshots/martuz.cn.png)

### Passive DNS Infrastructure

- 104.21.51.61  
- 172.67.222.134  
- 38.28.172.5  
- 38.28.171.8  
- 168.206.162.190  
- 164.88.18.168  
- 45.201.229.12  
- 103.224.182.210  
- 70.32.1.32  
- 170.178.168.203  

### Subdomain Infrastructure

- gumblar.martuz.cn  
- ww31.martuz.cn  
- ww6.martuz.cn  
- ww38.martuz.cn  
- zecz.martuz.cn  
- jfoh.martuz.cn  
- ljdt.martuz.cn  

### Malware File Relations

| File | Type | Detection |
|-----|-----|-----|
| laughter7.htm | HTML | 38/64 |
| toturial.exe | Executable | 16/70 |

### Behavioral Analysis

- Malware hosting infrastructure  
- Phishing activity  
- Payload delivery using executable files  
- Redirect-based infection chains

---

## 3 Domain Analysis: beladen.net

### Detection Summary

- Detection Rate: 2 / 94 vendors  
- Categories: Malicious infrastructure, Spyware and malware

### Evidence Screenshot

![beladen detection](threat-intelligence/domain-threat-investigation/screenshots/beladen.net.png)

### Passive DNS Infrastructure

| IP Address |
|-----|
| 69.172.201.217 |
| 213.247.47.190 |
| 174.137.132.28 |
| 54.72.9.51 |
| 69.43.161.167 |

### Behavioral Analysis

- Parked domain infrastructure  
- Historical malware association  
- Possible phishing infrastructure reuse

---

# Cross Domain Correlation & Comparison

## Observed Correlations

- gumblar.cn and martuz.cn are strongly linked to **active malware campaigns**  
- beladen.net is a **secondary/dormant node** but shares infrastructure with active domains  
- Subdomains show patterns of malware hosting, phishing, and redirect chains  
- Shared IP addresses indicate possible reuse of compromised servers

## Key Differences

| Domain | Activity Level | Malware / Phishing | Infrastructure Role |
|--------|----------------|-----------------|-------------------|
| gumblar.cn | High | Trojans, Rootkits, JS Exploits | Active malware campaign |
| martuz.cn | High | HTML/EXE payloads, phishing | Active malware campaign |
| beladen.net | Low | Spyware / parked domain | Dormant / secondary node |

---

# Indicators of Compromise (IoCs)

### Domains

- gumblar.cn  
- martuz.cn  
- beladen.net  

### Suspicious Subdomains

- gumblar.martuz.cn  
- ww31.martuz.cn  
- ww6.martuz.cn  
- ww38.martuz.cn  
- zecz.martuz.cn  
- jfoh.martuz.cn  
- ljdt.martuz.cn  

### Suspicious IP Addresses

217.160.0.187, 91.195.240.40, 210.188.201.7, 104.21.51.61, 172.67.222.134, 38.28.172.5, 38.28.171.8, 168.206.162.190, 164.88.18.168, 45.201.229.12, 103.224.182.210, 70.32.1.32, 170.178.168.203, 69.172.201.217, 213.247.47.190, 174.137.132.28, 54.72.9.51, 69.43.161.167  

---

# Defensive Security Measures

### Network Security

- Block malicious domains and IP addresses using firewall and DNS filtering systems  
- Add domains to DNS blocklists to prevent internal network communication  

### Endpoint Protection

- Deploy advanced endpoint detection systems capable of identifying malware payloads from these domains  
- Monitor executable downloads, DLL activity, and suspicious HTML exploit files  

### Threat Intelligence Monitoring

- Continuously monitor threat intelligence feeds to detect new infrastructure linked to these domains  

### Security Awareness

- User training to prevent phishing attacks and downloads from suspicious domains  

---

# Investigation Evidence

## Screenshots

![Investigation Evidence](threat-intelligence/domain-threat-investigation/screenshots)

## Walkthrough Video

[Investigation Walkthrough Video](https://drive.google.com/drive/folders/1xIPPe-aFZwnCZy8XmCd-4EbPnKfip8_a?usp=drive_link)

---

# Network Correlation Diagram

```mermaid
graph LR
    gumblar[gumblar.cn]
    martuz[martuz.cn]
    beladen[beladen.net]

    gumblar --> IP1[217.160.0.187]
    gumblar --> IP2[91.195.240.40]
    gumblar --> IP3[210.188.201.7]

    martuz --> IP4[104.21.51.61]
    martuz --> IP5[172.67.222.134]
    martuz --> IP6[38.28.172.5]
    martuz --> IP7[38.28.171.8]
    martuz --> IP8[168.206.162.190]

    beladen --> IP9[69.172.201.217]
    beladen --> IP10[213.247.47.190]
    beladen --> IP11[174.137.132.28]

    martuz --> Sub1[gumblar.martuz.cn]
    martuz --> Sub2[ww31.martuz.cn]
    martuz --> Sub3[ww6.martuz.cn]
    martuz --> Sub4[ww38.martuz.cn]
    martuz --> Sub5[zecz.martuz.cn]
    martuz --> Sub6[jfoh.martuz.cn]
    martuz --> Sub7[ljdt.martuz.cn]

***Conclusion***

gumblar.cn and martuz.cn demonstrate strong associations with malware distribution infrastructure

beladen.net shows weaker but notable links to suspicious activity

All three domains should be treated as potentially malicious and monitored
