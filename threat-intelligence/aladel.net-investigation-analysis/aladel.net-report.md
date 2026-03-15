# Threat Intelligence Investigation Report  
## Domain Analysis Case Study

Researcher: Adekunle A Joseph  
Handle: JK_spinnn  
Threat Intelligence Tool: VirusTotal  

---

# Executive Summary

This investigation analyzes the domain **aladel.net** using threat intelligence data from VirusTotal.

Analysis of the domain revealed multiple indicators associated with suspicious activity including DNS detections, malware communication, and subdomain infrastructure linked to potentially malicious campaigns.

Threat intelligence data also shows that **aladel.net shares malware infrastructure connections with another analyzed domain, 17ebook.com**, suggesting the possibility of a shared malware distribution ecosystem.

Due to these indicators, the domain should be considered **potentially malicious infrastructure**.

---

# 1 Investigation Objective

The objective of this investigation is to analyze the domain **aladel.net** to determine whether it is associated with malicious infrastructure or cyber threat activity.

The investigation focuses on domain reputation, DNS infrastructure behavior, associated malware files, and indicators of compromise.

---

# 2 Domain Overview

The domain **aladel.net** was analyzed using VirusTotal to evaluate its reputation and infrastructure characteristics.

Registrar: Pacific Domains LLC  
Creation Date: 13 November 2014  
Detection Rate: 9 out of 94 security vendors flagged the domain as malicious  
Community Reputation Score: -121  

Security vendors detecting the domain include:

• alphaMountain.ai – Phishing  
• CRDF – Malicious  
• CyRadar – Malicious  
• Fortinet – Malware / Phishing  
• Lionic – Phishing  
• Sucuri – Phishing  
• Sophos – Phishing  
• Webroot – Malicious  
• Forcepoint ThreatSeeker – Suspicious  

These detections indicate that the domain has previously been associated with malicious or phishing related infrastructure.

![Detection Summary](threat-intelligence/aladel.net-investigation-analysis/screenshots/detection.png)

---

# WHOIS and SSL Details

The domain uses an HTTPS certificate issued by Let's Encrypt.

Certificate Issuer: Let's Encrypt R11  
Signature Algorithm: RSA  
Public Key Size: 2048 bit  

Certificate Validity

Not Before: 11 May 2025  
Not After: 09 August 2025  

Certificate Thumbprint

331c7d6ae2ed21da742ff7cc687892c1a44c8545

JARM Fingerprint

07d2ad16d00000000007d2ad07d21d7f66f33792e2b8180a8c9753b2e2087d

Although HTTPS encryption is present, malicious websites frequently use legitimate certificates to appear trustworthy.

![WHOIS Details](threat-intelligence/aladel.net-investigation-analysis/screenshots/whoisslookup.png)

![HTTPS Certificate](threat-intelligence/aladel.net-investigation-analysis/screenshots/http-cert.png)

---

# WHOIS Information

Registrant Country: United States  
Registrant City: Grandville  
Registrant Organization: The Management Group II  

Name Servers

ns1.dnsnuts.com  
ns2.dnsnuts.com  

Registrar

Pacific Domains LLC  

Registrar WHOIS Server

whois.web.com  

Domain Status

clientTransferProhibited

![WHOIS Lookup](threat-intelligence/aladel.net-investigation-analysis/screenshots/whoislookup.png)

---

# 3 DNS Infrastructure Analysis

Passive DNS data reveals multiple IP addresses historically associated with the domain infrastructure.

Examples include

185.150.189.166  
185.150.189.123  
185.150.189.124  
185.150.189.29  
74.63.219.254  
74.63.219.253  
74.63.219.250  
74.63.219.252  
162.210.196.171  
162.210.196.172  

Frequent infrastructure changes may indicate attempts to evade detection or migrate malicious services.

![DNS Infrastructure](threat-intelligence/aladel.net-investigation-analysis/screenshots/dns.png)

---

# DNS Detection Timeline

