# Threat Intelligence Investigation Report  
## Domain Analysis Case Study

Researcher: Adekunle A Joseph  
Handle: JK_spinnn  
Threat Intelligence Tool: VirusTotal 

**Investigation Date:** 2025-07-24
---

# Executive Summary

This investigation analyzes the domain **17ebook.com** using VirusTotal threat intelligence data.

The analysis identified multiple indicators associated with malicious infrastructure including suspicious DNS behavior, communication with malware samples, and detection by several security vendors.

Evidence suggests the domain has been used in malware distribution activity and should be considered **high risk**.

Security teams should block or monitor traffic related to this domain and associated infrastructure.

---

# 1 Investigation Objective

The purpose of this investigation is to analyze the domain **17ebook.com** to determine whether it is associated with malicious infrastructure or cyber threat activity.

The analysis focuses on domain reputation, infrastructure behavior, associated malware samples, and indicators of compromise.

---

# 2 Domain Overview

The domain **17ebook.com** was analyzed using threat intelligence tools to determine its reputation and infrastructure characteristics.

**Registrar:** PDR Ltd PublicDomainRegistry.com  
**Creation Date:** 21 September 2014  
**WHOIS Privacy:** PrivacyProtect.org  
**Reputation Score:** -89  
**Detection Rate:** 12 out of 94 security engines flagged the domain as malicious

These results indicate that the domain has previously been associated with suspicious or malicious activity.

![WHOIS Lookup](threat-intelligence/17ebook-domain-investigation/screenshots/Wwhoislookup.png)

---

# Detection Engine Results

The following screenshot shows the antivirus engines that detected the domain as malicious.

![Detection Summary](threat-intelligence/17ebook-domain-investigation/screenshots/Summary%20details.png)

Several vendors including Fortinet, Sophos, and Kaspersky classified the domain as phishing or malicious infrastructure.

---

# 3 DNS Infrastructure Analysis

DNS records reveal the network infrastructure associated with the domain.

**A Record:** 208.91.196.152  

**Name Servers**

- sk.s7.ans1.ns147.klczy.com  
- sk.s7.ans2.ns147.klczy.com  

DNS infrastructure analysis is important for identifying relationships between domains that share malicious hosting environments.

---

# DNS Records Evidence

![DNS Records](threat-intelligence/17ebook-domain-investigation/screenshots/dNS.png)

---

# 4 HTTPS Certificate Analysis

The domain uses a valid HTTPS certificate issued by ZeroSSL.

**Certificate Issuer:** ZeroSSL ECC Domain Secure Site CA  

**Certificate Validity**

Not Before: 09 July 2025  
Not After: 07 October 2025  

**Public Key Algorithm:** Elliptic Curve Cryptography using secp384r1  

Although HTTPS encryption is present, attackers often use legitimate SSL certificates to make malicious websites appear trustworthy.

**JARM Fingerprint**

1dd40d40d00040d00042d43d000000831b6af40378e2dd35eeac4e9311926e

![HTTPS Certificate](threat-intelligence/17ebook-domain-investigation/screenshots/Http-certificate.png)

---

# 5 Passive DNS Historical Analysis

Passive DNS analysis shows historical IP addresses associated with the domain.

Examples include

208.91.196.127  
199.59.243.226  
199.59.243.225  
185.53.177.14  
45.33.20.235  
173.255.194.134  

Frequent infrastructure changes can indicate attempts to evade detection or move malicious infrastructure between hosting providers.

---

# Passive DNS Timeline

![Passive DNS](threat-intelligence/17ebook-domain-investigation/screenshots/Whoislookup.png)

---

# 6 Subdomain Infrastructure

Threat intelligence analysis identified more than eighty subdomains associated with the domain.

Examples include

pay.17ebook.com  
2b8be.17ebook.com  
60b73.17ebook.com  
8fa1d.17ebook.com  
48c7e.17ebook.com  

Many of these subdomains appear randomly generated. Random subdomain patterns are often associated with automated malicious infrastructure or malware command and control systems.

![Subdomains](threat-intelligence/17ebook-domain-investigation/screenshots/subdomian.png)

---

# 7 Malware Communication Analysis

Threat intelligence results show several malicious files communicating with the domain infrastructure.

Examples include

- zetvbdsius.exe  
- turkeybrain.bat  
- DielnHell.exe  
- Restart.exe  
- spnSetupFree.exe  

Some of these files were detected by more than thirty antivirus engines. These files include executable malware, batch scripts, and malicious scripts.

---

# Communicating Malware Files

![Malware Infrastructure](threat-intelligence/17ebook-domain-investigation/screenshots/infrasturre1.png)

---

# 8 Threat Intelligence Graph

Threat intelligence graph analysis reveals relationships between the domain, associated malware files, and infrastructure components.

This visualization helps analysts identify links between malicious infrastructure and cyber campaigns.

---

# Infrastructure Relationship Graph

![Threat Graph](threat-intelligence/17ebook-domain-investigation/screenshots/graphy.png)

---

# 9 Indicators of Compromise

| Type | Indicator |
|-----|-----------|
| Domain | 17ebook.com |
| IP Address | 208.91.196.127 |
| IP Address | 208.91.196.152 |
| IP Address | 199.59.243.225 |
| IP Address | 199.59.243.226 |
| Malware File | zetvbdsius.exe |
| Malware File | turkeybrain.bat |
| Malware File | DielnHell.exe |
| Malware File | Restart.exe |

These indicators can be used by security teams to block or monitor suspicious activity.

---

# Defensive Recommendations

Organizations should consider implementing the following defensive actions

• Block the domain **17ebook.com** at DNS or firewall level  
• Monitor network logs for connections to identified IP addresses  
• Add related malware signatures to endpoint detection tools  
• Investigate hosts that previously communicated with this infrastructure  

These actions help reduce exposure to potential malware campaigns associated with the domain.

---

# 10 Risk Assessment

The investigation reveals several characteristics commonly associated with malicious infrastructure

- Use of WHOIS privacy protection  
- Association with malicious files  
- Presence of suspicious subdomains  
- Multiple antivirus detections  
- Frequent IP address changes  

These indicators suggest the domain has been involved in malicious cyber activity.

---

# 11 Conclusion

The investigation of the domain **17ebook.com** shows strong evidence linking the infrastructure to malware distribution and suspicious activity.

Threat intelligence results from VirusTotal revealed connections between the domain and several malicious files as well as suspicious subdomain infrastructure.

Organizations should treat the domain as high risk and monitor or block network communication associated with it.
