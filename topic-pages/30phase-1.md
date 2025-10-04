## Phase 1 – Asset Inventory / Auditing

**Project:** Cybersecurity Home Lab  
**Author:** Julfri Caguiat  
**Date:** 2025-09-26  
**Objective:** Identify all assets, devices, and services in the lab to support network design.

---

### Hardware Inventory

- **Switch**
  - Cisco Catalyst 2960G – Lab physical switch for VLAN experiments

- **Virtual Router / Firewall**
  - pfSense appliance running on HP All-in-One Desktop

- **Servers**
  - Ubuntu 24.04 LTS VM (running Splunk, Snort, Nextcloud)
  - Ubuntu Headless Server VM (running Wazuh SIEM)

- **Workstations**
  - **MacBook Air Laptop (management host / Kali Linux VM host)**
    - OS: macOS Tahoe
    - Chip: Apple M1
    - Memory: 8 GB
    - Free HDD Storage: 79 GB
  - **Lenovo Laptop (Windows 11 host for Wazuh VM, Kali, Win10)**
    - OS: Windows 11 Home
    - Chip: AMD Ryzen 5
    - Graphics: 2 GB
    - RAM: 20 GB
    - Free SSD Storage: 15 GB
    - Free HDD Storage: 15 GB
  - **Inspiron 3650 Desktop (Splunk / Nextcloud host)**
    - OS: Ubuntu 24.04 LTS Desktop
    - Chip: Intel Core i5
    - Memory: 16 GB
    - Free SSD Storage: 450 GB
  - **HP All-in-One Desktop (pfSense host)**
    - OS: Windows 11 Home
    - Chip: Unknown
    - RAM: Unknown
    - Free Storage: Unknown

- **Additional Storage**
  - 2 × 1 TB HDDs (dedicated to file storage and backups)

- **External Monitor**
  - 2 × 15.6 Type-C FHD Portable Monitor (extended monitors for Lenovo and Mac devices)

- **Wireless Access Point**
  - Home Wi-Fi (isolated from lab VLANs)

---

### Software / Services

- **Nextcloud (on Ubuntu VM)** – File storage and sharing  
- **Splunk (on Ubuntu VM)** – Log management and monitoring  
- **Snort (on Ubuntu VM)** – Network intrusion detection/prevention (NIDS/NIPS)  
- **Wazuh (on Ubuntu Headless Server)** – Endpoint monitoring (SIEM/HIDS)  
- **pfSense (on HP All-in-One)** – Firewall / Router (virtualized appliance)  
- **Kali Linux VM** – Attack machine, penetration testing, and TryHackMe labs  
- **Windows 10 VM** – Endpoint with Sysmon + Wazuh agent installed  
- **Optional:** Docker/containers on Ubuntu VM for application testing  

---

### Network Inventory

- **VLAN 10**  
  - Subnet: 192.168.10.0/24  
  - Hosts: Host A / Host B  
  - Router Subinterface: 192.168.10.1  

- **VLAN 20**  
  - Subnet: 192.168.20.0/24  
  - Hosts: Host C / Host D  
  - Router Subinterface: 192.168.20.1  

- **VLAN 30**  
  - Subnet: 192.168.30.0/24  
  - Hosts: Splunk VM  
  - Router Subinterface: 192.168.30.1  

- **VLAN 40**  
  - Subnet: 192.168.40.0/24  
  - Hosts: Nextcloud VM  
  - Router Subinterface: 192.168.40.1  

- **VLAN 50 (Management / SIEM LAN)**  
  - Subnet: 192.168.50.0/24  
  - Hosts: Ubuntu Wazuh VM, management devices  
  - Router Subinterface: 192.168.50.1  

---

### Physical Device IP Assignments

- **HP All-in-One Desktop (pfSense)**
  - LAN (to lab): 192.168.50.1/24
  - Host-only (VirtualBox): 192.168.120.1/24 (for pfSense GUI access)
  - WAN: DHCP from home router

- **Cisco Catalyst 2960G**
  - Management VLAN (50): 192.168.50.2/24
  - Default Gateway: 192.168.50.1

- **Lenovo Laptop**
  - Lab Ethernet: 192.168.50.10/24
  - Host-only: 192.168.120.10/24 (for Wazuh-Dashboard Access)

- **MacBook Air**
  - Lab Ethernet: 192.168.50.20/24
  - Host-only: 192.168.120.20/24

- **Inspiron 3650**
  - Lab Ethernet: 192.168.50.30/24
  - Host-only: 192.168.120.30/24 (for Snort, Splunk, NextCloud access)

- **Host-only Network (Management Subnet)**
  - Subnet: 192.168.120.0/24
  - Purpose: Direct host ↔ VM access (pfSense GUI, Wazuh dashboard)

---

