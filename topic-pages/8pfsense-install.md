**Install pfSense on VirtualBox (Windows 11 Host Machine)**

**Summary:**  This guide walks you through installing **pfSense®
Community Edition (CE)** as

a virtual firewall/router on **Oracle VM VirtualBox**. We'll start by
downloading the pfSense ISO,

then install it in VirtualBox on Windows 11 host. This the first part of
our new home lab setup series,

in the next tutorial, we will configure all the VMs adapter in the
internal network and connect

everything together to build a full functional practice environment.

---
 **Terms & Acronyms (Plain‑English)**

- **pfSense:** A FreeBSD‑based, open‑source firewall/router. *"pf"*
  stands for *packet filter*.

- **VM (Virtual Machine):** A software computer that emulates hardware.

- **NIC (Network Interface Card):** A network adapter.

- **WAN (Wide Area Network):** Upstream/Internet‑facing side of the
  firewall.

- **LAN (Local Area Network):** Internal/trusted side for your devices.

- **NAT (Network Address Translation):** Lets multiple devices share one
  public IP.

- **Internal Network:** A VirtualBox network that connects VMs together
  within a network.

- **ISO:** A disk image file used to install an OS.

---
 **Prerequisites**

- **VirtualBox** installed.

- **pfSense CE ISO** downloaded from the official site.

- **Hardware virtualization** enabled in BIOS/UEFI.

- **CPU:** 		1 vCPU

- **RAM:** 		2 GB

- **Disk:** 	20 GB

---
 **Pro Tip --- Use ChatGPT for Assistance**

Keep **ChatGPT handy** for installation and configuration problems.
Provide:

- Host OS and VirtualBox version

- pfSense version and settings

- Exact error messages/screenshots

**Example prompt:**\
*"Installing pfSense CE 2.x on VirtualBox (Windows 11 host). \<**state
error here**\>. What should I check?"*

---
# **Let’s begin pfSense download and installation:**

**Step 1 --- Download pfSense ISO**

1.  Go to the
    [[https://www.pfsense.org/download/]{.underline}](https://www.pfsense.org/download/).

2.  Create an account.

![](../images/8pf-images/1.png)

3.  Click **Download**

![](../images/8pf-images/2.png)

4.  Select **AMD64 ISO IPMI/Virtual Machines**

![](../images/8pf-images/3.png)

5.  Click **ADD TO CART**, then Click **ENTER CART**

![](../images/8pf-images/4.png)

6.  Click **CHECKOUT**

![](../images/8pf-images/5.png)

7.  Click **Complete order**

![](../images/8pf-images/6.png)

8.  Click **Download Now**

![](../images/8pf-images/7.png)

---
 **Step 2 --- Install pfSense on VirtualBox**

1.  Navigate to **Downloads** folder (or where your ISO file was
    downloaded)

2.  Open **7Zip File Manager**, then **Run as Administrator**

![](../images/8pf-images/8.png)

3.  Select **netgate-installer-amd64\...iso.gz,** Copy to **Downloads**,
    then click **OK**

>**Note:** If you don't have drive D: save it to where you save your other VMs on C:/

![](../images/8pf-images/9.png)

4.  Copy **netgate-installer-v10...ISO** file to be moved to
    D:/virtualbox-VMs/pfSense directory.

![](../images/8pf-images/10.png)

5.  Create **PfSense** folder in **D:/virtualbox-VMs**, then Paste
    **netgate-installer-v10...ISO** file

![](../images/8pf-images/11.png)

6.  Open **VirtualBox**

7.  Click **New**

![](../images/8pf-images/12.png)

8.  Set 

	>Name: **pfSenseVM**<br>
	>ISO Image: **locate netgate-installer-v10...iso**<br>
	>Type: **BSD**<br>
       >SubType: **FreeBSD**<br>
       >Version: **FreeBSD (64 bit)**

9.  Click **Hardware**

![](../images/8pf-images/13.png)

10. Set 

	>Base Memory: **2048 MB RAM**<br>
	>Processor: **1 CPU**

![](../images/8pf-images/14.png)

11. Set 

	>Hard Disk: **20 GB*<br>
	>Hard Disk File Type: **VDI (Virtualbox Disk Image)**

12. Click **Finish**

![](../images/8pf-images/15.png)

	>pfSense VM will boot automatically.

![](../images/8pf-images/16.png)

13. Hit **Enter**

![](../images/8pf-images/17.png)

14. Hit **Enter**

![](../images/8pf-images/18.png)

15. Hit **Enter**

![](../images/8pf-images/19.png)

16. Hit **Enter**

![](../images/8pf-images/20.png)

17. Hit **Enter**

![](../images/8pf-images/21.png)

18. Hit **Enter**

![](../images/8pf-images/22.png)

19. Hit **Enter**

![](../images/8pf-images/23.png)

20. Hit **Enter**

![](../images/8pf-images/24.png)

21. Hit **Enter** (**Note**: confirm both WAN and LAN interfaces are active)

![](../images/8pf-images/25.png)

22. Hit **Enter**

![](../images/8pf-images/26.png)

23. Hit **Enter**

![](../images/8pf-images/27.png)


24. Hit **Enter**

![](../images/8pf-images/28.png)


25. Hit **Enter**

![](../images/8pf-images/29.png)

26. Hit **Enter**

![](../images/8pf-images/30.png)

27. Hit **Enter**

![](../images/8pf-images/31.png)

29. Hit **Enter**

![](../images/8pf-images/32.png)

	The pfSense VM console!

![](../images/8pf-images/33.png)

---
# **Done!** You now have pfSense running on VirtualBox. 
In the next tutorial, we will configure pfSense and the network adapters of each VMs to setup our new and complete functioning network with the additional pfSense firewall.

- 👉 [Back to **Home**](../index.md)

