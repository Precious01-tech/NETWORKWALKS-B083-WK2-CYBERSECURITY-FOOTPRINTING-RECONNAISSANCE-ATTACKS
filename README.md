# Week 2 – Footprinting & Reconnaissance Attacks

## Project Overview
This repository documents practical passive footprinting, reconnaissance, and Open-Source Intelligence (OSINT) exercises conducted during Week 2 of the NetworkWalks Cybersecurity Internship (Batch B083). The objective is to gather domain, server, network, and publicly exposed infrastructure data using Kali Linux tools and Google Hacking Database (GHDB) techniques.

---

## Module 1 (W2-PM1) — Reconnaissance with Multiple Kali Tools

### Task 1 – Query Domain Registration Details (whois)

#### Command
bash
whois networkwalks.com

Purpose & Analysis

Queried public domain registration records to identify domain ownership, registrar details, registration/expiration dates, and authoritative name servers without probing the host directly.

Evidence

<img width="908" height="594" alt="WA_1789751557999" src="https://github.com/user-attachments/assets/4a3aa28e-5ac2-4616-8931-030a5b630217" />



Task 2 – Fingerprint Web Technologies (whatweb)

Command

whatweb networkwalks.com

Purpose & Analysis

Analyzed web technology stacks to uncover underlying server software, Content Management Systems (CMS), scripting languages, IP addresses, and active HTTP headers.

Evidence

<img width="1353" height="228" alt="WA_1789761425917" src="https://github.com/user-attachments/assets/15c5dab8-329d-4846-9ac4-9eed0a675172" />




Task 3 – Resolve Domain IP Address (nslookup)

Command

nslookup networkwalks.com

Purpose & Analysis

Queried DNS servers to resolve the domain name to its corresponding public IPv4 address.

Evidence

<img width="396" height="150" alt="WA_1789761787667" src="https://github.com/user-attachments/assets/5aa2dfa4-c84d-41e7-bece-9662e18e3fc4" />




Task 4 – Read HTTP Response Headers (cURL)

Command

curl -I [https://networkwalks.com](https://networkwalks.com)

Purpose & Analysis

Fetched web server HTTP response headers using the -I flag to check server banners, status codes, and security response headers.

Evidence

<img width="1365" height="269" alt="WA_1789762139818" src="https://github.com/user-attachments/assets/1efb2a3c-4520-426b-9890-d75c7d614838" />


Task 5 – Detect Web Application Firewall (wafw0of)

Command

wafw00f [https://networkwalks.com](https://networkwalks.com)

Purpose & Analysis

Tested the target domain for active Web Application Firewalls (WAF) or request-filtering solutions protecting the application layer.

Evidence

<img width="671" height="451" alt="wafw00f update" src="https://github.com/user-attachments/assets/175c9ea7-1174-4b2d-a4dd-2cfcfa7c5008" />



Task 6 – Enumerate DNS Records (dnsrecon)

Command

dnsrecon -d networkwalks.com

Purpose & Analysis

Enumerated authoritative name servers, mail exchange (MX) servers, Start of Authority (SOA) details, and TXT/SPF records across public DNS infrastructure.

Evidence

<img width="1131" height="420" alt="WA_1789763033893" src="https://github.com/user-attachments/assets/e3ba7175-5fa5-4cc3-ad1f-8c59b1aefae1" />




Module 2 (W2-PM2) — Reconnaissance with GHDB (Google Dorks)

Task 1 – Live Vulnerable Security Camera Links

Objective

Locate publicly exposed security camera feeds accessible via search engine indexing using targeted Google Dorks.


Findings & Dorks

| No. | Exposed Link / Endpoint | Relevant Dork |
|-----|--------------------------|----------------|
| 1 | http://122.116.41.8:8080/ | intitle:"webcamXP 5" |
| 2 | http://\<IP_ADDRESS\>:\<PORT\>/ | inurl:view/index.shtml |
| 3 | http://\<IP_ADDRESS\>:\<PORT\>/ | intitle:"Live View / - AXIS" |
| 4 | http://\<IP_ADDRESS\>:\<PORT\>/ | inurl:ViewerFrame?Mode= |
| 5 | http://\<IP_ADDRESS\>:\<PORT\>/ | intitle:"Network Camera" |
| 6 | http://\<IP_ADDRESS\>:\<PORT\>/ | inurl:axis-cgi/mjpg |
| 7 | http://\<IP_ADDRESS\>:\<PORT\>/ | intitle:"Toshiba Network Camera" |
| 8 | http://\<IP_ADDRESS\>:\<PORT\>/ | inurl:"/view/view.shtml" |
| 9 | http://\<IP_ADDRESS\>:\<PORT\>/ | intitle:"iNetCam" |
| 10 | http://\<IP_ADDRESS\>:\<PORT\>/ | inurl:view/view.shtml?videos= |


Evidence

<img width="790" height="574" alt="Screenshot 2026-09-17 010258" src="https://github.com/user-attachments/assets/63d514e9-1049-4437-8389-6f26392bea64" />


Module 4 (W2-PM4) — Reconnaissance with theHarvester


Task 1 – Gather Target Emails & Subdomains via Baidu

Command

theHarvester -d microsoft.com -l 1000 -b baidu

Purpose & Analysis

Searched public index data via Baidu with a maximum limit of 1000 results to collect corporate email addresses and subdomains belonging to microsoft.com.

Evidence

<img width="565" height="592" alt="theHarvester-Baidu" src="https://github.com/user-attachments/assets/2d8779fb-d9ba-433c-a76a-b3820510bd53" />


Task 2 – Gather Target Emails & Subdomains via All Sources

Command

theHarvester -d microsoft.com -l 50 -b all

Purpose & Analysis

Executed passive footprinting across all available search engines and public databases with a result limit of 50 to aggregate target metadata.


Summary of Tools & Techniques

| Module | Activity / Tool | Primary Function | Target Scope |
|--------|------------------|-------------------|----------------|
| W2-PM1 | whois | Domain ownership & registration | networkwalks.com |
| W2-PM1 | whatweb | Web technology fingerprinting | networkwalks.com |
| W2-PM1 | nslookup | Domain-to-IP DNS resolution | networkwalks.com |
| W2-PM1 | curl | HTTP header retrieval | networkwalks.com |
| W2-PM1 | wafw00f | Web Application Firewall detection | networkwalks.com |
| W2-PM1 | dnsrecon | Comprehensive DNS enumeration | networkwalks.com |
| W2-PM2 | GHDB (Google Dorks) | Search engine OSINT indexing | Public Web |
| W2-PM4 | theHarvester | Email & subdomain harvesting | 



Security & Ethical Considerations
All footprinting activities were strictly passive and non-intrusive, conducted in compliance with NetworkWalks internship safety guidelines and authorized educational scope. No active exploitation or unauthorized testing was performed.


👤 Author

Name: Kehinde Precious Akinyami

Role: Cybersecurity Student / Intern (Batch B083)

Program: NetworkWalks Cybersecurity Internship

LinkedIn:** [Kehinde Precious Akinyami]

* **GitHub:** [Precious01-tech](https://github.com/Precious01-tech)
* 
