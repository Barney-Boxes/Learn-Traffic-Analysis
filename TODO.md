## Tools to include/use
* Splunk
* ELK Stack
* WireShark
* TShark
* Tcpdump
* SiLK/NetFlow/SFlow data tools
* Snort
* OSSEC
* SecurityOnion
* Bro/Zeek
* Yara
* Suricata
* Scirius
* GRR (Google Rapid Response)
* Kismet
* Open DLP
* SAGAN
* Syslog
* Logstash
* Fluentd
* [Riemann](https://riemann.io/concepts.html)
* Wazuh
* Tripwire
* osquery
* [artillery](https://github.com/BinaryDefense/artillery)
* [MozDef](https://github.com/jeffbryner/mozdef)
* \[MEMBERSHIP-REQUIRED\] Fortigate
* \[MEMBERSHIP-REQUIRED\] Palo Alto FireWall
* \[MEMBERSHIP-REQUIRED\] McAfee
* \[MEMBERSHIP-REQUIRED\] FireEye
* \[MEMBERSHIP-REQUIRED\] AlienVault USM
* \[MEMBERSHIP-REQUIRED\] CISCO NGIPS
* \[MEMBERSHIP-REQUIRED\] LogRythm
* \[MEMBERSHIP-REQUIRED\] IBM QRadar
* \[MEMBERSHIP-REQUIRED\] RSA NetWitness
* \[MEMBERSHIP-REQUIRED\] Sumo Logic
* \[MEMBERSHIP-REQUIRED\] SolarWinds
* \[MEMBERSHIP-REQUIRED\] Arcsight

## Designing the Template Network
* Edge Device
* Client Device pool
* IDS/IPS
* Analyst Device
* Infrastructure devices
  * switches/Routing
  * DNS/DHCP
  * LDAP

## How to Engineer your own network
* Setting up BOTS (Splunk)
* Setting up ELK Stack
* Setting up EFK Stack

## Picking Examples/Challenges
Try looking through Snort alerts & CVEs and try to replicate them.  
Try copying other challenges, or just explain how to setup other events/challenges, and provide write-ups.  

## Working on new stuff
Open a new branch per goal, name 'dev-<cve-### OR snort-rule, etc>'.  
When ready, create a pull request to merge the branch & delete it.  


## Layout of the Repository

#### Challenges
  - Cloud Based
  - Engineering
    - Cloud
    - Log
    - SIEM
  - Analysis
    - Log
    - Packet
    - Malware
  - Tools

#### Alerts
  - Whats this alert mean?
  - Whats related to this alert? (CVE)
  - How is the alert fired?

#### CVEs
  - How to detect
  - What they're doing
  - Possible Cross-talk/False Positives

#### Examples by Tools
  - Splunk
  - ELK Stack
  - WireShark
  - TShark
  - Tcpdump
  - SiLK/NetFlow/SFlow data tools
  - Snort
  - OSSEC
  - SecurityOnion
  - Bro/Zeek
  - Yara
  - Suricata
  - Scirius
  - GRR (Google Rapid Response)
  - Kismet
  - Open DLP
  - SAGAN
  - Wazuh
  - Tripwire
  - osquery
  - [artillery](https://github.com/BinaryDefense/artillery)
  - [MozDef](https://github.com/jeffbryner/mozdef)
  - \[MEMBERSHIP-REQUIRED\] Fortigate
  - \[MEMBERSHIP-REQUIRED\] Palo Alto FireWall
  - \[MEMBERSHIP-REQUIRED\] McAfee
  - \[MEMBERSHIP-REQUIRED\] FireEye
  - \[MEMBERSHIP-REQUIRED\] AlienVault USM
  - \[MEMBERSHIP-REQUIRED\] CISCO NGIPS
  - \[MEMBERSHIP-REQUIRED\] LogRythm
  - \[MEMBERSHIP-REQUIRED\] IBM QRadar
  - \[MEMBERSHIP-REQUIRED\] RSA NetWitness
  - \[MEMBERSHIP-REQUIRED\] Sumo Logic
  - \[MEMBERSHIP-REQUIRED\] SolarWinds
  - \[MEMBERSHIP-REQUIRED\] Arcsight
