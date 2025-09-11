🖧 Why I Use NAT + Internal Network (and Not Bridge or NAT Network) in My pfSense Home Lab

When setting up virtual machines in VirtualBox, you’ll often see options like NAT, NAT Network, or Bridged Adapter. They all provide internet, but the way they do it changes how your lab works. If your goal is to practice with pfSense as a real firewall and gateway, it’s important to understand the difference.

⸻

⚡ NAT Network

With NAT Network, VirtualBox creates its own private subnet for your VMs. Each VM gets an IP address inside that subnet, and they can talk to each other. VirtualBox then translates all their traffic out to the internet through your host.

[ Kali ] ─┐
          │
[ Win10 ]─┘──> VirtualBox NAT Network ──> Host ──> Internet

✔️ VMs can talk to each other
✔️ All VMs get internet
❌ pfSense is bypassed if your lab VMs are directly attached to NAT Network

This setup is fine for quick testing, but if you want pfSense to control traffic, NAT Network isn’t the right choice.

⸻

🌍 Bridged Adapter

With Bridged mode, VirtualBox connects your VM directly to your real physical network. Your VM will appear on the same network as your host machine and get an IP from your home router.

[ Kali ] ──> Your Home Router ──> Internet
[ Win10 ] ──> Your Home Router ──> Internet

✔️ VM acts like a real machine on your home network
✔️ Can talk to other real devices on your LAN
❌ Bypasses pfSense (unless pfSense itself is also bridged and used as the gateway)
❌ Less isolated — you might not want your testing VM directly exposed on your home network

⸻

🔒 Why I Don’t Use NAT Network or Bridged for My Lab VMs

Both NAT Network and Bridged give VMs a “shortcut” to the internet. That means pfSense doesn’t get to do its job. In my pfSense lab, I want all traffic to flow through pfSense, so I set it up like this:
	•	Adapter 1 (NAT): pfSense WAN → internet
	•	Adapter 2 (Internal): pfSense LAN → Kali + Windows VMs
	•	(Optional) Adapter 3 (Host-only): For direct pfSense GUI access from the host

[ Kali  ] ─┐
[ Win10 ] ─┘──> pfSense LAN (Internal Network) ──> pfSense WAN (NAT) ──> Internet

This way, pfSense is the only gateway to the internet, and I can practice firewall rules, routing, and security features without bypasses.

⸻

✅ Key takeaway:
	•	NAT Network = VMs get internet + can talk to each other, but pfSense is skipped.
	•	Bridged Adapter = VMs join your real home network, but pfSense is skipped unless you bridge pfSense too.
	•	NAT + Internal Network = pfSense sits in the middle as a real firewall.