| Date | Detection | IP |
|-----|-----------|-----|
| 2025-07-20 | 1 / 94 | 185.150.189.166 |
| 2025-05-30 | 7 / 94 | 185.150.189.29 |
| 2023-12-14 | 2 / 94 | 185.150.189.123 |
| 2023-12-03 | 4 / 94 | 185.150.189.124 |

This timeline indicates intermittent detection events over time.

---

# 4 Subdomain Infrastructure

Threat intelligence analysis identified several subdomains associated with the domain.

Examples include

ww2.aladel.net  
http.aladel.net  
https.aladel.net  
admin.aladel.net  
mailgw.aladel.net  
sportsmansclub.aladel.net  
www.aladel.net  
ww3.aladel.net  

Detection results for notable subdomains

| Subdomain | Detection |
|----------|-----------|
| ww2.aladel.net | 6 / 94 |
| http.aladel.net | 5 / 94 |

Random or numerous subdomains can indicate infrastructure used for malware distribution or spam operations.

![Subdomain Evidence](threat-intelligence/aladel.net-investigation-analysis/screenshots/subdomain.png)

---

# 5 Referring Malware Files

VirusTotal analysis identified several files referencing the domain.

Examples include

FxzPndZ90gs2.exe  
rufus-3.5.bin  

Additional associated files include

Cliente Argentumania Beta v1.0.175  
Kostopoulos Web Browser.exe  
spnSetupFree.exe  
Minecraft generator v1.0.exe  
turkeybrain.bat  
Lockerz crack invite.bat  

These files include executable malware and batch scripts often associated with trojans or dropper payloads.

![Referring Files](threat-intelligence/aladel.net-investigation-analysis/screenshots/transfering-files.png)

---

# 6 Communicating Malware Files

Several malware samples were identified communicating directly with the domain infrastructure.

Examples include

zetvbdsius.exe  
FxzPndZ90gs2.exe  
rufus-3.5.bin  
Real Virus.bat  
db01a12be97bdba44292e3c7189a6723.virus  

Detection rates for some files include

FxzPndZ90gs2.exe detected by 54 / 72 engines  
zetvbdsius.exe detected by 21 / 72 engines  
rufus-3.5.bin detected by 23 / 73 engines  

The presence of communicating malware samples indicates the domain may have been used for malware hosting or command and control activity.

![Communicating Malware](threat-intelligence/aladel.net-investigation-analysis/screenshots/communicating-infra.png)

---

# 7 Threat Intelligence Graph Analysis

Threat intelligence graph analysis reveals relationships between the domain, malware samples, and infrastructure nodes.

The graph shows connections between

• malicious executable files  
• DNS infrastructure  
• potential spam distribution systems  

The infrastructure appears linked to email spam campaigns and malware dropper distribution networks.

![Threat Graph](threat-intelligence/aladel.net-investigation-analysis/screenshots/graphy.png)

---

# 8 Indicators of Compromise

| Type | Indicator |
|-----|-----------|
| Domain | aladel.net |
| IP Address | 185.150.189.29 |
| IP Address | 185.150.189.166 |
| Malware File | FxzPndZ90gs2.exe |
| Malware File | zetvbdsius.exe |
| Malware File | rufus-3.5.bin |

---

# Defensive Recommendations

Organizations should consider implementing the following defensive actions

• Block the domain **aladel.net** at DNS or firewall level  
• Monitor network logs for connections to associated IP addresses  
• Investigate endpoints that communicated with identified malware samples  
• Add malware signatures to endpoint detection and response systems  

---

# 9 Risk Assessment

The investigation identified multiple characteristics commonly associated with malicious infrastructure

• detection by several security vendors  
• association with malware samples  
• suspicious subdomain infrastructure  
• links to spam and malware distribution networks  

These indicators suggest the domain may be part of a malware delivery ecosystem or spam campaign infrastructure.

---

# 10 Conclusion

The investigation of the domain **aladel.net** reveals several indicators linking the infrastructure to suspicious activity and malware communication.

Threat intelligence data from VirusTotal shows connections between the domain and multiple malicious files as well as infrastructure used in spam distribution campaigns.

Organizations should treat the domain as potentially malicious and implement monitoring or blocking strategies to mitigate risk.
