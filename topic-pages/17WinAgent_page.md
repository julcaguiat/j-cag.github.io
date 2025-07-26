\*\*🛰️ How to Install the Wazuh Agent on a Windows 10 VM\*\*

\> The Wazuh Agent runs on endpoints (like Windows 10) and sends logs,

\> events, and security

\>

\> data to the Wazuh Manager for analysis. This tutorial will guide you

\> through installing and

\>

\> registering the Wazuh Agent on a Windows 10 VM inside VirtualBox, and

\> connecting it to

\>

\> your existing Wazuh Server on Ubuntu.

⸻

\*\*✅ What You Need\*\*

• A Windows 10 VM running in VirtualBox on your Windows 11 host

• A working Wazuh Server (on Ubuntu VM), installed using the previous

guide

• The IP address of the Wazuh Server

• Internet access on the Windows 10 VM

⸻

\*\*🌐 Step 1: Find Your Wazuh Server\'s IP Address\*\*

\> On your Ubuntu VM (Wazuh Server), run:

\>

\> \*\*ip a\*\*

\>

\> Look for IP address:

\>

\> \*\*inet\*\* (ex. xxx.xxx.x.xxx)

\![\](images/7win-agent2-images/1.png){width=\"5.231832895888014in\"

height=\"2.734176509186352in\"}

⸻

\*\*🧰 Step 2: Deploy New Agent on Wazuh Dashboard to Kali-Linux\*\*

1\. \*\*Log-on\*\* to Wazuh Dashboard

2\. Click \*\*Active\*\*

3\. Click \*\*Deploy new agent\*\*

\> \![\](images/7win-agent2-images/2.png){width=\"5.4994783464566925in\"

\> height=\"3.0822779965004377in\"}

4\. Click \*\*MSI 32/64 bits\*\*

5\. Assign your \*\*Wazuh-Server IP address\*\*

\![\](images/7win-agent2-images/3.png){width=\"5.4824726596675415in\"

height=\"3.0379746281714786in\"}

6\. Assign \*\*Agent Name\*\*

7\. Copy \*\*commands\*\*

\![\](images/7win-agent2-images/4.png){width=\"5.476923665791776in\"

height=\"3.082055993000875in\"}

8\. Open \*\*Windows10-VM\*\* -\\\> open \*\*PowerShell as
Administrator\*\*:

\> \![\](images/7win-agent2-images/5.png){width=\"5.561538713910761in\"

\> height=\"2.9341360454943133in\"}

9\. \*\*Paste\*\* the commands from Wazuh Dashboard and run it.

10\. Run: \*\*NET START WazuhSvc\*\*

\> \![\]( images/7win-agent2-images/6.png){width=\"5.570347769028872in\"

\> height=\"2.8923075240594924in\"}

⸻

\*\*🔄 Step 3: Confirm Agent Appears in Wazuh Dashboard\*\*

\- Windows10-VM is now actively monitored by Wazuh as an agent.

\> \![\](images/7win-agent2-images/7.png){width=\"5.512253937007874in\"

\> height=\"3.06923009623797in\"}

\*\*Step 4: Monitor Logs & Events\*\*

\> Click on your Windows10-VM agent in the Dashboard to:

\>

\> • View alerts

\>

\> • Check file integrity logs

\>

\> • Monitor services and system events

\*\*✅ Done!\*\*

You\'ve now installed the Wazuh Agent on Windows 10 VM and connected it

to your Wazuh Server.

\> 🔎 What You Can Monitor Now:

\>

\> • Windows Event Logs (login failures, policy changes, etc.)

\>

\> • File Integrity Monitoring (FIM)

\>

\> • Registry changes

\>

\> • Installed apps and services
