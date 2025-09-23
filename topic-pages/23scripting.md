🖥️ Learn Scripting for Pentesting — Setup + 8-Week Study Plan

A concise, practical path for learning scripting specifically for pentesting. Follow the 1–2 hrs/day template and apply everything in an isolated lab (VirtualBox / VMs / TryHackMe). Beginner-friendly.

⸻

⚡ Quick setup: Python virtualenv + TryHackMe

Why this first? 🐍 A virtualenv keeps your pentest tooling and Python packages isolated so you can experiment without breaking system Python. TryHackMe provides safe, hands-on rooms to apply what you learn.

1️⃣ Install Python 3

Linux / macOS (Ubuntu example)

sudo apt update
sudo apt install -y python3 python3-venv python3-pip

macOS (Homebrew)

brew install python

Windows
	1.	Download & install Python 3 from https://www.python.org/downloads/
	2.	During install check “Add Python to PATH” ✅

Verify:

python3 --version   # or python --version
pip3 --version      # or pip --version


⸻

2️⃣ Create a project folder and virtualenv

Replace ~/pentest-scripts with your path.

Linux / macOS

mkdir -p ~/pentest-scripts
cd ~/pentest-scripts
python3 -m venv .venv
source .venv/bin/activate

Windows (PowerShell)

mkdir C:\Users\you\pentest-scripts
cd C:\Users\you\pentest-scripts
python -m venv .venv
.\.venv\Scripts\Activate.ps1

	•	After activation you’ll see (.venv) in your prompt 🔹
	•	To leave: deactivate ❌

⸻

3️⃣ Install useful Python packages

pip install --upgrade pip
pip install requests paramiko scapy python-nmap tqdm
# optional later: pip install pwntools

Save dependencies:

⸻

4️⃣ Git + Editor
	•	Install Git and initialize a repo in your project folder:

git init
git add .
git commit -m "initial environment"

	•	VS Code 💻: install the Python extension → Ctrl+Shift+P → Python: Select Interpreter → choose .venv
⸻

5️⃣ Install basic CLI tools (optional / recommended)

On Ubuntu:

On Kali these are usually preinstalled ⚡

⸻

6️⃣ TryHackMe — sign up & quick start
	•	Create a free account: https://tryhackme.com 🌐
	•	Start with recommended rooms:
	•	Python for Pentesters / Scripting for Pentesters
	•	Linux Fundamentals / Bandit
	•	Use TryHackMe labs to test your scripts safely 🛡️


⸻

7️⃣ Quick sanity test script

Save as log_summary.py in your project:

#!/usr/bin/env python3
# log_summary.py - count top IPs from a text log (lab-only)

from collections import Counter
import argparse, re

IP_RE = re.compile(r'(\d+\.\d+\.\d+\.\d+)')

def top_ips(path, n=10):
    cnt = Counter()
    with open(path, 'r', errors='ignore') as f:
        for line in f:
            m = IP_RE.search(line)
            if m:
                cnt[m.group(1)] += 1
    for ip, c in cnt.most_common(n):
        print(f"{ip}\t{c}")

if __name__ == "__main__":
    p = argparse.ArgumentParser()
    p.add_argument("file", help="log file to parse")
    p.add_argument("-n", type=int, default=10)
    args = p.parse_args()
    top_ips(args.file, args.n)

Run:

python log_summary.py /path/to/sample.log -n 10


⸻

🗓️ 8-Week Study Plan (1–2 hrs/day)

Follow the Day template:
10m review → 30–45m lesson → 30–60m hands-on lab/script → 10–15m document & commit 📝

⸻

Week 1 — Python fundamentals 🐍
	•	Resource: Automate the Boring Stuff with Python
	•	Focus: variables, lists/dicts, control flow, functions, file I/O, argparse, logging
	•	Project: log_summary.py → CSV output


⸻

Week 2 — Bash & Linux toolchain 🖥️
	•	Resource: OverTheWire — Bandit
	•	Focus: grep, awk, sed, cut, xargs, ssh, cron
	•	Project: host_scan.sh that runs nmap and collects results

⸻

Weeks 3–4 — Networking scripting & Web automation 🌐
	•	Resources:
	•	TryHackMe “Scripting for Pentesters / Python for Pentesters” — https://tryhackme.com
	•	PortSwigger Web Security Academy — https://portswigger.net/web-security
	•	Focus: socket, concurrent scanners, requests, basic fuzzing, parsing HTTP responses
	•	Projects: TCP scanner, discover.py probing /admin, /login, /robots.txt

⸻

Week 5 — SSH / paramiko / automation 🔑
	•	Resources: TryHackMe + GitHub paramiko examples
	•	Focus: SSH automation (run commands, SFTP), remote collection, error handling
	•	Project: multi-host command runner that saves per-host outputs

⸻

Week 6 — PowerShell / Windows scripting ⚡
	•	Resource: Microsoft Learn — PowerShell
	•	Focus: Get-Process, Get-Service, Get-WinEvent, remoting, CSV export
	•	Project: PS script collecting system info + event snippets

⸻

Week 7 — Post-exploit & pivoting 🕵️‍♂️
	•	Resource: TryHackMe pivoting/C2 rooms + lab practice
	•	Focus: reverse shells (lab only), SSH SOCKS, socat, proxychains
	•	Project: route browser traffic through compromised VM

⸻

Week 8 — Final project 🎯
	•	Combine parsing logs, recon (nmap + Python), pivoting, reporting
	•	Targets: TryHackMe / PortSwigger safe labs
	•	Deliverable: Git repo with README, sample outputs, usage instructions

⸻

🔗 Quick links to start now
	•	Automate the Boring Stuff 🐍
	•	TryHackMe 🛡️
	•	PortSwigger Web Security Academy 🌐
	•	OverTheWire Bandit 🖥️
	•	Microsoft Learn — PowerShell ⚡

⸻

📌 How to follow like a course
	1.	Daily template: 10m review → 30–45m lesson → 30–60m lab → 10–15m commit/docs
	2.	Apply scripts in TryHackMe rooms
	3.	Keep all code in a Git repo + one-paragraph README per script

⸻

✅ Final tips
	•	Start with Automate the Boring Stuff + Bandit to cover Weeks 1–2 quickly
	•	Apply scripts in guided TryHackMe labs
	•	Keep your lab isolated (Host-only / Internal networks)
	•	Never test external systems without permission 🛑

⸻

📝 License / safety note

All code and labs are for learning in isolated environments only. Do not scan or attack third-party systems without explicit permission.