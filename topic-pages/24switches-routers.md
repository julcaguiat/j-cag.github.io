## 🧩 Switches vs Routers — Study Priority & Functionality Guide

This guide categorizes core, intermediate, and advanced functionalities of **Switches** and **Routers**, prioritized for CCNA study and hands-on practice.

---

### 🧱 1. Core Layer (Foundation — Study These First)

| **Functionality** | **Used By** | **Purpose** | **CLI Example (Cisco IOS)** |
|--------------------|-------------|--------------|-----------------------------|
| **Static IP Addressing (Management IP)** | **Switches** | Assigns an IP to a VLAN interface for remote access (SSH/Telnet). | Switch(config)# interface vlan 1<br>Switch(config-if)# ip address 192.168.1.2 255.255.255.0<br>Switch(config-if)# no shutdown<br>Switch(config)# ip default-gateway 192.168.1.1 |
| **Static Routing** | **Routers** | Defines manual routes to specific networks. | Router(config)# ip route 192.168.2.0 255.255.255.0 10.0.0.2 |
| **Dynamic Routing (RIP / OSPF)** | **Routers** | Learns and updates routes automatically. | Router(config)# router ospf 1<br>Router(config-router)# network 10.0.0.0 0.0.0.255 area 0 |
| **VLAN (Virtual LAN)** | **Switches** | Segments a LAN into smaller broadcast domains. | Switch(config)# vlan 10<br>Switch(config-vlan)# name HR<br>Switch(config)# interface fa0/1<br>Switch(config-if)# switchport access vlan 10 |
| **Trunking (802.1Q)** | **Switches** | Carries multiple VLANs over a single link. | Switch(config)# interface fa0/24<br>Switch(config-if)# switchport mode trunk<br>Switch(config-if)# switchport trunk allowed vlan 10,20 |

---

### 🔐 2. Intermediate Layer (Network Design & Control)

| **Functionality** | **Used By** | **Purpose** | **CLI Example (Cisco IOS)** |
|--------------------|-------------|--------------|-----------------------------|
| **Inter-VLAN Routing (SVI)** | **Multilayer Switches** | Enables communication between VLANs without a router. | Switch(config)# interface vlan 10<br>Switch(config-if)# ip address 192.168.10.1 255.255.255.0<br>Switch(config-if)# no shutdown |
| **Subinterfaces** | **Routers** | Allows routing multiple VLANs via one physical interface. | Router(config)# interface g0/0.10<br>Router(config-subif)# encapsulation dot1Q 10<br>Router(config-subif)# ip address 192.168.10.1 255.255.255.0 |
| **EtherChannel (Port-channel)** | **Switches** | Bundles multiple physical links into one logical link. | Switch(config)# interface range fa0/1 - 2<br>Switch(config-if-range)# channel-group 1 mode active<br>Switch(config)# interface port-channel 1 |
| **Spanning Tree Protocol (STP)** | **Switches** | Prevents Layer 2 loops in redundant topologies. | Switch(config)# spanning-tree mode rapid-pvst |
| **Default Route / Gateway** | **Routers & Switches** | Defines a fallback path for unknown destinations. | Router(config)# ip route 0.0.0.0 0.0.0.0 192.168.1.1 |

---

### 🛡️ 3. Advanced Layer (Security & Optimization)

| **Functionality** | **Used By** | **Purpose** | **CLI Example (Cisco IOS)** |
|--------------------|-------------|--------------|-----------------------------|
| **Port Security** | **Switches** | Limits allowed MAC addresses per port. | Switch(config)# interface fa0/2<br>Switch(config-if)# switchport port-security<br>Switch(config-if)# switchport port-security maximum 2<br>Switch(config-if)# switchport port-security violation shutdown |
| **Access Control List (ACL)** | **Routers** | Filters traffic by IP/port for security or control. | Router(config)# access-list 10 permit 192.168.1.0 0.0.0.255<br>Router(config)# interface g0/0<br>Router(config-if)# ip access-group 10 in |
| **NAT (Network Address Translation)** | **Routers** | Translates private IPs to public IPs for internet access. | Router(config)# interface g0/0<br>Router(config-if)# ip nat inside<br>Router(config)# interface g0/1<br>Router(config-if)# ip nat outside<br>Router(config)# ip nat inside source list 1 interface g0/1 overload |
| **DHCP Snooping / ARP Inspection** | **Switches** | Protects from rogue DHCP servers and spoofing. | Switch(config)# ip dhcp snooping<br>Switch(config)# ip arp inspection vlan 10 |
| **QoS (Quality of Service)** | **Routers** | Prioritizes specific traffic (e.g., VoIP). | Router(config)# class-map VOICE<br>Router(config-cmap)# match protocol rtp<br>Router(config)# policy-map PRIORITY<br>Router(config-pmap)# class VOICE<br>Router(config-pmap-c)# priority 1000 |
| **VPN / IPsec Tunnel** | **Routers** | Creates secure connections between networks. | *(config omitted for brevity — advanced topic)* |

