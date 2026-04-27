 MITRE ATT&CK Mapping


 Project Overview

This project analyzes real-world attack data captured using the T-Pot honeypot platform over a two-month period. The analysis reveals automated botnet-driven attacks targeting exposed services such as SSH and Telnet.

The findings demonstrate a complete attack lifecycle including brute-force access, system reconnaissance, privilege escalation, persistence mechanisms, and malware deployment.

The project further maps these observed behaviours to the MITRE ATT&CK framework to provide structured threat intelligence insights.


The observed attack follows a complete intrusion lifecycle consistent with automated botnet behaviour (Mirai/Tsunami). The activities were mapped to the MITRE ATT&CK framework as follows:

| Attack Stage          | Observed Behaviour                                    | MITRE Technique                           |
| --------------------- | ----------------------------------------------------- | ----------------------------------------- |
| Initial Access        | SSH brute-force login attempts using weak credentials | T1110 – Brute Force                       |
| Execution             | Remote command execution after login                  | T1059 – Command and Scripting Interpreter |
| Discovery             | System reconnaissance (uname, id, /etc/passwd)        | T1082 – System Information Discovery      |
| Privilege Escalation  | Modification of sudoers file and account privileges   | T1548 – Abuse Elevation Control Mechanism |
| Persistence           | SSH key injection into authorized_keys                | T1098 – Account Manipulation              |
| Command & Control     | Communication with external malicious servers         | T1071 – Application Layer Protocol        |
| Ingress Tool Transfer | Download of malicious files via wget/curl             | T1105 – Ingress Tool Transfer             |
| Defense Evasion       | Disguising malware as .jpg files                      | T1036 – Masquerading                      |
| Impact                | Botnet activity (Mirai/Tsunami, DDoS capability)      | T1496 – Resource Hijacking                |

 Summary

The attack demonstrates a fully automated compromise workflow commonly used by IoT botnets. The sequence of brute-force access, reconnaissance, payload delivery, and persistence highlights a structured and repeatable attack pattern aligned with real-world threat intelligence.

Analysis is based on previously collected honeypot data and documented observations.
