# SOC Simulation Lab

## Objective

The SOC Simulation Lab project is designed to create a realistic Security Operations Center environment using open-source tools. The main goal is to simulate cyber attacks, collect and analyze security logs, and develop the ability to detect, investigate, and respond to threats within a controlled setting. This project helps build foundational SOC skills including alert tuning, incident triage, and network monitoring.

---

## Skills Learned

- Hands-on experience setting up and managing SOC environments  
- Proficiency in ingesting and analyzing logs from multiple sources  
- Understanding of cyber attack simulation and detection techniques  
- Ability to tune alerts and reduce false positives  
- Incident triage and basic investigation workflows  

---

## Tools Used

- **Wazuh** (SIEM for log ingestion and alerting)  
- **Security Onion** (SOC platform with Suricata, Zeek, Kibana, etc.)  
- **Wireshark** (network packet capture and analysis)  
- **Suricata** (signature-based IDS)  
- **Zeek** (network flow analysis)  
- **Sysmon** and **Windows Event Viewer** (endpoint telemetry)  
- **Atomic Red Team** (attack simulation)  
- **VirtualBox** (virtual lab environment)  

---

## Lab Environment

- **Windows 10 VM** — Target machine for simulated attacks  
- **Wazuh Server** — Deployed on Amazon Linux 2 for host-based monitoring  
- **Security Onion** — Separate VM running Zeek, Suricata, and Kibana  
- **Networking** — All VMs are connected via a Bridged VirtualBox network  
- **Sysmon** — Installed on Windows for endpoint logging  

> 📌 See the network diagram here: `docs/environment-diagram.png`

---

## Project Structure

```plaintext
📁 docs/             → Diagrams and high-level overview  
📁 setup/            → Configuration steps for each tool and system  
📁 attacks/          → Attack plans and logs 
📁 analysis/         → Detection results and screenshots  
📁 reports/          → Executive summary and full report  
```

---

## Attack Simulations

Simulated real-world attack techniques using Atomic Red Team on the Windows 10 VM:

| Technique ID | Description                           |
|--------------|---------------------------------------|
| T1003        | Credential Dumping                    |
| T1059        | PowerShell Execution                  |
| T1547        | Persistence via Scheduled Tasks       |

All attacks were monitored and logged using Wazuh and Security Onion to test detection and analysis workflows.

---

## Detection Results

- ✅ **Wazuh** detected suspicious PowerShell behavior and credential access  
- ✅ **Sysmon** logged parent-child process trees and registry modifications  
- ✅ **Suricata** generated alerts for outbound suspicious network traffic  
- ✅ **Zeek** flagged abnormal DNS queries and connection anomalies  
- ✅ **Wireshark** confirmed HTTP-based command & control behavior  

---

## License

This project is licensed under the [MIT License](LICENSE).

---

## Author

<div align="center">

**Timothy Mushinskiy**  
[GitHub](https://github.com/tmushinskiy) | [LinkedIn](https://www.linkedin.com/in/timothy-mushinskiy)

</div>