---

### 📚 Study Order Summary

| **Priority** | **Focus Area** | **Key Topics** |
|---------------|----------------|----------------|
| **1️⃣ Foundation** | Basic network operation | VLANs, Trunking, Static IPs, Static Routing |
| **2️⃣ Intermediate** | Network interconnectivity | Inter-VLAN Routing, Subinterfaces, EtherChannel, STP |
| **3️⃣ Advanced** | Security & optimization | ACLs, NAT, Port Security, DHCP Snooping, QoS, VPNs |

---

# ⚙️ CCNA Lab Practice Blueprint

## 🧩 Devices Used
- 🖥️ **Switch:** Cisco 2960G  
- 🌐 **Router:** GNS3 or Packet Tracer Router  
- 💻 **End Hosts:** 2 PCs or VMs (Windows + Linux)  
- 🔒 **Optional:** pfSense, Wazuh, Snort  

---

## 🧱 1️⃣ Foundation — Basic Connectivity & VLAN Segmentation

| **Goal** | **What to Configure** | **Device(s)** | **Test Command(s)** |
|-----------|----------------------|----------------|----------------------|
| Assign management IP to switch | Configure static IP on VLAN 1 | Switch | `show ip interface brief` |
| Create VLANs | VLAN 10 (HR), VLAN 20 (IT) | Switch | `show vlan brief` |
| Assign access ports | Fa0/1 → VLAN 10, Fa0/2 → VLAN 20 | Switch | `show interfaces switchport` |
| Configure trunk link | Fa0/24 (Switch ↔ Router or another Switch) | Switch | `show interfaces trunk` |
| Verify connectivity per VLAN | Ping within same VLAN only | PCs | `ping <same VLAN IP>` |

**Sample Config (Switch):**

```bash
vlan 10
 name HR
vlan 20
 name IT
interface range fa0/1-2
 switchport mode access
 switchport access vlan 10
interface fa0/24
 switchport mode trunk 
```
 
 ## 🧭 2️⃣ Intermediate — Routing Between VLANs & Redundancy

| **Goal** | **What to Configure** | **Device(s)** | **Test Command(s)** |
|-----------|------------------------|----------------|----------------------|
| Inter-VLAN Routing (Router-on-a-Stick) | Subinterfaces for VLANs | Router | `show ip interface brief` |
| Add Static Routes | Connect different subnets | Router | `show ip route` |
| Configure EtherChannel | Bundle `Fa0/3–Fa0/4` links | Switches | `show etherchannel summary` |
| Enable STP | Prevent loops | Switches | `show spanning-tree` |

### 🧩 Sample Config (Router)

```bash
interface g0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0

interface g0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0
 ```

 ## 🔐 3️⃣ Advanced — Security, Access Control & Optimization

| **Goal** | **What to Configure** | **Device(s)** | **Test Command(s)** |
|-----------|----------------------|----------------|-------------------|
| Secure Access Ports | Enable Port Security | Switch | `show port-security interface fa0/1` |
| Filter Traffic | Create ACL to block specific subnet | Router | `show access-lists` |
| Translate Private IPs | NAT Overload (PAT) | Router | `show ip nat translations` |
| Simulate DHCP Attack Prevention | Enable DHCP Snooping | Switch | `show ip dhcp snooping binding` |
| Optimize Traffic | Apply QoS for VoIP (optional) | Router | `show policy-map interface` |

### 🧩 Sample Config (Port Security)

```bash
interface fa0/1
 switchport port-security
 switchport port-security maximum 2
 switchport port-security violation restrict
 ```

 ## 🧪 4️⃣ Validation & Monitoring

| **Goal** | **Tool/Command** | **Purpose** |
|-----------|-----------------|-------------|
| Test Layer 2 | `show mac address-table` | Verify learned MACs |
| Test Layer 3 | `ping` / `traceroute` | Check routing between VLANs |
| Inspect STP State | `show spanning-tree` | Confirm root bridge election |
| Check Routes Dynamically | `show ip route` | Verify static or dynamic routes |
| Monitor NAT and ACLs | `show ip nat translations`, `show access-lists` | Confirm filtering & address translation |
| Save Configs | `wr mem` | Persist configuration |

---

## 🧰 Bonus: Integration with Security Home Lab Components

| **Component** | **How It Fits** | **Example Use** |
|---------------|----------------|----------------|
| Wazuh SIEM | Collect logs from router/switch syslog | Monitor configuration changes, login attempts |
| Snort IDS | Analyze mirrored traffic | Detect scans or brute-force attempts |
| pfSense | Act as router/firewall | Segment lab network and create VPN tunnels |
| Splunk | Visualize syslogs and SNMP traps | Create dashboards for events per VLAN |