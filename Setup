# ⚙️ SOC Home Lab Setup Guide (Wazuh)

This guide provides a simple step-by-step process to recreate the SOC home lab using Wazuh.

---

##  Requirements

* VirtualBox (or any virtualization software)
* Minimum 8 GB RAM (recommended)
* Ubuntu ISO (for Wazuh server)
* Windows/Linux system (for agent)

---

##  Setup Steps

### 1. Install VirtualBox

Download and install VirtualBox from the official website.

---

### 2. Create Ubuntu VM (Wazuh Server)

* Create a new VM
* Select **Linux → Ubuntu (64-bit)**
* Allocate:

  * RAM: 4 GB (minimum)
  * CPU: 2 cores
* Attach Ubuntu ISO and complete installation

---

### 3. Install Wazuh (All-in-One)

Run the following commands in the Ubuntu VM:

```bash
sudo apt update && sudo apt upgrade -y
curl -sO https://packages.wazuh.com/4.7/wazuh-install.sh
sudo bash wazuh-install.sh -a
```

After installation:

* Note down the **username and password**
* Access dashboard at:

```
https://<WAZUH-SERVER-IP>
```

---

### 4. Configure Wazuh Agent (Windows/Linux)

Download Wazuh agent from:
https://packages.wazuh.com/

Install the agent and provide:

* **Wazuh Manager IP**

---

### 5. Connect Agent to Manager

On the agent machine:

* Start the agent service
* Ensure it connects to the Wazuh server

Verify connection from the dashboard:

* Navigate to **Agents → Active**

---

### 6. Verify Logs in Dashboard

* Open Wazuh Dashboard
* Go to **Security Events**
* Run basic commands on the agent machine:

```bash
whoami
net user
ipconfig /all
```

* Confirm logs are visible

---

## Outcome

At this point, your SOC lab should be fully functional:

* Wazuh server running
* Agent connected
* Logs flowing into dashboard

---

## Notes

* Restart Wazuh services if logs are not visible
* Ensure correct IP configuration between VMs
* Small configuration errors may stop services — always check logs

---

## Next Steps

* Integrate Sysmon for advanced logging
* Create custom detection rules
* Simulate attacks and analyze alerts

---
