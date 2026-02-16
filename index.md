
**Updated:** 02-16-2026 [added: PacketTracer Lab5]<br> 
**Started:** 08-15-2025

# **Welcome to my Cybersecurity/Networking Projects Page!**<br>
### **About This Blog**

This blog documents my learning journey in **cybersecurity** and **networking**, combining study, hands-on projects, and practical exercises. I use platforms such as **PacketTracer** for network simulations and  **TryHackMe** for cybesecurity hands-on lab to deepen my understanding of real-world scenarios. I have also implemented **virtual** and **physical** labs as a personal playground for practicing **network implementations** and **penetration testing**. Having recently earned the **CompTIA Security+** and **CCNA** certifications and currently studying **CCNP Security**. I maintain this blog to document my projects, serve as a personal reference, and provide a resource for others. I hope it can be helpful, even in the smallest way.


💡**Strong recommendation:** Keep AI assistants like ChatGPT handy — they’re invaluable for troubleshooting, planning labs, and clarifying complex topics as you learn.

---
### Table of Contents
---

**Hands-on Lab Projects**

<ol class="tool-list">
  <li>
    <a href="#virtual-soc-home-lab" title="Jump to Virtual SOC Setup">
      🖥️ Setting up a Basic Virtual SOC (Security Operation Center) Home Lab
    </a>
    <br>
    <span class="note">[Kali Linux & Windows10 VMs w/ Wazuh SIEM (HIDS) on VirtualBox running on Windows 11]</span>
  </li>
  <br>
  <li>
    <a href="#upgraded-home-lab" title="Jump to Upgraded Home Lab">
      🔥 Upgraded Home Virtual Lab
    </a>
    <br>
    <span class="note">[Integrating pfSense Virtual Firewall/Router & Static IP Setup]</span>
  </li>
 <br>
  <li>
    <a href="#personal-home-lab" title="Jump to Personal Cybersecurity Home Lab">
      🛠️ [WORK IN PROGRESS] Hybrid (Physical & Virtual) Cybersecurity Home Lab
    </a>
    <br>
    <!--
    <span class="note">[Integrating Cisco 1841 Router & 2960G Switch (VLAN / Trunking), Multi-Host Virtual Machines with Splunk (Log Management), Snort (NIDS/NIPS), Nextcloud (Self-Hosted File Server)]</span>
    -->
  </li>
   <br>
  <li>
    <a href="topic-pages/22packettracer.html">
     🌐 Enterprise Network Architecture Project (Cisco Packet Tracer)</a>
    <br>
    [Designing, implementing, and documenting a multi-tier enterprise campus network with VLAN segmentation, inter-VLAN routing, Layer 2/3 redundancy, WAN connectivity, and enterprise services]
  </li>
 <br>
 <li>
    <a href="#tryhackme" title="Jump to TryHackMe">
     🛡️ TryHackMe Practical Labs [walkthroughs with images]
    </a>
    <br>
    [SOC Simulation, Pentest, and SOC Practical Labs]
  </li>
 <br>

</ol>

---
---
**Downloadable Command Cheat Sheets**

