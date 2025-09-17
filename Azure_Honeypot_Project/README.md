# Project 3 – Azure Honeypot

## 📌 Overview
This project demonstrates the setup of a honeypot in Microsoft Azure to collect and analyze real-world attack attempts against a virtual machine (VM).  
The purpose is to practice data collection (Event Logs, NSG flow logs, packet captures), enrichment with GeoIP data, and visualization of attack sources using Microsoft Sentinel.

## 🛠️ Method
1. Created an Azure subscription and a dedicated resource group.  
2. Deployed a Windows VM and configured the Network Security Group (NSG) to allow inbound traffic (RDP/other).  
3. Adjusted Windows Firewall for the lab environment.  
4. Generated failed login attempts (Event ID 4625) to validate log collection.  
5. Created a Log Analytics Workspace (LAW) and connected Microsoft Sentinel.  
6. Imported a GeoIP watchlist (CSV) to Sentinel to enrich IP addresses with geographic data.  
7. Built a Sentinel Workbook (attack map) to visualize login attempts on a world map.

## 📂 Project Structure
- **screenshots/**  
  Screenshots from the Azure portal and Sentinel (VM creation, NSG rules, Event Viewer, LAW, Sentinel connector, watchlist import, KQL queries, attack map).

- **logs/**  
  Raw data and exports:  
  - `nsg_flowlog.json` – Example NSG flow log.  
  - `securityevents_4625.csv` – Exported failed login events.  
  - `geoip-summarized.csv` – GeoIP dataset used for enrichment.  

- **scripts/**  
  Commands and queries used:  
  - `az_commands.txt` – Azure CLI commands for setup.  
  - `kql_queries.txt` – KQL queries (failed login, aggregation, ipv4_lookup).  
  - `map.json` – JSON definition for the attack map workbook.  

- **figures/**  
  Final visualizations:  
  - `geolocation_map.png` – World map of login attempts.  
  - `top10_ips.png` – Bar chart of top attacker IPs.  
  - `timeline_attempts.png` – Time series of attack attempts.  

## 🔎 Results (to be filled in)
- Total number of attempts: **(fill in)**  
- Most common usernames: **(fill in)**  
- Most targeted ports: **(fill in)**  
- Top 5 countries/IP sources: **(fill in)**  

## ⚖️ Ethics and Privacy
- Data was collected in an isolated lab environment using resources I own.  
- Raw data that may contain personally identifiable information (PII), such as IP addresses, will be anonymized before sharing.  
- PCAP/JSON files containing sensitive data should not be publicly shared without anonymization.  

## 💰 Cost Management
- Used Azure free-tier where possible.  
- VM was deallocated/deleted after testing to minimize cost.  
- Estimated and actual costs can be documented separately if needed.  

## 🧭 Reproduction Guide (short)
1. Use `scripts/az_commands.txt` for resource group, VM, NSG, LAW setup and flow log activation.  
2. Use `scripts/kql_queries.txt` for basic queries (EventID==4625, ipv4_lookup with watchlist).  
3. Place `geoip-summarized.csv` in `logs/` and import it as a Watchlist in Sentinel.  
4. Import `scripts/map.json` into Sentinel Workbook editor to recreate the attack map.  

---

**Note:** This README is a template. Insert your own screenshots, data, and findings into the respective folders.
