# 🛡️ How to Install Ubuntu Server VM (on Windows 11 -- Stored on Drive D:)

> Wazuh is a powerful open-source platform for threat detection,
> compliance monitoring, and SIEM.
>
> This guide walks you through installing the Wazuh server and Dashboard
> UI on an Ubuntu Server VM
>
> hosted in VirtualBox on Windows 11 --- with all VM files neatly stored
> in your D:\\virtualbox-VMs\\

**💡 Tip:** Installing a headless server may involve command-line
errors, network config issues, or SSH

setup. Keep an AI assistant like **ChatGPT** or **DeepSeek** open for
quick help when you're stuck.

> **You will definitely encounter configuration errors -- keep looking
> for solutions. Patience is a virtue!**

## ✅ Requirements

• 🖥️ Windows 11 with VirtualBox installed

• 📦 Ubuntu Server 24.04 LTS VM (minimum 4 GB RAM, 40 GB storage)

• 🌐 Internet access

• 🔐 Ports 443

⸻

**📥 Step 1: Download Ubuntu Server ISO**

> 1\. Visit: 👉 <https://ubuntu.com/download/server>\
> 2. **Download** Ubuntu Server 22.04 LTS

![](../images/4ubuntu2-images/1.png) 
>
> 3\. Go to **Downloads**, then **Cut**
> ubuntu-24.04.02-live-server-amd64-iso to be moved to
> D:\\virtualbox-VMs

![](../images/4ubuntu2-images/2.png) 

3\. **Paste** it to: D:\\VirtualBox VMs\\

![](../images/4ubuntu2-images/3.png) 

## 🧰 Step 2: Create the Ubuntu Server VM in VirtualBox

1.  Open VirtualBox → Click **New**

![](../images/4ubuntu2-images/4.png) 

> 2\. Name: **Ubuntu-Wazuh-Server**\
> 3. ISO Image: click the **drop-down arrow** at the far right \> click
> **other**

![](../images/4ubuntu2-images/5.png) 

4\. choose **Windows.iso**, click **Open**

![](../images/4ubuntu2-images/6.png)
 
5\. Confirm ISO Image: **ubuntu-24.04.2-live-server-amd64.iso**

Type: **Linux**

Subtype: **Ubuntu**

Version: **Ubuntu (64-bit)**

6\. Click **Unattended Install**

![](../images/4ubuntu2-images/7.png) 

7\. Change Username: \<your_username\>

Password: \<your_password\>

![](../images/4ubuntu2-images/8.png) 

> 8\. Ram: **6MB**\
> 9. CPU: **2**\
> 10. Click **Hard Disk**

![](../images/4ubuntu2-images/9.png) 

> 11\. Disk: **VDI, 40 GB**
>
> 12\. Click **Finish**

![](../images/4ubuntu2-images/10.png) 

!!! IMPORTANT NOTE: After clicking **finish**, the VM installation will
start automatically.

> It will take 10 -- 15 minutes to install, you'll think that
> installation
>
> freezes from time to time -- just be patient).

13\. After installation, close VM, then power off (shutdown) to modify
Settings.

![](../images/4ubuntu2-images/11.png) 

14\. click **Settings**

![](../images/4ubuntu2-images/12.png) 

15\. Go to **Systems** **\> Motherboard** \> Uncheck **Floppy**

![](../images/4ubuntu2-images/13.png) 

16\. Go to **Storage** \> click Controller IDE: **Empty** \> click
Optical Drive **disk icon** \>

Select **ubuntu-24.04.2-live-server-amd.iso** \> click **OK**

![](../images/4ubuntu2-images/14.png) 

- Your Storage setup should look like the image below.

![](../images/4ubuntu2-images/15.png) 

- Click **OK**, then click **Start** on VirtualBox, then **log-in** to
  the Ubuntu Server VM.

## 🎉 Done!

You've now installed Ubuntu Server VM on VirtualBox.

The next tutorial will guide you on how to install the Wazuh SIEM on
this Ubuntu Server.

[🔙 Back to Home](../index.md)
