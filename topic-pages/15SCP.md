## SSH and SCP Guide: Windows ↔ macOS/Linux

**SCP (Secure Copy Protocol)** uses SSH to securely transfer files between systems using SSH.

**Note:** If you have enabled ssh from the SSH cheat sheet, skip step 1 (Enable and Verify SSH)

This step-by-step guide covers how to enable SSH, transfer files with SCP, and troubleshoot common issues between Windows and macOS/Linux systems.
All examples assume both systems are on the same local network.

---

1. ### Enable and Verify SSH

    * On macOS / Linux Terminal

        * Turn on remote Login (enables SSH server):
        
                sudo systemsetup -setremotelogin on

        * Check status:
            
                systemsetup -getremotelogin

        * Test port 22 listening:

                sudo lsof -iTCP -sTCP:LISTEN -n -P | grep ssh
                    or
                netstat -an | grep “.22”

    * Windows (PowerShell as Admin)                                      

        * Install OpenSSH Server (if needed):
       
                Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0

        * Start and enable the service:
        
                Start-Service sshd
                Set-Service -Name sshd -StartupType ‘Automatic’

        * Verify it’s running:

                Get-Service sshd

        * Allow SSH in firewall (port 22): 
                **Note:** Run one line command or go to Windows Defender to set rule

                New-NetFirewallRule -Name sshd -DisplayName ‘OpenSSH Server (sshd)’ -Enabled True -Direction Inbound -Protocol TCP -Action Allow -LocalPort 22

---

* ### Single File Transfer with SCP 

    * **On Mac/Linux**

    A. Download File from Windows to Mac/Linux (Mac pulls file)

        scp <windows_user>@<windowsIP ex. 192.168.1.xxx>:/Users/<windows_user>/Desktop/file.docx /Users/mac_user/Downloads/

        ex. scp aliceOnWindows@192.168.1.10:/Users/aliceOnWindows/Desktop/alice_file.txt /Users/bobOnMac/Downloads/

        Alternative (Windows path form) if the first command line failed:

        scp <windows_user>@<windowsIP ex. 192.168.1.xxx>:“C:/Users/<windows_user>/Desktop/file.docx” /Users/<mac_user>/Downloads/

    B. Upload File from Mac/Linux to Windows (Mac pushes file)

        scp /Users/mac_user/Desktop/file.docx windows_user@192.168.1.xxx:“C:/Users/windows_user/Downloads/”

    * **On Windows**

    A. Download grom Mac/Linux to Windows (Windows pulls file)

        scp mac_user@192.168.1.xxx:/Users/mac_user/Desktop/file.docx C:\Users\windowsuser\Downloads\

    B. Upload from Windows to Mac/Linux (Windows pushes file)

        scp C:\Users\windows_user\Desktop\file.docx mac_user@192.168.1.243:/Users/mac_user/Downloads/

---

* ### Recursive Folder Transfers (Copy Directories)

From Windows Desktop folder → Mac Downloads (run on Mac):
scp -r windowsuser@192.168.1.186:/Users/windowsuser/Desktop/FolderName /Users/macuser/Downloads/

From Mac Desktop folder → Windows Downloads (run on Mac):
scp -r /Users/macuser/Desktop/FolderName windowsuser@192.168.1.186:“C:/Users/windowsuser/Downloads/FolderName”

From Windows Desktop folder → Mac Downloads (run on Windows):
scp -r C:\Users\windowsuser\Desktop\FolderName macuser@192.168.1.243:/Users/macuser/Downloads/

⸻

5. Quick Service Checks & Troubleshooting

On macOS/Linux

Check if SSH is enabled:
systemsetup -getremotelogin

Restart SSH service:
sudo launchctl kickstart -k system/com.openssh.sshd

Check SSH port listening:
sudo lsof -iTCP -sTCP:LISTEN -n -P | grep ssh

Test connectivity to Windows port 22:
nc -vz 192.168.1.186 22
or
telnet 192.168.1.186 22

On Windows

Check SSH service:
Get-Service sshd

Restart SSH service:
Restart-Service sshd

Check listening ports:
netstat -ano | findstr “:22”

Test connectivity to Mac port 22:
Test-NetConnection -ComputerName 192.168.1.243 -Port 22

⸻

6. Key-Based (Passwordless) Login Setup

Generate a key on Mac/Linux:
ssh-keygen -t ed25519 -f ~/.ssh/id_ed25519 -C “mac-to-win-key”

Copy public key to Windows:

Method A (if ssh-copy-id available):
ssh-copy-id -i ~/.ssh/id_ed25519.pub windowsuser@192.168.1.186

Method B (manual):
On Mac:
cat ~/.ssh/id_ed25519.pub

On Windows (PowerShell as the target user):
mkdir $env:USERPROFILE.ssh
notepad $env:USERPROFILE.ssh\authorized_keys
(paste the public key line, save file)

Set permissions:
icacls $env:USERPROFILE.ssh /grant $env:USERNAME:(R,W)

Restart SSH service:
Restart-Service sshd

Now you can log in without entering a password:
ssh windowsuser@192.168.1.186

⸻

7. Common Problems & Fixes
	1.	Permission denied (publickey,password,keyboard-interactive)
	•	Check correct username (run whoami).
	•	Windows PIN will not work; use account password.
	•	If using keys, ensure authorized_keys is set up correctly.
	2.	Connection refused / no route to host
	•	SSH not running.
	•	Firewall blocking port 22.
	3.	scp: No such file or directory
	•	Check source/destination paths.
	•	Use forward slashes for Windows paths (“C:/Users/…”).
	4.	Publickey only authentication
	•	Ensure PasswordAuthentication yes in sshd_config if needed.
	5.	Permissions denied
	•	Make sure destination folder is writable.
	6.	Path formatting confusion
	•	Try both: C:/Users/… or “C:\Users...”.
	7.	Network not same LAN
	•	Ensure systems can ping each other.
	8.	Interrupted transfers
	•	Use rsync for resume:
rsync -avz -e ssh /Users/macuser/Desktop/Folder/ windowsuser@192.168.1.186:“C:/Users/windowsuser/Downloads/Folder/”
