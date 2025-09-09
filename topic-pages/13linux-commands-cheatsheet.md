# 🐧 Essential Linux Commands for Beginners ☁️

If you’re starting your journey in Linux—whether for **cybersecurity, networking, or IT skills**—mastering the terminal is key. The command line might seem intimidating, but with practice, it becomes your most powerful tool. Here’s a **visual, easy-to-skim guide** to essential Linux commands for beginners.

---

## 🧭 Navigation
- `pwd` → Show current directory  
- `ls` → List files  
- `ls -l` → Long listing with details  
- `ls -a` → Include hidden files  
- `cd <directory>` → Change directory  
- `cd ..` → Move up one level  
- `cd ~` → Go to home directory  

---

## 📂 File & Directory Management
- `mkdir <folder>` → Create a folder  
- `touch <file>` → Create an empty file  
- `cp <source> <destination>` → Copy a file or folder  
- `mv <source> <destination>` → Move or rename  
- `rm <file>` → Delete a file  
- `rm -r <folder>` → Delete a folder recursively  

---

## 📄 Viewing & Editing Files
- `cat <file>` → View file content  
- `less <file>` / `more <file>` → Scroll through files  
- `nano <file>` → Simple text editor  
- `vi <file>` / `vim <file>` → Advanced text editor  

---

## 🔍 Searching
- `find <path> -name "<pattern>"` → Search for files  
- `grep "<text>" <file>` → Search inside a file  
- `grep -r "<text>" <folder>` → Recursive search in a folder  

---

## 💻 System Information
- `whoami` → Display current user  
- `uname -a` → Display system info  
- `top` / `htop` → Monitor processes  
- `df -h` → Check disk usage  
- `free -h` → Check memory usage  

---

## 🌐 Networking
- `ping <host>` → Test connectivity  
- `ip a` / `ifconfig` → View network interfaces  
- `netstat -tuln` / `ss -tuln` → Show active connections  
- `curl <URL>` / `wget <URL>` → Download content  

---

## 📦 Package Management (Debian/Ubuntu)
- `sudo apt update` → Update package list  
- `sudo apt upgrade` → Upgrade installed packages  
- `sudo apt install <package>` → Install a package  
- `sudo apt remove <package>` → Remove a package  

---

## 🔐 Permissions & Ownership
- `chmod <permissions> <file>` → Change file permissions  
- `chown <user>:<group> <file>` → Change file owner  
- `sudo <command>` → Execute as superuser  

---

## ⚙️ Miscellaneous
- `history` → Show command history  
- `clear` → Clear the terminal  
- `exit` → Exit the terminal  

---

💡 **Tip:** Practice these commands in a safe environment like a **Linux VM or cloud lab**. The more you use them, the more natural the terminal will feel.

---
<p>Download the Linux Commands Guide:</p>
<a href="../downloadables/linux-commands.pdf" 
   download="linux-commands-guide.pdf"
   type="application/pdf">
   📥 Download PDF
</a>

🔙 [Back to Home](../index.md) 