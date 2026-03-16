# Threat Intelligence Investigation Report  
## Domain Analysis Case Study

Researcher: Adekunle A Joseph  
Handle: JK_spinnn  
Threat Intelligence Tool: VirusTotal  

**Investigation Date:** 2025-07-24

---

# Executive Summary

This investigation analyzes the domain **clicnews.com** using threat intelligence data from VirusTotal.

Analysis shows that the domain has been flagged by security vendors and exhibits indicators of potential malicious activity, including subdomains with low detection rates and historical DNS patterns linked to suspicious infrastructure.

Due to these findings, the domain should be considered **potentially risky** and monitored for any connections to malware or phishing activity.

---

# 1 Investigation Objective

The objective is to determine whether **clicnews.com** is associated with malicious infrastructure, phishing, or malware campaigns. The analysis focuses on domain reputation, DNS infrastructure, subdomains, and indicators of compromise.

---

# 2 Domain Overview

The domain **clicnews.com** was analyzed for reputation and technical characteristics.

- **Registrar:** Megazone Corp., dba HOSTING.KR  
- **Creation Date:** 5 March 2011  
- **Community Reputation Score:** -691  
- **Detection Rate:** 1 / 94 security vendors flagged this domain  

Popularity ranks:

- Alexa: 196158  

These metrics indicate low popularity but presence in threat intelligence datasets.  
![Detection Summary](threat-intelligence/clicnews-domain-investigation/screenshots/Detection.png)

---

# WHOIS and SSL Details

- **Registrant Country:** South Korea  
- **Registrant City:** Seoul  
- **Admin Organization:** PARK TAE WON  
- **Admin Email:** 7df2ed162494053as@gmail.com  

**Name Servers:**  
- NS1.AFTERNIC.COM  
- NS2.AFTERNIC.COM  

**HTTPS Certificate:**  
- Signature Algorithm: sha256RSA  
- X509 Thumbprint: 3fd3fd20d00000000043d3fd3fd43d9d4f83ac87494648a3bed4ab670795cd  
- Extended Key Usage & CA information present  

Even though the domain uses HTTPS, malicious actors often use valid certificates to appear trustworthy.  
![WHOIS Details](threat-intelligence/clicnews-domain-investigation/screenshots/whoislookup.png)
![HTTPS Certificate](threat-intelligence/clicnews-domain-investigation/screenshots/http-cert.png)

---

# 3 Passive DNS Historical Analysis

Historical IPs associated with the domain:

76.223.54.146  
13.248.169.48  
64.190.63.111  
64.190.62.111  
127.0.0.1  
91.195.241.137  
91.195.241.136  
35.186.238.101  
91.195.240.126  
72.52.4.119  

These IPs indicate a mix of hosting providers and intermittent detection events over time.  
![DNS Infrastructure](threat-intelligence/clicnews-domain-investigation/screenshots/passive-dns.png)

---

# DNS Detection Timeline

| Date | Detection | IP |
|-----|-----------|-----|
| 2023-06-05 | 7 / 94 | 76.223.54.146 |
| 2023-06-05 | 7 / 94 | 13.248.169.48 |
| 2022-03-24 | 5 / 94 | 64.190.63.111 |
| 2021-03-26 | 4 / 94 | 64.190.62.111 |

---

# 4 Subdomain Infrastructure

Several subdomains were identified:

- 2a.clicnews.com  
- seed.clicnews.com  
- mail2.clicnews.com  
- spam.clicnews.com  
- com.clicnews.com  
- mail9.clicnews.com  
- srv.clicnews.com  
- box.clicnews.com  
- mail12.clicnews.com  
- mailbox.clicnews.com  

Detection results for notable subdomains:

| Subdomain | Detection |
|-----------|-----------|
| 2a.clicnews.com | 1 / 94 |
| seed.clicnews.com | 0 / 94 |

Random or multiple subdomains can indicate infrastructure used for phishing, spam, or malware delivery.  
![Subdomain Evidence](threat-intelligence/clicnews-domain-investigation/screenshots/subdomain.png)

---

# 5 Indicators of Compromise (IoCs)

| Type | Indicator |
|------|-----------|
| Domain | clicnews.com |
| Subdomain | 2a.clicnews.com |
| Subdomain | seed.clicnews.com |
| IP Address | 76.223.54.146 |
| IP Address | 13.248.169.48 |

These IoCs can be used by security teams to block or monitor suspicious traffic.

---

# 6 Defensive Recommendations

Organizations should consider implementing the following actions:

- Block the domain **clicnews.com** at DNS or firewall level  
- Monitor network traffic for connections to identified IP addresses  
- Investigate any endpoints that communicate with suspicious subdomains  
- Include the domain in endpoint detection and response (EDR) systems for monitoring  
- Regularly update threat intelligence feeds to detect new associated malware or subdomains  

These measures help reduce exposure to potential malware or phishing campaigns.

---

# 7 Risk Assessment

The investigation identifies the following risk factors:

- Detection by security vendors  
- Low community reputation score  
- Multiple subdomains with suspicious IPs  
- Historical DNS patterns linked to phishing/malware  

These factors indicate that **clicnews.com may be part of risky infrastructure**, requiring monitoring or defensive action.

---

# 8 Conclusion

The domain **clicnews.com** exhibits characteristics of potentially risky infrastructure, with historical detections and suspicious subdomain patterns.

Security teams should treat it as a **high-risk domain**, applying defensive measures such as DNS blocking, network monitoring, and endpoint awareness to prevent possible compromise.
