# **Welcome to my Cyber/Net Hands-On Projects Blog!**<br>
### **About This Blog**
This blog documents my **learning journey in cybersecurity and networking**, combining study, hands-on projects, and practical exercises. I also use platforms like **TryHackMe** to supplement my learning and deepen my understanding of real-world scenarios.<br>
<br>
I’ve built a **virtual lab** that serves as my personal playground for testing, experimentation, and future pentesting practice. For now, my primary focus is **developing strong networking skills** through virtual implementations, but I will eventually build network projects implemented in the **cloud environment and physical devices** as I progress.<br>
<br>
I recently passed the **CompTIA Security+** certification and am currently studying for my **CCNA** certification exam, sharing insights, lab setups, and step-by-step tutorials along the way. This blog is meant to be both a **personal reference** and a **resource for others** following a similar path in cybersecurity and networking.
💡**Tip:** Keep AI assistants like ChatGPT handy — they’re invaluable for troubleshooting, planning labs, and clarifying complex topics as you learn.

---
## ** 📘 Setting up a Virtual Home Lab w/ Wazuh SIEM  **

**What we’ll install:**

> **VirtualBox:**		| Hypervisor on host machine where VMs will be installed.<br>
> **Kali-Linux VM:**	| will serve as the attack machine<br>
> **Windows 10 VM:**	| will serve as the target machine<br>
> **Ubuntu VM:**		| will serve as the Wazuh server<br>
> **Wazuh SIEM:**		| end-points activities/threats monitoring<br> 
> **Wazuh Agents** 	| to be installed on Kali-Linux and Windows 10 VMs<br>

**What You Will Learn:**
• How to use VirtualBox as a hypervisor to run and manage multiple virtual machines.
• How to set up Kali Linux as an attack machine to simulate offensive security scenarios.
• How to configure Windows 10 as a target machine to practice detection and defense.
• How to deploy Ubuntu as a server for running the Wazuh SIEM.
• How to install and configure Wazuh SIEM to monitor endpoint activities and detect threats.
• How to set up and manage Wazuh Agents on Kali Linux and Windows 10 to forward logs and events.
• The fundamentals of building and managing a Security Operations Center (SOC) on a home lab scale.

|	 🌐 [**Network Topology Image**](/images/0/1.png)

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
## ** 📘 Setting up a New Soc Lab Architecture w/ pfSense as Firewall/Router **

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
• **pfSense** → will serve as the network firewall/router<br>

**What You Will Learn:**
• How to set up pfSense as a firewall and configure network adapters and LAN settings.
• How to configure Static IP addresses across different platforms.
• The difference between isolated vs. bridged networks for safe experimentation.
• How to configure and test connectivity between multiple VMs.
• The foundation for scaling the lab into more advanced SOC environments.<br>

|	 🌐 [**Updated Network Topology Image**](/images/0/1.png)

- 👉 [🖥️ **Part 1**: How to Install pfSense VM on Windows 11](topic-pages/8pfsense-install.md)

- 👉 [🖥️ **Part 2.a.**: pfSense VM Network Adapters and Static IP Address Configuration ](topic-pages/9pf1.md)
- 👉 [🖥️ **Part 2.b.**: Kali Linux VM Network Adapter and Static IP Address Configuration ](topic-pages/9pf1.md)
- 👉 [🖥️ **Part 2.c.**: Ubuntu Wazuh VM Network Adapters and Static IP Address Configuration ](topic-pages/9pf1.md)
- 👉 [🖥️ **Part 2.d.**: Windows 10 VM Network Adapter and Static IP Address Configuration ](topic-pages/9pf1.md)


---
## ** 📚 Essential Linux Commands for Beginners  **
- 👉 [🖥️ **Downloadable Linux Commands Cheat Sheet (useful for practicing on Kali-Linux VM)-- Coming Soon!]()

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
