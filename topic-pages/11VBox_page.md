\*\*💽\*\* \*\*How to Install VirtualBox on Windows 11\*\*

\*\*(This is the first step to setting up a home lab)\*\*

\> VirtualBox is a powerful open-source virtualization platform that
lets

\> you run multiple

\>

\> operating systems (Virtual Machines like Kali Linux, Ubuntu, or

\> Windows) on a host system.

\>

\> This is the first tool needed to set up a home lab. This guide shows

\> how to install VirtualBox

\>

\> with its core files on Windows 11.

⸻

\*\*💡 Tip: Have an AI Assistant Ready!\*\*

\> When installing VirtualBox, you may run into unexpected

\> errors\-\--driver issues,

\>

\> virtualization settings, or networking problems. To save time and

\> reduce frustration, keep an

\>

\> AI assistant like \*\*ChatGPT\*\* or \*\*DeepSeek\*\* open in your
browser.

\> These tools can help you

\>

\> \*\*quickly troubleshoot\*\* errors, explain cryptic messages, and
guide

\> you step-by-step through

\>

\> solutions. The output might not be the right solution sometimes, but

\> by adjusting your prompt,

\>

\> you might get the right fix.

⸻

\*\*✅\*\* \*\*Requirements\*\*

• 🖥️ Windows 11 Home or Pro

• 💾 At least 10 GB of free space on Drive D

• 🌐 Internet connection

⸻

\*\*🌐\*\* \*\*Step 1: Download VirtualBox Installer\*\*

1\\. Go to the official VirtualBox page:

\> 👉 \<https://www.virtualbox.org/wiki/Downloads\>

2\\. Under VirtualBox platform packages, click \*\*Windows hosts\*\*.

\![\](images/1VBox2-images/1.png){width=\"5.489837051618547in\"

height=\"3.0833333333333335in\"}

⸻

\*\*🛠️ Step 2: Run the Installer as Administrator\*\*

1\\. Once downloaded, go to \*\*Downloads\*\* folder.

2\\. Right click the installer file: \*\*VirtualBox-7.0.x-Wind.exe\*\*

3\\. Select \*\*Run as Administrator\*\*

\![\]( images/1VBox2-images/2.png){width=\"5.201388888888889in\"

height=\"2.923611111111111in\"}

⸻

\*\*⚠️ Step 3: Begin Installation\*\*

Click \*\*Next\*\* to start installation wizard.

\![\]( images/1VBox2-images/3.png){width=\"5.201388888888889in\"

height=\"2.923611111111111in\"}

⸻

\*\*✅ Step 4: End User License Agreement\*\*

1\. Select \*\*I accept the License Agreement\*\*.

2\. Click \*\*Next\*\*.

\> \![\]( images/1VBox2-images/4.png){width=\"5.201388888888889in\"
height=\"3.0in\"}

⸻

\*\*✅ Step 5: Custom Setup\*\*

Leave default options selected unless you have specific needs.

Click \*\*Next\*\*.

\![\]( images/1VBox2-images/5.png){width=\"5.201388888888889in\"
height=\"3.0in\"}

⸻

\*\*✅ Step 6: Finish Installation\*\*

You will see \*\*Warning: Network Interfaces\*\*. Ignore this.

Click \*\*Yes\*\*.

\![\]( images/1VBox2-images/6.png){width=\"5.333333333333333in\"
height=\"3.0in\"}

⸻

\*\*✅ Step 7: Missing Dependencies: Python Core / win32api\*\*

This appears because VirtualBox optionally supports scripting via

Python.

Click \*\*Yes\*\* If you\'re not planning to automate VirtualBox with
Python

\- The optional dependencies (Python Core and wind32api) can be added

later.

\> If you intend to add the missing dependencies, quick research will

\> help.

\![\]( images/1VBox2-images/7.png){width=\"5.201388888888889in\"

height=\"2.923611111111111in\"}

⸻

\*\*✅ Step 8: Ready to Install\*\*

\> Click \*\*Next\*\* to continue.

\![\]( images/1VBox2-images/8.png){width=\"5.201388888888889in\"

height=\"2.923611111111111in\"}

⸻

\*\*✅ Step 9: Finish Setup\*\*

When finished, leave \*\*Start Oracle VM VirtualBox after
installation\*\*.

Click \*\*Finish\*\*.

\![\]( images/1VBox2-images/9.png){width=\"5.201388888888889in\"

height=\"2.923611111111111in\"}

\> \*\*VirtualBox Manager\*\* should start automatically and the
VirtualBox

\> shortcut should

\>

\> appear on your desktop.

\>

\> \![\]( images/1VBox2-images/10.png){width=\"5.201388888888889in\"

\> height=\"2.923611111111111in\"}

\>

\> \*\*!!! REBOOT\*\* for good measures.

⸻

\*\*✅ Done!\*\*

\*\*VirtualBox\*\* is now successfully installed on your Windows 11, and
all

future

virtual machines (VMs) will be stored on: D:\\\\virtualbox-VMs\\\\ for

better organization

of VMs and for saving storage space of C:

The next steps are to setup the following on the VirtualBox:

• 🧪 Kali Linux VM for penetration testing.

• 🪟 Windows VM as target machine monitored with Wazuh Agent.

• 🛡️ Ubuntu VM as a server for Wazuh SIEM.

• 🌐 pfSense firewall for virtual networking.
