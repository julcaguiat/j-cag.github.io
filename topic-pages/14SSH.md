## **🔑 SSH Connection Cheat Sheet: Windows ↔ Mac/Linux**

This short cheat sheet provides **step-by-step instructions** on how to set up and use SSH to connect between Windows and Mac/Linux machines.

👉 The SSH command syntax is the same across platforms:

*ssh user@IPaddress*

**Note:** The key difference lies in **enabling the SSH server** on the target system.

---

### **🖥️ 1\. Preparing Each System**

#### **⚙️ Windows (as SSH Server)**

1. Open **Settings** → **Apps** → **Optional Features**.

2. Click **Add a feature** → search for **OpenSSH Server** → **Install**.

3. Start the service: Open **PowerShell as Administrator** and run:

   *Get-Service sshd*

   *Start-Service sshd*

4. Allow SSH through the firewall if prompted.

---

#### **🐧 Mac/Linux (as SSH Server)**

**On Linux:**

1. Check if SSH server is installed:

   *sudo apt install openssh-server*

2. Start the service:

   *sudo systemctl enable \--now ssh*

   

**On macOS:**

* Go to **System Preferences** → **Sharing** → enable ✅ **Remote Login**.

---

### **🔗 2\. SSH Command Syntax**

From any client machine, the syntax is always:

*ssh username@IPaddress*

#### Examples:

* **From Windows → Mac/Linux or Windows:**

  *ssh bob@192.168.1.50*

  * First time: may ask to confirm host key → type **yes**  
    * Then enter **bob’s password** (on the target machine).

* **From Mac/Linux → Windows or Mac/Linux:**

  *ssh alice@192.168.1.50*

  * First time: may ask to confirm host key → type **yes**  
    * Then enter **alice’s password** (on the target machine).

### **💡 3\. Notes & Tips**

* 🔑 Replace **username** with the actual account name on the target machine.

* 🌐 Replace **IPaddress** with the machine’s LAN IP:

  * Windows → *ipconfig*

  * Mac/Linux → *ifconfig* or *ip a*

* 🛡️ First connection may ask to confirm the host key → type **yes**.

* 🚪 Use exit to close an SSH session.

---

✨ With this cheat sheet, you can quickly establish secure remote connections between different systems\!

---
🔙 [Back to Home](../index.md) 