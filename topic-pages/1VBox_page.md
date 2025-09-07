## **💽** **How to Install VirtualBox on Windows 11**

**This is the first step to setting up a home lab!**

> VirtualBox is a powerful open-source virtualization platform that lets you 
> run multiple operating systems (Virtual Machines like Kali Linux, Ubuntu, or
> Windows) on a host system. This is the first tool needed to set up a home lab. 
> This guide shows how to install VirtualBox with its core files on Windows 11.

---

**💡 Tip: Have an AI Assistant Ready!**

> When installing VirtualBox, you may run into unexpected errors – 
> driver issues, virtualization settings, or networking problems. To save 
> time and reduce frustration, keep an AI assistant like **ChatGPT** or 
> **DeepSeek** ready. These tools can help you **quickly troubleshoot** errors, 
> explain cryptic messages, and guide you step-by-step through solutions. 
> The output might not be the right answers sometimes, but by adjusting your prompt,
> hopefully you’ll get the solution that you’re looking for.

---

**✅** **Requirements**

>• 🖥️ Windows 11 Home or Pro
>
>• 💾 At least 10 GB of free space on Drive D: or C: for VirtualBox alone, 
>	 need more resources (Disk: 80 GB, RAM: 16 Mb, CPU: 6) for VMs to be installed.
>
>• 🌐 Internet connection

---

### **🌐** **Step 1: Download VirtualBox Installer**

1\. Go to: 👉 <https://www.virtualbox.org/wiki/Downloads>

2\. Under VirtualBox platform packages, click **Windows hosts**.

![](../images/1VBox2-images/1.png)

⸻

### **🛠️ Step 2: Run the Installer as Administrator**

1\. Once downloaded, go to **Downloads** folder.

2\. Right click the installer file: **VirtualBox-7.0.x-Wind.exe**

3\. Select **Run as Administrator**

![](../images/1VBox2-images/2.png) 

⸻

### **⚠️ Step 3: Begin Installation**

Click **Next** to start installation wizard.

![](../images/1VBox2-images/3.png

⸻

### **✅ Step 4: End User License Agreement**

1\.  Select **I accept the License Agreement**.

2\.  Click **Next**.

![](../images/1VBox2-images/4.png) 

⸻

### **✅ Step 5: Custom Setup**

Leave default options selected unless you have specific needs.

Click **Next**.

![](../images/1VBox2-images/5.png) 

⸻

### **✅ Step 6: Finish Installation**

You will see **Warning: Network Interfaces**. Ignore this.

Click **Yes**.

![](../images/1VBox2-images/6.png) 
⸻

### **✅ Step 7: Missing Dependencies: Python Core / win32api**

This appears because VirtualBox optionally supports scripting via Python.

Click **Yes** If you're not planning to automate VirtualBox with Python

- The optional dependencies (Python Core and wind32api) can be added
  later.

> If you intend to add the missing dependencies, quick research will
> help.

![](../images/1VBox2-images/7.png) 

⸻

### **✅ Step 8: Ready to Install**

Click **Next** to continue.

![](../images/1VBox2-images/8.png) 

⸻

### **✅ Step 9: Finish Setup**

When finished, leave **Start Oracle VM VirtualBox after installation**.

Click **Finish**.

![](../images/1VBox2-images/9.png) 

- The **VirtualBox Manager** should start automatically. 

- The VirtualBox shortcut should appear on your desktop.

![](../images/1VBox2-images/10.png) 

- **!!! REBOOT** for good measure.

---

### **✅ Done!**

> **VirtualBox** is now successfully installed on your Windows 11!
> Future virtual machines (VMs) will be stored on: D:\\virtualbox-VMs\\ for
> better VM organization and saving C: storage space.

**The next steps are to setup the following on VirtualBox:**

• 🧪 Kali Linux VM installation for penetration testing.

• 🪟 Windows 10 VM installation as target machine monitored by Wazuh SIEM.

• 🛡️ Ubuntu VM and Wazuh installation for end-point security monitoring.

• 🌐 pfSense firewall for the virtual network.


[👉 Install Kali-Linux VM](/2KaliVM_page.md)

[🔙 Back to Home](../index.md)