- [🐧 Essential Linux Commands Cheat Sheet for Beginners [Download Available)]](#linux-commands)

- [🔑 SSH (Secure Shell): Guide for Secure Remote Login and Command Execution (Download Available)](#SSH)

- [⬇️ SCP (Secure Copy Protocol): Guide for Secure File Transfer Between Machines [Download Available]](#SCP)

---

<h2 id="tryhackme">🖥️</h2>

**🛡️ TryHackMe SOC Simulations [Walkthroughs]** 

<ul class="tool-list">
 <li>
   Phishing Scenario SOC Sim
   <ul class="tool-sublist">
     <li>
       <a href="/j-cag.github.io/images/101thm_SOC_SIM/SOCSim_Phishing1.pdf"
          target="_blank" rel="noopener noreferrer"
          title="Phishing 1 SOC Sim (PDF)">
         SOC Sim 1: Introduction to Phishing
       </a>
       <br>
       <span class="note">[Learn to monitor and analyse real-time alerts | Identify and document critical events | Create detailed case reports based on your observations]</span>
     </li>
     <li>
       <a href="/j-cag.github.io/images/101thm_SOC_SIM/SOCSim_Phishing2.pdf"
         target="_blank" rel="noopener noreferrer"
         title="Phishing 2 SOC Sim (PDF)">
        SOC Sim 2: Phishing Unfolding
       </a>
       <br>
       <span class="note">[Learn to monitor and analyse real-time alerts | Identify and document critical events | Create detailed case reports based on your observations]</span>
     </li>
   </ul>
 </li>
</ul>

---

**Hand-picked TryHackMe Rooms [Walkthroughs]**

**⚔️ Jr. Pentester**<br>

<ul class="tool-list">
  <li>
    Intro to Web Hacking
    <ul class="tool-sublist">
      <li>
        <a href="/j-cag.github.io/images/100thm-pdfs/Authentication-Bypass.pdf"
           target="_blank"
           rel="noopener noreferrer"
           title="Open Authentication Bypass (PDF)">
          Authentication Bypass
        </a>
        <br>
        <span class="note">[Used fluff utility with wordlist (user enumeration)  | crackstation.net (decoding) | base64encoding.org (encoding)]</span>
      </li>
    </ul>
  </li>
</ul>
<ul class="tool-list">
  <li>
    Hydra [password cracking tool]
    <ul class="tool-sublist">
      <li>
        <a href="/j-cag.github.io/images/100thm-pdfs/Hydra.pdf"
           target="_blank"
           rel="noopener noreferrer"
           title="Hydra (PDF)">
           Hydra
        </a>
        <br>
        <span class="note">[SSH Password Cracking Command: (hydra -l &lt;username&gt; -P &lt;full path to pass&gt; MACHINE_IP -t 4 ssh)  | Post Web Form Login Password Cracking Command: (hydra -l &lt;username&gt; -P &lt;wordlist&gt; MACHINE_IP http-post-form "/login:username=^USER^&password=^PASS^:F=&lt;incorrect&gt;" -V)]
        </span>
      </li>
    </ul>
  </li>
</ul>

<ul class="tool-list">
  <li>
    Nmap [scanning tool] 
     <br>
       <span class="note">(hosts | port status | service/version dicovery, and OS detection)</span>
    <ul class="tool-sublist">
      <li>
        <a href="/j-cag.github.io/images/100thm-pdfs/Nmap1-Live-Host-Discovery.pdf"
           target="_blank"
           rel="noopener noreferrer"
           title="Open Nmap Part 1: Live Host Discovery (PDF)">
          Part 1: Live Host Discovery
        </a>
      </li>
      <li>
        <a href="/j-cag.github.io/images/100thm-pdfs/Nmap2-Basic-Port-Scan.pdf"
           target="_blank"
           rel="noopener noreferrer"
           title="Open Nmap Part 2: Basic Port Scan (PDF)">
          Part 2: Basic Port Scan
        </a>
      </li>
      <li>
        <a href="/j-cag.github.io/images/100thm-pdfs/Nmap3-Advance-Port-Scan.pdf"
           target="_blank"
           rel="noopener noreferrer"
           title="Open Nmap Part 3: Advance Port Scan (PDF)">
          Part 3: Advance Port Scan
        </a>
      </li>
      <li>
        <a href="/j-cag.github.io/images/100thm-pdfs/Nmap3-Post-Port-Scan.pdf"
           target="_blank"
           rel="noopener noreferrer"
           title="Open Nmap Part 4: Post Port Scan (PDF)">
          Part 4: Post Port Scan
        </a>
      </li>
    </ul>
  </li>
</ul>

<ul class="tool-list">
  <li>
    Burp Suite [tool for web application security testing]
     <br>
       <span class="note">(intercept, modify, and analyze HTTP(S) traffic, scan for vulnerabilities, and automate web security assessments)</span>
    <ul class="tool-sublist">
      <li>
        <a href="/j-cag.github.io/images/100thm-pdfs/BurpSuite1-The-Basics.pdf"
           target="_blank"
           rel="noopener noreferrer"
           title="Open Burp Suite Part 1: The Basics (PDF)">
          Part 1: The Basics
        </a>
      </li>
      <li>
        <a href="/j-cag.github.io/images/100thm-pdfs/BurpSuite2-Repeater.pdf"
           target="_blank"
           rel="noopener noreferrer"
           title="Open Burp Suite Part 2: Repeater (PDF)">
          Part 2: Repeater
        </a>
      </li>
      <li>
        <a href="/j-cag.github.io/images/100thm-pdfs/BurpSuite3-Intruder.pdf"
           target="_blank"
           rel="noopener noreferrer"
           title="Open Burp Suite Part 3: Intruder (PDF)">
          Part 3: Intruder
        </a>
      </li>
      <li>
        <a href="/j-cag.github.io/images/100thm-pdfs/BurpSuite4-Other-Modules.pdf"
           target="_blank"
           rel="noopener noreferrer"
           title="Open Burp Suite Part 4: Other Modules (PDF)">
          Part 4: Other Modules
        </a>
      </li>
      <li>
        <a href="/j-cag.github.io/images/100thm-pdfs/BurpSuite5-Extensions.pdf"
           target="_blank"
           rel="noopener noreferrer"
           title="Open Burp Suite Part 5: Extensions (PDF)">
          Part 5: Extensions
        </a>
      </li>
    </ul>
  </li>
</ul>

<ul class="tool-list">
 <li>
   Vulnerability Research
   <ul class="tool-sublist">
     <li>
       <a href="/j-cag.github.io/images/100thm-pdfs/Vulnerability1-Exploit.pdf"
          target="_blank" rel="noopener noreferrer"
          title="Open Vulnerability Part 1: Vulnerability Exploit (PDF)">
         Part 1: Vulnerability Exploit
       </a>
       <br>
       <span class="note">[Used Exploit-DB (research & scripts). Configured vetted exploit scripts to launch RCE on an authorized test target]</span>
     </li>
     <li>
       <a href="/j-cag.github.io/images/100thm-pdfs/Vulnerability2-Capstone.pdf"
         target="_blank" rel="noopener noreferrer"
         title="Open Vulnerability Part 2: Vulnerability Capstone (PDF)">
        Part 2: Vulnerability Capstone
       </a>
       <br>
       <span class="note">[Used Exploit-DB, configured vetted exploit scripts & Netcat to deploy payloads and achieve RCE on authorized test systems]</span>
     </li>
   </ul>
 </li>
</ul>

<ul class="tool-list">
 <li>
   Metasploit [tool for payload generation and systems exploitation]
   <ul class="tool-sublist">
     <li>
       <a href="/j-cag.github.io/images/100thm-pdfs/Metasploit1-Introduction.pdf"
          target="_blank" rel="noopener noreferrer"
          title="Open Metasploit Part 1: Introduction (PDF)">
         Part 1: Introduction
       </a>
       <br>
       <!--
       <span class="note">[Used ]
       </span>
       -->
     </li>
     <li>
       <a href="/j-cag.github.io/images/100thm-pdfs/Metasploit2-Exploitation.pdf"
         target="_blank" rel="noopener noreferrer"
         title="Open Metasploit Part 2: Exploitation (PDF)">
        Part 2: Exploitation
       </a>
       <br>
       <span class="note">[used ssh (initial access), msfvenom (payload generation), exploit/multi/handler (reverse shell catching), python3 -m http.server &lt;LOCAL_HOST&gt;&lt;PORT&gt; (web server), wget &lt;uri&gt;:&lt;port&gt;/&lt;file&gt; (file download)]
       </span>
     </li>
     <li>
       <a href="/j-cag.github.io/images/100thm-pdfs/Metasploit3-Meterpreter.pdf"
         target="_blank" rel="noopener noreferrer"
         title="Open Metasploit Part 3: Meterpreter (PDF)">
        Part 3: Meterpreter
       </a>
       <br>
       <span class="note">[used ‘exploit/windows/smb/psexec’ module to gain initial access (session creation); other enumeration modules to gather information; Meterpreter commands (for discovery/enumeration, file searches, etc); ps, migrate &lt;PID&gt;, & hashdump commands (for password hashes extraction); crackstation.net (for cracking password hashes)]
       </span>
     </li>
   </ul>
 </li>
</ul>
<ul class="tool-list">
 <li>
   Privilege Escalation
   <ul class="tool-sublist">
     <li>
       <a href="/j-cag.github.io/images/100thm-pdfs/PrivilegeEscalation1-Shell.pdf"
          target="_blank" rel="noopener noreferrer"
          title="Open Privilege Escalation Part 1: What the Shell? (PDF)">
         Part 1: What the Shell?
       </a>
       <br> 
       <span class="note">[Used netcat & socat (bind and reverse shells), metasploit – msfvenom & multihandler (for payload generation/handling), RDP/SSH & SCP (for RCE & file transfer)]
       </span>
     </li>
     <li>
       <a href="/j-cag.github.io/images/100thm-pdfs/PrivilegeEscalation2-Linux.pdf"
         target="_blank" rel="noopener noreferrer"
         title="Open Privilege Escalation Part 2: Linux (PDF)">
        Part 2: Linux Privilege Escalation
       </a>
       <br>
       <span class="note">[Used: Linux commands (for enumeration/searches), cvedetails.com (for vulnerability research), exploit-db.com (for available payloads), Metasploit – MSFvenom & multihandler (for payload generation/handling), gtfobin.githug.io (for sudo/suid executables), SSH & SCP [for initial access/RCE & file transfers (uploads)], Python3 -m http.sever [port] & wget [uri]:[port]/file_path/file [for http file server & transfers (downloads)], John the Ripper (for cracking password hashes)]</span>
     </li>
     <li>
       <a href="/j-cag.github.io/images/100thm-pdfs/PrivilegeEscalation3-Windows.pdf"
         target="_blank" rel="noopener noreferrer"
         title="Open Privilege Escalation Part 3: Windows (PDF)">
        Part 3: Windows Privilege Escalation
       </a>
       <br>
       <span class="note">[Used: MSFvenom (for payload generation), xfreerdp utitily (for remote connection from linux to windows), Python3 -m http.sever [port] & wget [uri]:[port]/file_path/file [for http file server & transfers (downloads)], smbserver.py (to start a simple SMB server), secretsdump.py (to retrieve the users' password hashes), psexec.py (to perform a Pass-the-Hash attack), RogueWinRM exploit (for impersonation method privilege escalation)]</span>
     </li>
   </ul>
 </li>
</ul>

**🛡️ SOC 1**

<ul class="tool-list">
 <li>
   Threat Detection Tools
   <ul class="tool-sublist">
     <li>
       <a href="/j-cag.github.io/images/100thm-pdfs/Splunk1_TheBasic.pdf"
          target="_blank" rel="noopener noreferrer"
          title="Splunk: The Basic (PDF)">
         Spunk: The Basic
       </a>
       <br>
       <span class="note">[Splunk components | Navigate Splunk Interface | Upload data (adding data) to Splunk (ex. VPN logs) | Basic search commands]</span>
     </li>
     <li>
       <a href="/j-cag.github.io/images/100thm-pdfs/Splunk2_Exploring_SPL.pdf"
          target="_blank" rel="noopener noreferrer"
          title="Splunk: Exploring SPL (Splunk Processing Language) (PDF)">
         Spunk: Exploring SPL (Splunk Processing Language)
       </a>
       <br>
       <span class="note">[Search & Reporting app interface (Splunk home page) overview | SPL commands | Filter, structure, & transform SPL results]</span>
     </li>
     <li>
       <a href="/j-cag.github.io/images/100thm-pdfs/ElasticStack_TheBasic.pdf"
         target="_blank" rel="noopener noreferrer"
         title="ELK Stack: The Basic (PDF)">
        ELK Stack: The Basic
       </a>
       <br>
       <span class="note">[ELK components | Features of ELK | Search and filter data | Investigate VPN logs | Create visualizations and dashboards]</span>
     </li>
   </ul>
 </li>
</ul>


---
---

<h2 id="virtual-soc-home-lab">🖥️ Setting up a Virtual SOC Home Lab - Kali Linux & Windows10 VMs w/ Wazuh SIEM on VirtualBox</h2>


**What we’ll install:**

> **VirtualBox:**		| Hypervisor on host machine where VMs will be installed.<br>
> **Kali-Linux VM:**	| will serve as the attack machine<br>
> **Windows 10 VM:**	| will serve as end-point<br>
> **Ubuntu VM:**		| will be the Headless Server for Wazuha<br>
> **Wazuh SIEM:**		| end-point activities/threats monitor & IR<br> 
> **Wazuh Agents** 	| to be installed on Kali-Linux and Windows 10 VMs<br>

**What You Will Learn:**
• How to use VirtualBox as a hypervisor to run and manage multiple virtual machines.
• How to set up Kali Linux as an attack machine to simulate offensive security scenarios.
• How to configure Windows 10 as a target machine to practice detection and defense.
• How to deploy Ubuntu as a server for running the Wazuh SIEM.
• How to install and configure Wazuh SIEM to monitor endpoint activities and detect threats.
• How to set up and manage Wazuh Agents on Kali Linux and Windows 10 to forward logs and events.
• The fundamentals of building and managing a Security Operations Center (SOC) on a home lab scale.<br>
<br>
<!--
|	 🌐 [**Network Topology Image**](/images/0/lab-image1.png)
-->
🌐 <a href="/j-cag.github.io/images/0/lab-image1.png" target="_blank" rel="noopener noreferrer">
<strong>Network Topology Image</strong>
</a>

- 👉 [🖥️ **Step 1**: How to Install VirtualBox on Windows 11](topic-pages/1VBox_page.md)
- 👉 [🖥️ **Step 2**: How to Install Kali-Linux VM on Windows 11](topic-pages/2KaliVM_page.md)
- 👉 [🖥️ **Step 3**: How to Install Windows 10 VM on Windows 11](topic-pages/3WinVM_page.md)
- 👉 [🖥️ **Step 4**: How to Install Ubuntu Server VM on Windows 11](topic-pages/4UbuntuServerVM_page.md)
- 👉 [🖥️ **Step 5**: How to Install Wazuh SIEM on Ubuntu Server VM](topic-pages/5Wazuh_page.md)
- 👉 [🖥️ **Step 6**: How to Install Wazuh Agent on Kali-Linux VM](topic-pages/6KaliAgent_page.md)
- 👉 [🖥️ **Step 7**: How to Install Wazuh Agent on Windows 10 VM](topic-pages/7WinAgent_page.md)

**Note:** The VMs in this home lab use Bridge mode for internet access, so they’re part of your 
       home network and not an isolated lab. If you want an isolated lab, wait until everything is set up, 
       then switch adapters to Host-only or Internal Network. After completing the lab setup, you now have 
 an attack machine, a target machine, and SIEM to monitor activity — feel free to tweak settings, 
 modify SIEM rules, and experiment. Don’t worry about breaking anything; you can always reinstall a VM. 
       **Have fun and happy learning!**

---
<h2 id="upgraded-home-lab">🔥 Upgraded Home Lab: pfSense Firewall & Static IP</h2>

**In this section,** we’ll install pfSense and configure it as firewall/router. We will then 
reconfigure the network adapters of all existing VMs and set their IP addresses as Static IPs. 
The lab will be built as an Internal Network with internet access capability, ensuring both 
connectivity and isolation for safe experimentation.<br>

To keep things organized, **the guide is split into five parts:**<br>
> • Part 1:		| pfSense VM Installation<br>
> • Part 2.a: 	| pfSense Adapters & IP Configurations<br>
> • Part 2.b: 	| Kali Linux Adapter & IP Configurations<br>
> • Part 2.c: 	| Ubuntu Wazuh Adapter & IP Configurations<br>
> • Part 2.d:	| Windows 10 Adapter & IP Configurations<br>

**What We’ll Install**<br>
• **pfSense** → will serve as the network virtual firewall/router<br>

**What You Will Learn:**
• How to set up pfSense as a firewall and configure network adapters and LAN settings.
• How to configure Static IP addresses across different platforms.
• The difference between isolated vs. bridged networks for safe experimentation.
• How to configure and test connectivity between multiple VMs.
• The foundation for scaling the lab into more advanced SOC environments.<br>

|	 🌐 [**Updated Network Topology Image**](/images/0/lab-image2.png)

- 👉 [🖥️ **Part 1**: How to Install pfSense VM on Windows 11](topic-pages/8pfsense-install.md)

- 👉 [🖥️ **Part 2.a**: pfSense VM Network Adapters and Static IP Address Configuration ](topic-pages/9pf1.md)
- 👉 [🖥️ **Part 2.b**: Kali Linux VM Network Adapter and Static IP Address Configuration ](topic-pages/10kali2.md)
- 👉 [🖥️ **Part 2.c**: Ubuntu Wazuh VM Network Adapters and Static IP Address Configuration ](topic-pages/11w3.md)
- 👉 [🖥️ **Part 2.d**: Windows 10 VM Network Adapter and Static IP Address Configuration ](topic-pages/12win4.md)


---
<h2 id="personal-home-lab">🛠️ Personal Cybersecurity Home Lab Project: WORK-IN-PROGRESS </h2>

**Preparation**
- 👉 [🖥️ **Inspiron 3650 Desktop (for Splunk, Snort, and File Server)**: Bypass Windows 10 Login using Rufus and chntpw utilities ]

|	 🌐 [**Updated Network Topology Image**]

- 👉 [🖥️ **Phase 1 (Asset Inventory)**: Record of all devices, IPs, VLANs, and services](topic-pages/30phase-1.md)

**COMMING SOON!**

- 👉 [🖥️ **Phase 2 (Risk Assessment)**: Design decisions, security rules, and priorities documentation]
- 👉 [🖥️ **Phase 3 (Logical Design)**: Network diagram and notes ]
- 👉 [🖥️ **Phase 4 (Physical/Virtual Design)**: Connected VMs, virtual firewall/router, switch, and other physical devices ]
- 👉 [🖥️ **Phase 5 (Implementation & Hardening)**: Record of configurations, firewall rules, and applied hardening measures ]
- 👉 [🖥️ **Phase 6 (Monitoring & Improvement)**: Reference for logs, alerts, and changes over time ]

---

<h2 id="linux-commands">🐧 Essential Downloadable Linux Commands Cheat Sheet for Beginners</h2>

- 👉 [📖 View Linux Commands Guide (useful for practicing your Linux skills)](topic-pages/13linux-commands-cheatsheet.md) 

<a href="downloadables/linux-commands.pdf" 
   download="linux-commands.pdf"
   type="application/pdf"
   style="display:inline-block;
       padding:6px 12px;       /* smaller padding */
       font-size:14px;         /* smaller font */
       font-weight:bold;
       color:#fff;
       background-color:#007BFF;
       text-decoration:none;
       border-radius:6px;      /* slightly smaller corners */
       box-shadow:0 3px 4px rgba(0,0,0,0.1);
       transition:background-color 0.3s ease;">
   📥 Download PDF
</a>

---
<h2 id="SSH">🔑 SSH (Secure Shell): Guide for Secure Remote Login and Command Execution</h2>

- 👉 [📖 View How to Implement SSH Guide (useful for remote login into a different machine)](topic-pages/14SSH.md) 

<a href="downloadables/SSH.pdf" 
   download="SSH Cheat Sheet.pdf"
   type="application/pdf"
   style="display:inline-block;
       padding:6px 12px;       /* smaller padding */
       font-size:14px;         /* smaller font */
       font-weight:bold;
       color:#fff;
       background-color:#007BFF;
       text-decoration:none;
       border-radius:6px;      /* slightly smaller corners */
       box-shadow:0 3px 4px rgba(0,0,0,0.1);
       transition:background-color 0.3s ease;">
   📥 Download PDF
</a>

---

<h2 id="SCP">🔑 SCP (Secure Copy Protocol): Guide for Secure File/Directory Transfer</h2>

- 👉 [📖 View How to Use SCP Guide (useful for secure file transfers between different machines)](topic-pages/16SSH_SCP_guide.md) 
 
<a href="downloadables/SCP.pdf" 
   download="SCP Cheat Sheet.pdf"
   type="application/pdf"
   style="display:inline-block;
       padding:6px 12px;       /* smaller padding */
       font-size:14px;         /* smaller font */
       font-weight:bold;
       color:#fff;
       background-color:#007BFF;
       text-decoration:none;
       border-radius:6px;      /* slightly smaller corners */
       box-shadow:0 3px 4px rgba(0,0,0,0.1);
       transition:background-color 0.3s ease;">
   📥 Download PDF
</a>

---
## ** 📚 Security+ and CCNA Study Notes  **
Review key concepts and domains while preparing for the CompTIA Security+ certification:

- 📘 *(Coming soon)*
- 📘 *(Coming soon)*

Review key concepts and domains while preparing for the CCNA certification:

- 📘 *(Coming soon)*
- 📘 *(Coming soon)*

---
**🛠️ What’s Coming Next?**

- More **Security+ domains**
- Advanced **SIEM use cases**
- TryHackMe walkthroughs
- Bash and PowerShell scripting tutorials

---