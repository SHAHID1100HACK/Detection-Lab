# THREAT HUNTING: DETECTION LAB

## Objective
The Detection Lab project aimed to establish a controlled environment for simulating and detecting cyber attacks. The primary focus was to ingest and analyze logs within a Security Information and Event Management (SIEM) system, generating test telemetry to mimic real-world attack scenarios. This hands-on experience was designed to deepen understanding of network security, attack patterns, and defensive strategies.

## Skills Learned
* **SIEM Mastery:** Advanced understanding of SIEM concepts and practical application.
* **Log Analysis:** Proficiency in analyzing and interpreting network logs.
* **Attack Signatures:** Ability to generate and recognize attack signatures and patterns.
* **Security Fundamentals:** Enhanced knowledge of network protocols and security vulnerabilities.
* **Critical Thinking:** Development of problem-solving skills in a cybersecurity context.

## Tools Used
* **Wazuh:** SIEM system used for log ingestion and analysis.
* **Sysmon:** Advanced telemetry generation tool to create realistic process-level logs.
* **Atomic Red Team:** Adversary simulation library used to execute portable, reproducible attacks.
* **Oracle VirtualBox:** Virtualization platform used to isolate the victim and manager environments.


## ATTACKS AND ALEARTS 

### 1. Windows Event Log Clearing
<img width="1788" height="924" alt="Screenshot from 2025-12-28 18-54-22" src="https://github.com/user-attachments/assets/2c3a064c-d348-4f0c-a282-78a122bba9ce" />

Alert: A Windows log file was cleared (Rule ID: 63104)

Agent: windows_10

Description: This alert was triggered when a user or process attempted to wipe the security, system, or application logs.

Significance: In a real-world attack, this is a major "red flag." It usually indicates an adversary is trying to hide their tracks (Defense Evasion) after performing malicious actions.
\



### 2. Unauthorized Network Port Changes
<img width="1797" height="963" alt="Screenshot from 2025-12-29 00-51-11" src="https://github.com/user-attachments/assets/e6e1e963-02ed-4acb-89b1-bcc616a836f1" />

 Alert: Listened ports status (netstat) changed (Rule ID: 533)

 Agent: shahid

 Description: This alert fired when a new port was opened or an existing one was closed on the system.

 Significance: Monitoring port changes is vital for detecting Persistence or Command and Control (C2). If an attacker opens a back door (like a reverse shell), this alert ensures the activity is logged and flagged.



 ### 3. AppArmor Policy Enforcement

  Alert: Apparmor DENIED (Rule ID: 52002)

  Agent: shahid

  Description: Multiple alerts showing that the Linux AppArmor security module blocked a process from performing an unauthorized action (like reading a sensitive file or executing a restricted binary).
    
  Significance: This demonstrates System Hardening. It shows that even if an attacker gains access, the system's security policies are actively preventing them from escalating privileges or moving laterally.