### Virtual Machine IP Assignments

- **pfSense (HP All-in-One)**
  - LAN Interface: 192.168.50.1/24 (gateway for lab VLANs)
  - Host-only Interface: 192.168.120.1/24 (management access)
  - WAN Interface: DHCP (home router)

- **Wazuh Server VM (Lenovo Laptop, Ubuntu Headless)**
  - Lab Ethernet (LAN 50): 192.168.50.50/24
  - Host-only Adapter: 192.168.120.50/24
  - Purpose: SIEM/HIDS, Wazuh manager + dashboard
  
- **Splunk Server VM (Inspiron 3650, Ubuntu Desktop)**
  - Lab Ethernet (LAN 30): 192.168.30.50/24
  - Host-only Adapter: 192.168.120.60/24
  - Purpose: Log management and SIEM correlation

- **Snort VM (Inspiron 3650, Ubuntu 24.04 LTS)**
  - Lab Ethernet (LAN 30): 192.168.30.51/24
  - Host-only Adapter: 192.168.120.61/24
  - Purpose: Intrusion Detection/Prevention (NIDS/NIPS)

- **Nextcloud VM ( Inspiron 3650, Ubuntu 24.04 LTS)**
  - Lab Ethernet (LAN 40): 192.168.40.50/24
  - Host-only Adapter: 192.168.120.70/24
  - Purpose: File storage and sharing

- **Windows 10 VM (Lenovo Laptop)**
  - Lab Ethernet (LAN 50): 192.168.50.60/24
  - Host-only Adapter: 192.168.120.80/24
  - Purpose: Endpoint with Sysmon + Wazuh agent

- **Kali Linux VM (MacBook Air)**
  - Lab Ethernet (LAN 20): 192.168.20.50/24
  - Host-only Adapter: 192.168.120.90/24
  - Purpose: Attack machine, TryHackMe labs

<!--
Virtual Machine IP Assignments
	•	pfSense VM (on HP All-in-One, VirtualBox)
	•	LAN Interface: 192.168.50.1/24 (gateway for lab VLANs)
	•	Host-only Interface: 192.168.120.1/24 (management access)
	•	WAN Interface: DHCP (home router)

	•	Wazuh Server VM (Lenovo Laptop, Ubuntu Headless)
	•	Lab Ethernet (LAN 50): 192.168.50.50/24
	•	Host-only Adapter: 192.168.120.50/24
	•	Purpose: SIEM/HIDS, Wazuh manager + dashboard

	•	Splunk Server VM (Inspiron 3650, Ubuntu Desktop)
	•	Lab Ethernet (LAN 30): 192.168.30.50/24
	•	Host-only Adapter: 192.168.120.60/24
	•	Purpose: Log management and SIEM correlation

	•	Snort VM (Ubuntu 24.04 LTS)
	•	Lab Ethernet (LAN 30): 192.168.30.51/24
	•	Host-only Adapter: 192.168.120.61/24
	•	Purpose: Intrusion Detection/Prevention (NIDS/NIPS)

	•	Nextcloud VM (Ubuntu 24.04 LTS, Inspiron 3650)
	•	Lab Ethernet (LAN 40): 192.168.40.50/24
	•	Host-only Adapter: 192.168.120.70/24
	•	Purpose: File storage and sharing

	•	Windows 10 VM (Lenovo Laptop)
	•	Lab Ethernet (LAN 50): 192.168.50.60/24
	•	Host-only Adapter: 192.168.120.80/24
	•	Purpose: Endpoint with Sysmon + Wazuh agent

	•	Kali Linux VM (MacBook Air)
	•	Lab Ethernet (LAN 20): 192.168.20.50/24
	•	Host-only Adapter: 192.168.120.90/24
	•	Purpose: Attack machine, TryHackMe labs
-->
---

### Observations / Notes

- Splunk and Nextcloud should remain isolated on separate VLANs for security.  
- Cisco Catalyst 2960G supports trunking for lab VLAN experiments.  
- pfSense will handle inter-VLAN routing via 802.1Q subinterfaces (dot1q encapsulation).  
- Switch management should be placed on VLAN 50 with IP 192.168.50.2.  
- Wi-Fi stays on home router; lab Internet access is routed through pfSense WAN.  
- Host-only 192.168.120.0/24 provides a safe management channel to pfSense and Wazuh without touching lab VLANs.  

---

### Next Steps

**Phase 2 – Risk Assessment & Requirements**  
- Identify potential attack surfaces in the lab  
- Assess security requirements for each service (Splunk, Nextcloud, Wazuh, pfSense)  
- Define isolation, segmentation, and monitoring strategy per VLAN  
- Document patch management and backup requirements  

---
[👉 Phase 2: (Risk Assessment)]

[🔙 Back to Home](../index.md)