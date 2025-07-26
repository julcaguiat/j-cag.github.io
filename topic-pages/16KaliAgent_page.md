\*\*🛰️ How to Install the Wazuh Agent on Kali Linux VM\*\*

\> This guide walks you through installing the Wazuh Agent on a Kali

\> Linux virtual machine and registering it with your Wazuh Server \-\--

\> allowing you to monitor security events, log activity,

\>

\> and practice SIEM skills in your home lab.

⸻

\*\*✅ What You Need\*\*

\- A Kali Linux VM running in VirtualBox on Windows 11

\- A working Wazuh Server installed (on Ubuntu)

\- The IP address of your Wazuh Server

\- Internet connection on the Kali VM

⸻

\*\*🧠 Step 1: Find Your Wazuh Server\'s IP:\*\*

\> On the Ubuntu-Wazuh-Server, run:

\>

\> \*\*ip a\*\*

\>

\> Look for IP address:

\>

\> \*\*inet\*\* (ex. xxx.xxx.x.xxx)

\>

\> \![\](images/6kali-agent2-images/1.png){width=\"5.231832895888014in\"

\> height=\"2.734176509186352in\"}

⸻

\*\*🧰 Step 2: Deploy New Agent on Wazuh Dashboard to Kali-Linux\*\*

1\. \*\*Log-on\*\* to Wazuh Dashboard

2\. Click \*\*Active\*\*

\> \![\](images/6kali-agent2-images/2.png){width=\"5.258225065616798in\"

\> height=\"2.924050743657043in\"}

3\. Click \*\*Deploy new agent\*\*

\> \![\](images/6kali-agent2-images/3.png){width=\"5.22476924759405in\"

\> height=\"2.943038057742782in\"}

4\. Click \*\*DEBamd64\*\*

5\. Assign your \*\*Wazuh-Server IP address\*\*

\> \![\](images/6kali-agent2-images/4.png){width=\"5.228907480314961in\"

\> height=\"2.911392169728784in\"}

6\. Assign \*\*Agent Name\*\*

\> \![\](images/6kali-agent2-images/5.png){width=\"5.243027121609798in\"

\> height=\"2.943038057742782in\"}

7\. Copy \*\*commands\*\*

\> \![\](images/6kali-agent2-images/6.png){width=\"5.372107392825897in\"

\> height=\"2.0973359580052495in\"}

8\. Open \*\*Kali-Linux-VM\*\* -\\\> open \*\*terminal\*\*:

\> Run: \*\*sudo su\*\* (needed for administrator privileges)

9\. \*\*Paste\*\* the commands from Wazuh Dashboard and run it.

\> \![\](images/6kali-agent2-images/7.png){width=\"5.242600612423447in\"

\> height=\"2.74050634295713in\"}

10\. Start the agent:

\> Run: \*\*sudo systemctl daemon-reload\*\*

\>

\> \*\*sudo systemctl enable wazuh-agent\*\*

\>

\> \*\*sudo systemctl start wazuh-agent\*\*

11\. Check status:

\> \*\*sudo systemctl status wazuh-agent\*\*

\>

\> ✅ Should say: active (running)

⸻

\*\*🔄 Step 3: Confirm Agent Appears in Wazuh Dashboard\*\*

\- Kali-Linux-VM is now actively monitored by Wazuh as an agent.

\![\](images/6kali-agent2-images/8.png){width=\"5.455696631671041in\"

height=\"3.0589643482064743in\"}

🛡️ \*\*Step 4: Monitor Logs & Events\*\*

\> Click on your Kali-Linux-VM agent in the Dashboard to:

\>

\> • View security alerts

\>

\> • Check running processes

\>

\> • See log entries from /var/log

\>

\> • Monitor file integrity and rootkit detections

\*\*✅ Done!\*\*

You\'ve now installed the Wazuh Agent on Kali Linux and connected it to

your Wazuh Server.

The next tutorial will guide you to install Wazuh agent on the Windows

10 VM.

\> 🧠 Why Monitor Kali?

\>

\> Even though Kali is a penetration testing distro, monitoring it can:

\>

\> • Detect reverse shells and lateral movement from labs

\>

\> • Alert you if exploits succeed

\>

\> • Train you in attacker/defender visibility
