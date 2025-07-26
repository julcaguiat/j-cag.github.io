**🛡️ How to Install Wazuh SIEM on Ubuntu Server**

> If you\'re building a **home lab** to sharpen your cybersecurity
> skills, installing a Security
>
> Information and Event Management (SIEM) tool like **Wazuh** is one of
> the most valuable
>
> setups you can add. Wazuh gives you deep insight into system activity,
> logs, threats, and
>
> even file changes across your environment --- all from a central
> dashboard. It\'s a practical
>
> way to learn how real-world security monitoring works, and it\'s
> commonly used by
>
> professionals in SOC and blue team roles.
>
> 💡 **Tip:** Keep an **AI assistant** like ChatGPT handy while doing
> this setup. It can help
>
> troubleshoot errors, explain configs, or even generate commands and
> regex patterns
>
> on the fly --- especially helpful when logs or certificates throw
> unexpected issues!

## 📎 Step 1: Install Wazuh Components: Manager, Indexer, filebeat, and Dashboard

- **Start** Ubuntu-Wazuh-Server VM on VirtualBox

- **Log-in**

1.  Once logged-in, **type the following commands in order**:

> sudo apt update && sudo apt upgrade -y
>
> sudo apt install curl apt-transport-https lsb-release gnupg -y
>
> curl -sO https://packages.wazuh.com/4.8/wazuh-install.sh
>
> chmod +x wazuh-install.sh
>
> sudo ./wazuh-install.sh -a

- **NOTE**: Installation takes 10 -- 15 minutes.

2.  **!!! IMPORTANT**: After installation, copy or take a picture of the
    given credentials

(**User** and **Password**). You will need them to access Wazuh's

web interface ()

> ![](images/5wazuh2-images/1.png){width="5.476923665791776in"
> height="2.8701235783027124in"}

3.  Verify if Services are active:

> sudo systemctl status wazuh-manager
>
> sudo systemctl status wazuh-indexer
>
> sudo systemctl status filebeat
>
> sudo systemctl status wazuh-dashboard

- Output should look like the image below:

![](images/5wazuh2-images/2.png){width="5.491228127734034in"
height="2.8923075240594924in"}

## 🌐 Step 4: Configure opensearch_dashboards.yml and opensearch.yml files 

**(To enable browser access to dashboard)**

1.  Get your Ubuntu-Wazuh-Server IP address.

> Type: **ip a**
>
> Search for: **inet** (this is the server's ip address)

2.  Navigate to the opensearch_dashboards.yml file

    - File Location: /etc/wazuh-dashboard/opensearch_dashboards.yml

    - To navigate to the target file:

> **sudo su**
>
> **cd /**
>
> **cd /etc/wazuh-dashboard**

- To check if the file exists:

> **ls**

- To open the file for editing configuration:

> **nano opensearch_dashboards.yml**
>
> ![]( images/5wazuh2-images/3.png){width="5.469231189851269in"
> height="2.8847550306211724in"}

- Replace the opensearch.hosts IP address with your Server's IP address

- Close the file: **ctrl + o**, then **enter**, then **control + x**

> ![](images/5wazuh2-images/4.png){width="5.520844269466317in"
> height="2.946153762029746in"}

3.  Navigate to the opensearch.yml file

    - File Location: /etc/wazuh-indexer/opensearch.yml

    - To navigate to the target file:

> **cd /**
>
> **cd /etc/wazuh-indexer**

- To check if the file exists:

> **ls**

- To open the file for editing configuration:

> **nano opensearch.yml**

- Replace the network.host IP address with **0.0.0.0**

- Close the file: **ctrl + o**, then **enter**, then **control + x**

> ![](images/5wazuh2-images/5.png){width="5.526264216972878in"
> height="2.876923665791776in"}

## 🔐 Step 6: Access the Wazuh Dashboard

- After configuration, open a browser on the host (Windows)

1.  Visit: https://\<**Ubuntu-Server-IP**\>:443

2.  Accept the security warning: click **Advanced...**

![](images/5wazuh2-images/6.png){width="5.509370078740157in"
height="3.0615387139107613in"}

> ![](images/5wazuh2-images/7.png){width="5.507692475940507in"
> height="3.079830489938758in"}

3\. Log in with:

• Username: **admin**\
• Password: \<**password was given after wazuh installation, hope you
saved it**\>

> ![](images/5wazuh2-images/8.png){width="5.497130358705162in"
> height="3.0615376202974627in"}

- **The Wazuh Dashboard!**

> ![](images/5wazuh2-images/9.png){width="5.4704265091863515in"
> height="3.053845144356955in"}

## 🎉 Done!

You've now installed Wazuh with the Wazuh Dashboard on an Ubuntu Server
VM.

The next tutorial will guide you on how to install wazuh agents on the
Kali-Linux VM

and the Windows10 VM for a full Wazuh SIEM setup.
