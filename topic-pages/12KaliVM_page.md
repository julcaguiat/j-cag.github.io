\*\*💽 How to Install Kali Linux on VirtualBox\*\*

\*\*(on Windows 11 \-- Stored on Drive D)\*\*

\> This Windows 11 step-by-step guide shows you how to install Kali
Linux

\> VM in VirtualBox

\>

\> using the .7z prebuilt image from Kali.org. You\'ll learn how to:

• Create and use a folder on Drive D: for a better organized VMs and to

\> save C: storage space. (\*\*If you don\'t have Drive D: just use
default

\> C:\*\*)

• Download and extract the .7z Kali Linux image and extract the file

with 7-Zip utility.

• Import the VM into VirtualBox

• Set the default machine folder to D:\\\\virtualBox-VMs

⸻

\*\*💡 Tip: Keep an AI Assistant Handy During VM Setup!\*\*

Installing an OS in a VM can cause issues like boot failures or display

bugs.

Keep an AI assistant like \*\*ChatGPT\*\* open to help troubleshoot
errors,

BIOS settings,

or installer problems quickly.

⸻

\> \*\*📁 Step 1: Create a Folder on Drive D for Your VMs\*\*

\>

\> \*\*(skip this step if you don\'t have Drive D:)\*\*

\>

\> To keep your C: drive clean and avoid space issues, we\'ll store Kali

\> and future VMs in a custom folder on D:

1\\. Press \*\*Win\*\* + \*\*E\*\* to open \*\*File Explorer\*\*

2\\. Go to \*\*This PC\*\* \\\> \*\*Data (D:)\*\*

3\\. Right-click → New \\\> Folder

\![\](images/2Kali2-images/1.png){width=\"5.493826552930884in\"

height=\"3.0902777777777777in\"}

4\\. Name it: \*\*virtualbox-VMs\*\*

\![\]( images/2Kali2-images/2.png){width=\"5.493826552930884in\"

height=\"3.0902777777777777in\"}

⸻

\*\*📥 Step 2: Download the Kali Linux VirtualBox Image\*\*

1\\. Go to: 👉

\[https://www.kali.org/get-kali/#kali-platforms\](https://www.kali.org/get-kali/%23kali-platforms)

2\\. Click \*\*Virtual Machines\*\*.

\![\]( images/2Kali2-images/3.png){width=\"5.5in\" height=\"3.09375in\"}

3\\. You\'ll be redirected to the \*\*Pre-built Virtual Machines\*\*
page.

4\\. Click \*\*VirtualBox\*\* to download

\*\*kali-linux-2025.2-virtualbox-amd64.7z\*\*.

\![\]( images/2Kali2-images/4.png){width=\"5.493825459317585in\"

height=\"3.0902777777777777in\"}

5\\. Go to your \*\*Downloads\*\* folder, right click on

\*\*kali-linux-2025.2-virtualbox-amd64.7z\*\*,

then click \*\*Cut\*\* to move the file to
\*\*D:\\\\virtualbox-VMs\\\\.\*\*

\*\*(Skip this and the next step if you don\'t have Drive D:)\*\*

\![\]( images/2Kali2-images/5.png){width=\"5.518518153980753in\"

height=\"3.1041666666666665in\"}

6\\. Go to \*\*This PC\*\* \\\> \*\*DATA (D:)\*\* \\\>
\*\*virtualbox-VMs\*\* then

\*\*Paste\*\*.

\![\]( images/2Kali2-images/6.png){width=\"5.493826552930884in\"

height=\"3.0902777777777777in\"}

⸻

\*\*🧰 Step 3: Download and Install 7-Zip Utility Tool (to Extract the
.7z

File)\*\*

1\\. Visit: 👉 \<https://www.7-zip.org/\>

2\\. Download the \*\*64-bit x64 installer\*\*

\![\]( images/2Kali2-images/7.png){width=\"5.479166666666667in\"

height=\"3.08203302712161in\"}

3\\. Run the installer and complete setup.

.

\![\]( images/2Kali2-images/8.png){width=\"5.493827646544182in\"

height=\"3.0902777777777777in\"}

\![\]( images/2Kali2-images/9.png){width=\"5.5in\" height=\"3.09375in\"}

⸻

\*\*🗂️ Step 4: Extract the Kali VM from

kali-linux-2025.2-virtualbox-amd64.7z.\*\*

\*\*Note: If you don\'t have Drive D: you can extract Kali VM in your

Download folder\*\*

\> \*\*or move the .7z file to a different folder where you can do the

\> extraction.\*\*

1\\. Go to: \*\*D:\\\\virtualbox-VMs\\\\\*\*

2\\. Right click \*\*kali-linux-2025.2-virtualbox-amd64.7z\*\* then
select

\*\*Extract All\*\*.

\![\]( images/2Kali2-images/10.png){width=\"5.493827646544182in\"

height=\"3.0902777777777777in\"}

3\\. Click \*\*Extract\*\*

\![\]( images/2Kali2-images/11.png){width=\"5.506172353455818in\"

height=\"3.0972222222222223in\"}

⸻

\*\*📂 Step 5: Set VirtualBox to Use D:\\\\VirtualBox VMs by Default\*\*

\> \*\*(skip this if you are don\'t have Drive D:)\*\*

1\\. Open \*\*VirtualBox\*\*

2\\. Go to: \*\*File\*\* \\\> \*\*Preferences\*\* \\\> \*\*General\*\*

3\\. Under \*\*Default Machine Folder\*\*, set to\*\*:
D:\\\\virtualbox-VMs\*\*

4\\. Click \*\*OK\*\*

\![\]( images/2Kali2-images/12.png){width=\"5.518518153980753in\"

height=\"3.1041666666666665in\"}

⸻

\*\*💻 Step 6: Import Kali-Linux into VirtualBox\*\*

1\. In \*\*VirtualBox\*\*: Go to \*\*Machine\*\* \\\> \*\*Add\*\*

\![\]( images/2Kali2-images/13.png){width=\"5.530865048118985in\"

height=\"3.111111111111111in\"}

2\\. Navigate to: \*\*D:\\\\VirtualBox

VMs\\\\kali-linux-2025.2-virtualbox-amd64\*\*,

\> then \*\*double click\*\* or click \*\*Open\*\*.

\![\]( images/2Kali2-images/14.png){width=\"5.506173447069116in\"

height=\"3.0972222222222223in\"}

3\\. \*\*Double click\*\* or click \*\*Open\*\*

\*\*Kali-Linux-2025.2-virtualbox-amd64.vbox\*\*.

\![\]( images/2Kali2-images/15.png){width=\"5.493827646544182in\"

height=\"3.0902777777777777in\"}

⸻

\*\*🚀 Step 7: Start the Kali-Linux VM\*\*

1\\. Select the \*\*Kali-Linux VM\*\* in \*\*VirtualBox\*\*

2\\. Click \*\*Start\*\*

3\\. Wait for Kali-Linux to boot

\![\]( images/2Kali2-images/16.png){width=\"5.493826552930884in\"

height=\"3.0902777777777777in\"}

⸻

\*\*🔐 Step 8: Login Credentials\*\*

Username: \*\*kali\*\*

Password: \*\*kali\*\*

\![\]( images/2Kali2-images/17.png){width=\"5.505664916885389in\"

height=\"2.9027777777777777in\"}

After login, you\'re ready to explore the Kali Linux environment.

\![\]( images/2Kali2-images/18.png){width=\"5.501879921259842in\"

height=\"2.9097222222222223in\"}

⸻

\*\*✅ You\'re Done!\*\*

\> This is just one way of installing a Virtual Machine, you can also

\> install a VM by mounting an .ISO image file. We will try to do that

\> with the Windows 10 VM in next tutorial. But for now, you\'ve

\> successfully installed Kali Linux in VirtualBox on Windows 11 system,

\> and:

• Installed 7-Zip and extracted a .7z image file.

• Stored everything in: D:\\\\virtualbox-VMs\\\\ (if you have Drive: D)
