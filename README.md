# richirabor-NetworkWalks-B083-Wk2-PM1-PM4-Cybersecurity-Lab-SETUP
Implementation of the Cybersecurity various tasks on Foot printing &amp; Reconnaissance and Scanning using Zenmap

| Pentester Name | Irabor Richard |
| ------- | ---------------- |
| Modules completed	| W2-PM1 (Multiple Kali Tools) W2-PM4 (theHarvester) W2-PM5 (Zenmap Scanning)   |
| Client/Target	| 1. Networkwalks (secured written permission already) 2. My own local LAN Network |
| Phases covered | Phase 1: Reconnaissance & Footprinting Phase 2: Scanning & Network Discovery Phase 3-5: In Progress |

# 1. Liability Disclaimer
I carried out these tasks and activities only on systems & devices where I had secured written permission, or on devices/systems I own. All materials are for educational and research purposes only. Do not use anything from here to break the law. The instructor, the authors and Networkwalks are not responsible for what you do with this knowledge. Every action taken is your own responsibility. Misuse can lead to criminal charges, heavy fines, loss of your job, and a permanent record. In most countries, unauthorised access is a crime even when nothing is damaged.

# 2. Introduction
This report covers footprinting the networkwalks.com domain using multiple Kali Linux tools (W2-PM1), theHarvester and scanning my own local network with Zenmap (W2-PM5). One module covers the footprinting phase and the other covers the scanning phase, so together they show how an attacker moves from gathering public information to mapping live hosts on a network. It is the Week 2 part of my ongoing internship program at Networkwalks.
All commands were run in Kali Linux (footprinting) and on a Windows PC with Zenmap installed (scanning). Every step below includes the exact command used, the result I observed, a screenshot as evidence, and a short note on why the finding matters from an attacker's point of view.


# 3. Tools Used
The table below lists each tool used in this report and its purpose.

|Tools | Purpose |
| ------- | ---------------- |
| Kali Linux & Windows	| Operating systems used for reconnaissance activities      |
| WHOIS	 | Find domain registration details (owner, dates, name servers). |
| whatweb	 | Fingerprint web technologies (server, CMS, plugins, IP).  |
| nslookup	 | Resolve the domain name to its IP address using DNS. |
| curl -I	 | Read the HTTP response headers of the website. |
| wafw00f	 | Detect whether a Web Application Firewall protects the site. |
| dnsrecon	 | Enumerate all DNS records (NS, MX, SPF, TXT, SRV). |
| theHarvester	 | Collect emails, sub-domians and hosts from dozens of public sources |
| Zenmap (Nmap GUI)	 | Scan the local subnet to find live hosts, IPs and MAC addresses. |
| Windows CMD	 | Local IP and MAC address identification |

# 4. Activities Performed
## 4.1 Footprinting & Reconnaissance

I performed reconnaissance against the networkwalks.com domain using six Kali Linux tools: WHOIS, WhatWeb, Nslookup, Curl, Wafw00f and DNSRecon. Each tool was used to collect a different type of information about the target.
First, I used WHOIS to obtain publicly available domain registration information and identify the domain’s name servers. The results provided information about the domain registration and hosting infrastructure.
I then used WhatWeb to identify technologies used by the website. The results identified WordPress 7.0.4 and WP Download Manager 3.3.58, along with other information exposed by the website.
Using Nslookup, I resolved the domain name to its IP address. The provided result identified 192.232.216.135.
I used Curl with the -I option to inspect the HTTP response headers. This provided additional information about the web application and exposed the WordPress REST API endpoint /wp-json/.
I used Wafw00f to determine whether a Web Application Firewall was protecting the website. The result identified ModSecurity (SpiderLabs).
Next, I used DNSRecon to enumerate DNS records. The results provided information relating to name servers, mail servers, SPF/TXT records, service records and DNS software information.
In conclusion, I implemented the theHarvester to collects various emails, sub-domains and hosts from different public sources without touching their target. The results pulled up the API of some of the public sources and listed a large query of sub-domains. 

## 4.2 Network Scanning with Zenmap
For this last activity, I performed network discovery on my local network using Zenmap. The practical required me to identify my local IP address and subnet, discover live hosts, identify their IP and MAC addresses, and generate a network topology.
I first used the Windows ipconfig command to identify my local IP address and LAN subnet. I then entered the subnet into Zenmap and selected Ping Scan to identify active hosts.
The example results provided in the practical identified five live hosts:
•	192.168.100.1
•	192.168.100.5
•	192.168.100.11
•	192.168.100.22
•	192.168.100.31
The example results also included only four MAC addresses.
After completing the scan, I opened the Topology section in Zenmap, enabled the legend and saved the network topology in PDF format as required by the practical task.
Note: The actual subnet, number of hosts and addresses should be replaced with the results from my own network when submitting the report.

# 5. Evidences Collected
## Whois 

<p align="center">
  <img src="Whois Pen.png"
      alt="Whois"
      width="800">
</p>

## Whatweb

<p align="center">
  <img src="whatweb Pen.png"
      alt="Whatweb"
      width="800">
</p>
