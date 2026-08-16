# Active-Directory-Project

## Objective
The Active Directory Lab project aimed to establish a controlled, hands-on environment for simulating and detecting real-world cyber attacks against enterprise Windows infrastructure. Using VirtualBox, the lab combined Active Directory, Splunk, and Sysmon to build a functioning domain environment with full security telemetry ingestion. The primary focus was configuring a Windows Server 2022 domain controller, joining a Windows 10 endpoint to the domain, and forwarding Sysmon-enriched event logs into Splunk for analysis. Kali Linux and Atomic Red Team were then used to simulate brute-force attacks and known adversary techniques, allowing for practical detection engineering, log correlation, and investigation of authentication failures and lateral movement indicators. This project was designed to deepen understanding of both blue team monitoring and red team attack simulation within an Active Directory environment.

### Skills Learned
- Building and managing a multi-VM lab environment using VirtualBox.
- Promoting a Windows Server to a domain controller and performing Active Directory configuration.
- Joining and managing domain-joined endpoints, including user, group, and Group Policy management.
- Configuring Sysmon for enhanced endpoint telemetry and integrating it with Splunk for centralized log collection.
- Building and tuning Splunk searches and correlation logic to detect authentication failures, brute-force activity, and lateral movement.
- Simulating adversary behavior using Kali Linux and Atomic Red Team to generate known attack techniques.
- Troubleshooting telemetry ingestion issues, including log source validation and forwarder/connectivity errors.
- Practical understanding of blue team detection workflows and how attacker activity appears in Windows/AD telemetry.

### Tools Used
- **Active Directory (Windows Server 2022)** – domain controller setup, user/group management, and Group Policy configuration.
- **Windows 10** – domain-joined target endpoint for telemetry generation.
- **Splunk** – SIEM platform used for log ingestion, searching, and detection/alerting.
- **Sysmon** – endpoint telemetry generation (process creation, network connections, logon events, etc.) forwarded to Splunk.
- **Kali Linux** – used to simulate brute-force attacks against Active Directory accounts.
- **Atomic Red Team** – used to generate known, mapped attack behaviors (MITRE ATT&CK) for detection testing.
- **VirtualBox** – virtualization platform hosting all lab machines.

### Lessons Learned
- Building and configuring an AD environment from scratch helped reinforce concepts like DCs, OUs, and GPOs.
- Small config details caused the most friction — a single typo in the Splunk Universal Forwarder config, or figuring out how to change the static IP method depending on the Ubuntu Server version, could throw everything off.
- Running attacks and familiarizing myself with how they work made it easier to write effective Splunk searches rather than just knowing about the attack.
- Documenting and screenshotting after building the environment was a mistake. I definitely should have done it during.

## Screenshots
<img width="616" height="575" alt="AD-Project_Diagram" src="https://github.com/user-attachments/assets/85955235-f4ee-4480-9b96-ff84ab363615" />

*Ref 1: Network Diagram*

<img width="637" height="509" alt="kali-attack" src="https://github.com/user-attachments/assets/355bca9d-1b0d-4e8e-9c63-72745861609a" />

*Ref 2: Kali Brute Force Attempt*

<img width="648" height="506" alt="kali-success" src="https://github.com/user-attachments/assets/14c7a909-4159-4070-aa4c-a21e89940764" />

*Ref 3: Kali Brute Force Result*

<img width="1832" height="805" alt="kali-spl" src="https://github.com/user-attachments/assets/64892055-bc92-4d5f-bc40-940a04a8c246" />

*Ref 4: Splunk Log for Kali Linux Failed and Successful Login For The User tsmith*

<img width="855" height="181" alt="ART-execution" src="https://github.com/user-attachments/assets/7fc8dfeb-25f5-49ad-b0fc-561bc8bbcc1b" />

*Ref 5: Atomic Red Team Attempt*

<img width="1147" height="732" alt="atr-result" src="https://github.com/user-attachments/assets/2fecc6cd-5981-4cd5-a74a-5a16ca298802" />

*Ref 6: Atomic Red Team Result*

<img width="1438" height="604" alt="atr-splunk-log" src="https://github.com/user-attachments/assets/577f96b4-89ea-42dd-8ef9-2b020121cee2" />

*Ref 7: Splunk Logging Atomic Red Team Creating NewLocalUser*
