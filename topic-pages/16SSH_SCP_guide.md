## 🔐 File Transfer with SCP: Windows ↔ macOS/Linux 



This step-by-step guide covers how to enable SSH, transfer files with SCP, and troubleshoot common issues between **Windows** and **macOS/Linux** systems.  
All examples assume both systems are on the same **local network**.

---

### 🧩 1. Enable and Verify SSH

#### macOS / Linux (Terminal)
Enable SSH server (Remote Login):

```bash
sudo systemsetup -setremotelogin on
```

Check SSH status:

```bash
systemsetup -getremotelogin
```

Verify port 22 is listening:

```bash
sudo lsof -iTCP -sTCP:LISTEN -n -P | grep ssh
# or
netstat -an | grep ".22"
```

---

#### Windows (PowerShell as Admin)
Install OpenSSH Server (if needed):

```powershell
Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0
```

Start and enable service:

```powershell
Start-Service sshd
Set-Service -Name sshd -StartupType 'Automatic'
```

Verify service is running:

```powershell
Get-Service sshd
```

Allow SSH in firewall (port 22):

```powershell
New-NetFirewallRule -Name sshd -DisplayName 'OpenSSH Server (sshd)' -Enabled True -Direction Inbound -Protocol TCP -Action Allow -LocalPort 22
```

---

## 📦 2. File Transfers with SCP

**SCP (Secure Copy)** uses SSH to securely transfer files between systems.

### A. From Windows → Mac/Linux (Mac pulls file)
```bash
scp <windows_user>@<windows_machine_IP>:/Users/<windows_user>/Desktop/file.docx /Users/<mac_user>/Downloads/
```

Alternative (Windows path form):
```bash
scp <windows_user>@<windows_machine_IP>:"C:/Users/<windows_user>/Desktop/file.docx" /Users/<mac_user>/Downloads/
```

### B. From Mac/Linux → Windows (Mac pushes file)
```bash
scp /Users/<mac_user>/Desktop/file.docx <windows_user>@<windows_machine_IP>:"C:/Users/<windows_user>/Downloads/"
```

### C. From Mac/Linux → Windows (Windows pulls file)
```bash
scp <mac_user>@<mac_IP:/Users/<mac_user>/Desktop/file.docx C:\Users\<windows_user>\Downloads\
```

### D. From Windows → Mac/Linux (Windows pushes file)
```bash
scp C:\Users\<windows_user>\Desktop\file.docx <mac_user>@<mac_IP:/Users/<mac_user>/Downloads/
```

---

## 💻 3. Open an Interactive SSH Shell

### From macOS/Linux → Windows
```bash
ssh <windows_user>@<windows_machine_IP>
```

### From Windows → macOS/Linux
```bash
ssh <mac_user>@<mac_IP
```

---

## 📁 4. Recursive Folder Transfers (Copy Directories)

### From Windows → Mac (run on Mac)
```bash
scp -r <windows_user>@<windows_machine_IP>:/Users/<windows_user>/Desktop/FolderName /Users/<mac_user>/Downloads/
```

### From Mac → Windows (run on Mac)
```bash
scp -r /Users/<mac_user>/Desktop/FolderName <windows_user>@<windows_machine_IP>:"C:/Users/<windows_user>/Downloads/FolderName"
```

### From Windows → Mac (run on Windows)
```bash
scp -r C:\Users\<windows_user>\Desktop\FolderName <mac_user>@<mac_IP:/Users/<mac_user>/Downloads/
```

---

## 🧰 5. Quick Service Checks & Troubleshooting

### macOS/Linux

Check if SSH is enabled:
```bash
systemsetup -getremotelogin
```

Restart SSH service:
```bash
sudo launchctl kickstart -k system/com.openssh.sshd
```

Check SSH port listening:
```bash
sudo lsof -iTCP -sTCP:LISTEN -n -P | grep ssh
```

Test connectivity to Windows port 22:
```bash
nc -vz <windows_machine_IP> 22
# or
telnet <windows_machine_IP> 22
```

---

### Windows

Check SSH service:
```powershell
Get-Service sshd
```

Restart SSH service:
```powershell
Restart-Service sshd
```

Check listening ports:
```powershell
netstat -ano | findstr ":22"
```

Test connectivity to Mac port 22:
```powershell
Test-NetConnection -ComputerName <mac_IP -Port 22
```

---

## 🔑 6. Key-Based (Passwordless) Login Setup

Generate a key on Mac/Linux:
```bash
ssh-keygen -t ed25519 -f ~/.ssh/id_ed25519 -C "mac-to-win-key"
```

Copy public key to Windows:

### Method A — Using `ssh-copy-id` (if available)
```bash
ssh-copy-id -i ~/.ssh/id_ed25519.pub <windows_user>@<windows_machine_IP>
```

### Method B — Manual Copy

On Mac:
```bash
cat ~/.ssh/id_ed25519.pub
```

On Windows (PowerShell as target user):
```powershell
mkdir $env:USERPROFILE\.ssh
notepad $env:USERPROFILE\.ssh\authorized_keys
```
👉 Paste the public key line, then **save file**.

Set permissions:
```powershell
icacls $env:USERPROFILE\.ssh /grant $env:USERNAME:(R,W)
```

Restart SSH service:
```powershell
Restart-Service sshd
```

Now login without password:
```bash
ssh <windows_user>@<windows_machine_IP>
```

---

## ⚠️ 7. Common Problems & Fixes

| Issue | Possible Cause | Solution |
|-------|----------------|-----------|
| **Permission denied (publickey,password,keyboard-interactive)** | Wrong username / bad key setup | Run `whoami` to confirm username. Check `authorized_keys`. |
| **Windows PIN doesn’t work** | SSH uses account password only | Use account password, not PIN. |
| **Connection refused / No route to host** | SSH not running or firewall blocking | Ensure SSH service is running; port 22 open. |
| **scp: No such file or directory** | Wrong file path or format | Verify file path; use forward slashes (`C:/Users/...`). |
| **Publickey only authentication** | Password authentication disabled | Edit `sshd_config` → `PasswordAuthentication yes`. |
| **Permission denied (folder write)** | Target folder not writable | Choose a writable directory. |
| **Path confusion (slashes)** | Incompatible path syntax | Try both `C:/Users/...` and `"C:\Users..."`. |
| **Different network segment** | Devices not on same LAN | Ensure both systems can `ping` each other. |
| **Interrupted transfers** | Unstable connection | Use `rsync` for resumable transfer: |

```bash
rsync -avz -e ssh /Users/<mac_user>/Desktop/Folder/ <windows_user>@<windows_machine_IP>:"C:/Users/<windows_user>/Downloads/Folder/"
```

---
📘 *Author:* [j-cag@github.io](https://j-cag.github.io)  
💡 *Category:* Home Lab & Networking Tutorials
---
[🔙 Back to Home](../index.md)


