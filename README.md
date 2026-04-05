# Install Wazuh (Indexer + Server + Dashboard) on Ubuntu Server

**Hardware:** MacBook M4  

**Software:** UTM

**Goal:** Deploy a functional SIEM server to monitor endpoints (Windows, Linux, macOS). Quick, free, ready-to-use Open Source SIEM / XDR

## Step-by-Step Installation Guide

### 1. Download and Install Wazuh
- Open Ubuntu Server Terminal. 

Here is a [guide to install & setup Ubuntu Server](https://github.com/spf-13/ubuntu-server-utm)


- Download the Wazuh installation assistant
```
curl -s0 https://packages.wazuh.com/4.14/wazuh-install.sh
```
- Run the installer
```
sudo bash wazuh-install.sh -a
```
- Wait for the installation to complete, **at the end you will receive the username and password.** You can then access the Wazuh Dashboard at:
``` https://[your-server-ip]:443 ```
- You can check Wazuh Status with:
```
sudo systemctl status wazuh-indexer wazuh-manager wazuh-dashboard --no-pager
```

### 2. Access the Dashboard
- Open browser
- Access: ```https://[your-server-ip]:443```
- Login with "username" and "password" shown at the end of the installation.

### 3. BONUS Change Your Password!
- Open Ubuntu Server Terminal
- Change directory to usr/share/wazuh-indexer/plugins/opensearch-security/tools/
```
cd usr/share/wazuh-indexer/plugins/opensearch-security/tools/
```
- List files in the current directory
```
ls
```
- You should see ```wazuh-passwords-tool.sh```
- Change your password with command "bash wazuh-passwords-tool.sh -u **username** -p **newpassword**"
```
bash wazuh-passwords-tool.sh -u admin -p Newpass123..!
```

# BONUS 2 
Useful COMMANDS
### Start/stop services
```
sudo systemctl start wazuh-indexer
```
```
sudo systemctl stop wazuh-indexer
```
```
sudo systemctl start wazuh-manager
```
```
sudo systemctl stop wazuh-manager
```
```
sudo systemctl start wazuh-dashboard
```
```
sudo systemctl stop wazuh-dashboard
```
### List connected agents
```
sudo /var/ossec/bin/agent_control -l
```
### List all agents
```
sudo /var/ossec/bin/manage_agents -l
```
### # Extract key for agent ID 001
```
sudo /var/ossec/bin/manage_agents -e 001
```

## Screenshots
<img width="815" height="580" alt="Screenshot 2026-04-05 at 11 21 50 AM" src="https://github.com/user-attachments/assets/b79fe828-f39a-4764-a34f-77f3813cee47" />
<img width="821" height="583" alt="Screenshot 2026-04-05 at 11 25 18 AM" src="https://github.com/user-attachments/assets/ddcf37f9-395d-405b-9678-22139817be54" />
<img width="1278" height="838" alt="Screenshot 2026-04-05 at 11 27 44 AM" src="https://github.com/user-attachments/assets/23cbb0bd-7d29-49d6-af71-f0499f46cde1" />
<img width="1281" height="840" alt="Screenshot 2026-04-05 at 11 28 14 AM" src="https://github.com/user-attachments/assets/79a97052-85dc-4b8c-b249-1a8e34705905" />
<img width="1281" height="842" alt="Screenshot 2026-04-05 at 11 28 27 AM" src="https://github.com/user-attachments/assets/9308b066-133e-4d54-b9f9-0e77b2f20345" />
<img width="1279" height="841" alt="Screenshot 2026-04-05 at 11 29 13 AM" src="https://github.com/user-attachments/assets/f52e0769-ed60-4194-a7f3-04f92a6bb33e" />
<img width="1278" height="837" alt="Screenshot 2026-04-05 at 11 29 26 AM" src="https://github.com/user-attachments/assets/9027096a-39ef-4a0e-a451-67df540ace40" />
<img width="816" height="576" alt="Screenshot 2026-04-05 at 12 29 24 PM" src="https://github.com/user-attachments/assets/fec46592-330b-4428-8666-5b1d4f84390b" />


## Useful for
- Wazuh SIEM deployment
- Monitoring endpoints
- Portfolio project 

This repo shows how I install Wazuh Indexer-Server-Dashboard on Ubuntu Server, change the password and more useful commands




