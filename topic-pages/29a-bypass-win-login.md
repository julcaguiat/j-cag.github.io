### 🔐 Resetting Windows Password | Disabling PIN Login (Windows 10)

**Using Ubuntu Live USB + chntpw**

This guide explains how to reset a Windows local or Microsoft account password and disable the PIN login (Windows Hello), using free tools and an Ubuntu Live USB environment.

---
**🛠️ Requirements:**
- Another working computer (to create the bootable USB)
- A blank USB stick (≥ 8GB)
- Ubuntu Desktop ISO 
- Rufus to create the bootable USB
- Internet access during Ubuntu Live session (to install chntpw)

---
####  Part 1: Create Ubuntu Live USB 
1.	Download Ubuntu 24.04.3 LTS ISO
From: https://ubuntu.com/download/desktop

2.  Download Rufus 

2.	Create USB with Rufus (on Windows)
    - Insert USB and open Rufus
	- Device: Your USB
	- Boot selection: Ubuntu ISO
	- Partition scheme: MBR
	- File system: FAT32
	- Click Start, accept defaults

⸻

#### Part 2: Boot Locked Computer from USB 
	1.	Insert USB into the locked computer
	2.	Turn on the PC and press ESC repeatedly until the startup menu appears
	3.	Press F12 → Select USB device (UEFI preferred)
	4.	Choose: “Try Ubuntu” (do not install)

⸻

🌐 Part 3: Connect to Internet (for installing chntpw)
	1.	Click Wi-Fi icon (top-right corner)
	2.	Connect to a network
	3.	Confirm internet with:
ping -c 2 google.com


⸻

🔧 Part 4: Install chntpw Tool

Open Terminal (Ctrl + Alt + T) and run:

sudo apt update
sudo apt install chntpw



⸻

💽 Part 5: Find and Mount the Windows Partition
	1.	Identify the main Windows partition (usually the largest NTFS drive):
lsblk -f
sudo lsblk -o NAME,FSTYPE,SIZE,LABEL,MOUNTPOINT
Example output:
nvme0n1p3 ntfs  118.3G  Microsoft basic data



sudo apt
2.	Mount the Windows drive:

sudo mkdir /mnt/win
sudo mount -t ntfs-3g /dev/nvme0n1p3 /mnt/win

3.	Confirm the SAM file is present:
ls /mnt/win/Windows/System32/config/


⸻

🔐 Part 6: Reset the Password Using chntpw
	1.	Launch the tool:

sudo chntpw -i /mnt/win/Windows/System32/config/SAM

	2.	Follow the menu:
	•	Type 1 → Edit user data and passwords
	•	Type the username or RID
	•	Type 1 → Clear (blank) password
	•	Type 3 → Promote user to admin (optional)
	•	Type 4 → Unlock user (if locked)
	•	Type ! → Exit user editor
	•	Type q → Quit
	•	Type y → Save changes

⸻

🚫 Optional (Recommended): Disable Windows Hello (PIN Login)

Even with a blank password, Windows Hello may still require a PIN. To disable it:

🔨 Delete the Hello settings folder:
sudo rm -rf /mnt/win/Windows/ServiceProfiles/LocalService/AppData/Local/Microsoft/Ngc

	•	This removes all saved PINs, fingerprints, and facial data
	•	Windows will default to password login

⸻

🔁 Part 7: Reboot and Log In
	1.	Reboot the system:
sudo reboot

	2.	Remove the USB when prompted
	3.	On the Windows login screen:
	•	Click Sign-in options
	•	Choose the password icon
	•	Press Enter (no password)

⸻

✅ Final Result

You are now logged into Windows with:
	•	🔓 A blank password
	•	❌ No PIN required
	•	🛠️ Optionally promoted to Admin



———————————————————————————————————————
NOTES:

chntpw stands for:

CHange NT (Windows NT) Password

⸻

🧩 Breakdown:
	•	ch → change
	•	nt → Windows NT-based systems (like Windows XP, 7, 10, 11, etc.)
	•	pw → password

So, chntpw = change NT password

⸻

🛠️ What Does chntpw Do?

It’s a Linux-based command-line utility used to:
	1.	Clear or reset Windows local account passwords
	2.	Unlock locked-out accounts
	3.	Promote a standard user to an administrator
	4.	Edit user registry data

It works offline, by directly modifying the SAM (Security Account Manager) file in the Windows registry — where local passwords and user data are stored.

⸻

🧠 Important Notes:
	•	It does not decrypt the password — it simply removes it or changes flags
	•	It only works on local accounts, not cloud-based Microsoft accounts (though you can work around those too)
	•	Doesn’t need to know the original password


—
select usb
connect to wifi
choose: ‘try ubuntu’ —  !do not download
open terminal: ping google.com (check internet connectivity)

on terminal run command: 
		sudo apt update
	   sudo apt install chntpw       
		lsblk -f
			
sudo mkdir /mnt/win
sudo mount -t ntfs-3g /dev/nvme0n1p3 /mnt/win
3.	Confirm the SAM file is present:
ls /mnt/win/Windows/System32/config/
sudo chntpw -i /mnt/win/Windows/System32/config/SAM
		sudo chntpw -i /mnt/Windows/System32/config              