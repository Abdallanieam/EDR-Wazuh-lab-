# Wazuh EDR Lab – Endpoint Monitoring & Security

## 📌 Project Overview

This project demonstrates a practical **Endpoint Detection and Response (EDR)** lab using Wazuh to monitor Windows endpoints, collect security-related data, and observe endpoint activity through a centralized dashboard.

The lab includes a Wazuh server, Windows 10 endpoints, and a Kali Linux machine used to simulate security testing in an isolated environment.

## 🎯 Objectives

- Deploy and access the Wazuh dashboard.
- Install and connect the Wazuh agent to Windows endpoints.
- Monitor endpoint status and system information.
- Review security events and endpoint activity.
- Understand how EDR supports threat detection and investigation.
- Explore security testing in a controlled lab environment.

## 🛠️ Technologies Used

- **Wazuh** – Security monitoring and threat detection platform
- **Wazuh Agent** – Endpoint data collection
- **Windows 10** – Monitored endpoints
- **Kali Linux** – Security testing machine
- **Hydra** – Password auditing and brute-force testing tool
- **VMware Workstation** – Virtualization platform

## 🗺️ Lab Topology

The lab contains the following components:

| Device | Role | IP Address |
|---|---|---|
| Wazuh Server | Central monitoring and dashboard | `10.41.188.23` |
| Windows 10 | Monitored endpoint | `10.41.188.132` |
| Kali Linux | Security testing machine | `10.41.188.224` |
| Virtual Switch | Network connectivity | Shared lab network |

All devices are connected through the virtual network shown in the lab topology.

## ⚙️ Implementation

### 1. Deploy the Wazuh Server

The Wazuh server provides centralized monitoring and a dashboard for viewing connected agents and their collected security data.

The dashboard is accessed through:

```text
https://10.41.188.23
```

Use the appropriate credentials configured during installation.

### 2. Deploy the Windows Agent

The Wazuh dashboard provides an agent deployment wizard for selecting the operating system and configuring the manager address.

For this lab:

1. Select Windows as the endpoint operating system.
2. Enter the Wazuh server address.
3. Generate or obtain the installation command.
4. Run the installation command in an elevated PowerShell session.
5. Start the Wazuh service.
6. Verify that the agent connects to the manager.

Example service command:

```powershell
NET START Wazuh
```

The exact installation command depends on the Wazuh version and deployment configuration.

### 3. Verify Agent Connectivity

Open the Wazuh dashboard and navigate to the agent management page.

Verify that the Windows endpoint appears in the agent list and reports an active status.

The dashboard can display information such as:

- Agent name and IP address
- Operating system
- Agent version
- Connection status
- Endpoint inventory

### 4. Monitor Endpoint Activity

Open the details page for a connected endpoint.

Review the available monitoring information, including system inventory, security events, and other collected data supported by the configured Wazuh modules.

This helps demonstrate how endpoint information can be collected and analyzed centrally.

### 5. Security Testing with Kali Linux

The lab topology includes Kali Linux with Hydra for controlled security testing.

In an authorized lab, password-auditing exercises can help demonstrate authentication risks and investigate related endpoint or authentication events.

**Important:** The presence of Kali Linux and Hydra in the topology does not by itself confirm that a successful attack was performed or detected. Detection depends on the test performed, the monitored service, and the configured logging and detection rules.

## 🔍 EDR Workflow

1. **Data Collection:** The Wazuh agent collects supported endpoint data.
2. **Centralized Monitoring:** The Wazuh manager processes incoming data.
3. **Event Analysis:** Configured decoders and detection rules identify relevant activity.
4. **Alert Generation:** Events matching configured rules may generate alerts.
5. **Investigation:** Administrators review alerts and endpoint information in the dashboard.
6. **Response:** Security personnel investigate and take appropriate actions.

Wazuh provides monitoring and detection capabilities. Automated response actions require appropriate configuration.

## 🛡️ Key Security Benefits

- Centralized endpoint visibility
- Security event monitoring
- Endpoint inventory collection
- Detection of activity matching configured rules
- Support for incident investigation
- Improved awareness of endpoint security status

## 📚 Key Takeaways

- EDR focuses on endpoint visibility, detection, and investigation.
- Wazuh agents collect data from monitored systems.
- The Wazuh dashboard provides a centralized view of agents and security information.
- Detection results depend on the available logs, enabled modules, and configured rules.
- Security testing should be performed only on systems you own or are authorized to test.

## 👨‍💻 Author

**Abdalla Mohamed Nieam**

Network Engineering | Network Security | Endpoint Monitoring

GitHub: [Abdallanieam](https://github.com/Abdallanieam)

---

*This project was implemented in a virtual lab using Wazuh, Windows 10, and Kali Linux for practical learning about endpoint monitoring and security detection.*
