# NETWORKWALKS-EMMANUEL-V083-WK2-FOOTPRINTING-RECONNAISSANCE-ATTACKS-WITH-MULTIPLE-KALI-TOOLS

# NETWORKWALKS-EMMANUEL-V083-WK2-PM1-FOOTPRINTING-RECONNAISSANCE

# Footprinting & Reconnaissance Attacks with Multiple Kali Tools

## 📌 Project Overview
This repository documents a passive reconnaissance (footprinting) exercise performed against a live website using built-in Kali Linux tools. The goal is to build a full public information profile of the target — its domain owner, real IP address, hosting provider, web technologies, DNS records, and firewall presence — without ever directly touching or attacking the target.

## 🖥️ Lab Architecture
*   **Attacking Machine:** Kali Linux
*   **Target:** networkwalks.com (live website, used with permission for training purposes)
*   **Tools Used:** whois, whatweb, nslookup, curl, wafw00f, dnsrecon

## 🛠️ Tasks Performed
1. **whois networkwalks.com** – Queried the public domain registration record to find the registrar, creation/expiry dates, and name servers.
2. **whatweb networkwalks.com** – Fingerprinted the web server, CMS, plugins, frameworks, and IP address.
3. **nslookup networkwalks.com** – Resolved the domain name to its real IP address via DNS.
4. **curl -I https://networkwalks.com** – Read the HTTP response headers (server banner, cookies, redirects, hidden endpoints).
5. **wafw00f networkwalks.com** – Detected whether a Web Application Firewall (WAF) is protecting the site.
6. **dnsrecon -d networkwalks.com** – Enumerated all DNS records (NS, MX, SPF, TXT, SRV).

## 📊 Key Findings
*   **Hosting Provider:** Identified via `whois` name servers.
*   **Tech Stack:** CMS and plugin versions identified via `whatweb`, useful for matching against known CVEs.
*   **Real IP Address:** Resolved via `nslookup`.
*   **Server Fingerprint:** Web server and hidden REST API endpoints found via `curl -I`.
*   **WAF Detected:** Confirmed and identified via `wafw00f`.
*   **Full DNS Footprint:** Mail servers, SPF policy, and service records enumerated via `dnsrecon`.

## 🚀 How to Use This Lab
1. Open a terminal in Kali Linux.
2. Run each command listed under **Tasks Performed** above, replacing the target domain if testing your own authorized target.
3. Save each command's output as a text file for reporting.
4. Take a screenshot of each terminal output.

## 📸 Snapshots
*   `whois` – Domain registration details captured.
*   `whatweb` – Web technology fingerprint captured.
*   `nslookup` – DNS resolution result captured.
*   `curl` – HTTP response headers captured.
*   `wafw00f` – WAF detection result captured.
*   `dnsrecon` – Full DNS enumeration captured.




# NETWORKWALKS-EMMANUEL-V083-WK2-PM5-NETWORK-SCANNING-ZENMAP

# Network Scanning with Zenmap

## 📌 Project Overview
This repository documents a network scanning exercise using Zenmap (the official GUI front-end for Nmap) to discover live hosts on a local LAN subnet, identify their IP and MAC addresses, and visualize the network topology.

## 🖥️ Lab Architecture
*   **Tool:** Zenmap (Nmap GUI)
*   **Host OS:** Windows PC
*   **Network Subnet:** 192.168.1.0/24
*   **Scan Type:** Ping Scan (`nmap -sn 192.168.1.0/24`)

## 🛠️ Tasks Performed
1. **Install Zenmap:** Downloaded and installed Zenmap from the official Nmap website ([nmap.org/download.html](https://nmap.org/download.html)).
2. **Find Local IP/Subnet:** Ran `ipconfig` in CMD to identify the local IP address and LAN subnet.
3. **Discover Live Hosts:** Ran a Ping Scan in Zenmap against the local subnet to find all live hosts.
4. **Count Live Hosts:** Reviewed scan output to count hosts that responded.
5. **Record IP Addresses:** Listed the IP addresses of all live hosts.
6. **Record MAC Addresses:** Listed the MAC addresses of all live hosts.
7. **Export Topology:** Generated the network topology view and exported it as a PDF.

## 📊 Scan Results
*   **Command used:** `nmap -sn 192.168.1.0/24`
*   **Live hosts found:** 5 (including local PC)
*   **IP addresses:** 192.168.1.1, 192.168.1.2, 192.168.1.4, 192.168.1.9, 192.168.1.14
*   **MAC addresses:**  D4:00:68:DB:2E:18, 4C:D0:DD:C2:13:BF, C6:96:6A:82:7C:59, 16:78:60:D7:DA:B6 (local machine, via `ipconfig /all`)
*   **Topology:** Exported to PDF and saved for the final report.

## 🚀 How to Use This Lab
1. Install Zenmap from [nmap.org](https://nmap.org/download.html) on a Windows PC.
2. Open CMD and run `ipconfig` to find your local IP and subnet.
3. Open Zenmap, enter your subnet as the target, select the **Ping scan** profile, and click **Scan**.
4. Review the **Hosts** tab for live host count and IP addresses; check MAC addresses in the Nmap output.
5. Click the **Topology** tab, enable the legend, and click **Save Graphic** → select **PDF** to export.

## 📸 Snapshots
*   `nmap2` – Ping scan results showing live hosts, IPs, and MAC addresses.
*   `nmap3` – Exported network topology diagram.

## ⚖️ Disclaimer
This lab was performed strictly for educational purposes on a private, authorized local subnet. Scanning networks you do not own or have explicit permission to test is illegal.
