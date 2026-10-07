<div align="center">

# Hi, I’m Mahima 👋

### Exploring cybersecurity across SOC operations, security automation, cloud, networks, applications, embedded systems, OT, hardware, and digital forensics 🔐

[LinkedIn](https://www.linkedin.com/in/mahimakulkarni) • [Medium](https://medium.com/@mahimakulkarni1999) • [GitHub Projects](https://github.com/mahimakulkarnii?tab=repositories)

</div>

## About Me

I’m a cybersecurity professional interested in understanding how systems operate, how security weaknesses emerge, and how technical findings can be translated into practical risk-reduction decisions.

My interests span SOC operations and incident response, security automation and agentic AI, cloud identity and monitoring, network defense, web and API security, digital forensics, embedded and IoT security, OT security fundamentals, hardware security, and governance.

* 🎓 M.S. in Technology, Cybersecurity & Policy
* 🔐 Interested in technical security, incident investigation, security automation, and risk-based decision-making
* 🤖 Building agentic SOC workflows that combine Splunk, Python, LLM reasoning, and controlled security automation
* 📚 Continuing to strengthen cloud, DFIR, network-defense, and detection-engineering skills
* ✍️ Writing about cloud security, privacy, third-party risk, and data breaches
* 🎤 Outside cybersecurity, I enjoy Bollywood singing

## Cybersecurity Focus

| Area | Current Focus |
| --- | --- |
| 🔍 SOC & Incident Response | Splunk, log analysis, alert triage, incident investigation, MITRE ATT&CK, YARA, security monitoring |
| 🤖 Security Automation & Agentic AI | Python, GPT-5.6, LLM tool calling, evidence-driven investigation, structured outputs, response guardrails |
| 🕵️ Digital Forensics | FTK Imager, Autopsy, Volatility, disk imaging, file carving, timeline analysis |
| ☁️ Cloud Security & IAM | Google Cloud IAM, service accounts, Cloud KMS, Cloud Audit Logs, BigQuery, SQL; Azure, Entra ID, RBAC, managed identities, Key Vault, Log Analytics, KQL |
| 🌐 Network Security | pfSense, VLANs, Snort, Wireshark, firewalls, routing, switching |
| 🛡️ Web, Application & API Security | Burp Suite, Postman, OWASP ZAP, OAuth, SAST/DAST, OWASP Top 10 |
| 📡 Embedded, IoT & OT Security | BLE, ESP32-C3, firmware security, SPI/UART, SCADA, Modbus, IEC 62443 |
| 🖥️ Hardware & Systems | PC assembly, BIOS/UEFI, Secure Boot, TPM, system hardening, Active Directory |
| 📋 GRC & Privacy | NIST CSF, NIST Privacy Framework, ISO 27001, GDPR, CCPA, SOC 2 |

## Featured Projects

### 🤖 [Agentic SOC Investigation & Response Lab](https://github.com/mahimakulkarnii/agentic-soc-investigation)

Built an agentic SOC investigation workflow that combines **Splunk Enterprise, Python, OpenAI GPT-5.6, structured function calling, asset context, threat intelligence, deterministic response policy, and human-reviewed containment guardrails**.

* Built a multi-round investigation loop where GPT-5.6 determines what evidence is needed and selects from approved Python investigation tools
* Integrated Python with the Splunk REST API to retrieve authentication, post-login, firewall, and system evidence using parameterized searches
* Implemented input validation, strict tool schemas, index allowlisting, bounded investigation rounds, and restricted execution paths so the LLM cannot submit unrestricted SPL or arbitrary commands
* Correlated authentication failures, successful access, post-login commands, firewall activity, system telemetry, asset context, and optional VirusTotal enrichment
* Separated LLM reasoning from response authority using deterministic containment policy and human approval for disruptive actions
* Evaluated the workflow against malicious, benign, and inconclusive controlled scenarios with explicit ground truth, matching expected classification and containment decisions in all three test cases

**Tools & Technologies:** Splunk Enterprise, SPL, Python, OpenAI GPT-5.6, Responses API, function calling, REST APIs, VirusTotal API v3, incident response, security automation

### ☁️ [GCP Identity, Access and Monitoring Lab](https://github.com/mahimakulkarnii/gcp-iam-monitoring-lab)

Built a Google Cloud security lab to test **least-privilege access, keyless VM authentication, and audit-log detections** using controlled workload activity.

* Created custom IAM roles with object read/list permissions scoped to one bucket and decrypt permission scoped to one KMS key
* Attached a service account to a Compute Engine VM so it authenticated through the metadata server without service-account JSON keys
* Configured uniform bucket-level access and enforced public access prevention; stored only encrypted dummy data in the bucket
* Validated five access tests: object read and KMS decrypt succeeded; VM listing, object upload, and KMS encrypt were denied
* Exported Cloud Audit Logs to BigQuery and validated SQL for IAM policy changes, role-binding additions, decrypt activity, and denied KMS operations
* Tuned the decrypt query to exclude the exact expected workload identity, key, and successful outcome while retaining an authorized human comparison event
* Published build notes, SQL queries, test results, and 38 screenshots, with selected evidence embedded in the repository README

**Tools & Technologies:** Google Cloud IAM, Compute Engine, service accounts, Cloud Storage, Cloud KMS, Cloud Audit Logs, BigQuery, SQL, gcloud

### 🌐 [Enterprise Network Segmentation & Firewall Lab](https://github.com/mahimakulkarnii/enterprise-network-segmentation-lab)

Built a segmented enterprise-style network environment using pfSense, VirtualBox, and Ubuntu Linux.

* Established separate User (`192.168.10.0/24`), Server (`192.168.20.0/24`), and Management (`192.168.99.0/24`) security zones
* Configured dedicated pfSense gateway interfaces, DHCP services, DNS/NTP firewall permissions, and static Ubuntu addressing
* Validated host-to-gateway connectivity across the User and Server network segments
* Diagnosed and resolved Netplan, routing, addressing, and VirtualBox network-attachment issues
* Documented the architecture, implementation, validation, and troubleshooting process with technical evidence

**Tools & Technologies:** pfSense, VirtualBox, Ubuntu Linux, Netplan, TCP/IP, DHCP, DNS, NTP, ICMP

### 🕵️ [Deleted Data Recovery & Forensic Image Analysis](https://github.com/mahimakulkarnii/deleted-data-recovery-dfir)

A digital-forensics case study demonstrating:

* Acquisition of an approximately 256 GB physical storage device
* Creation of 76 segmented E01 evidence files
* MD5 and SHA-1 integrity verification
* Analysis of allocated, unallocated, and slack-space entries
* File carving, keyword searching, and timeline reconstruction
* FTK Imager, Autopsy, PhotoRec, Plaso, YARA, and Linux imaging workflows

## Project Portfolio

<details>
<summary><strong>🔍 SOC Operations, Detection & Incident Response</strong></summary>

<br>

### [Agentic SOC Investigation & Response Lab](https://github.com/mahimakulkarnii/agentic-soc-investigation) — Published

Built an agentic SOC workflow where **GPT-5.6 reasons about suspicious activity, selects approved investigation tools, Python retrieves structured evidence from Splunk and contextual sources, and deterministic policy controls whether containment can be requested**.

The lab investigates authentication, post-login, firewall, and system telemetry through parameterized Splunk searches; supports asset-context and VirusTotal enrichment; validates model-requested parameters before execution; and prevents the LLM from directly executing unrestricted SPL or disruptive response actions.

Tested the workflow against controlled **malicious, benign, and inconclusive scenarios** with explicit ground truth. The system matched the expected classification and containment decision in all three controlled test cases while keeping containment execution disabled and subject to human review.

**Tools:** Splunk Enterprise, SPL, Python, OpenAI GPT-5.6, Responses API, function calling, REST APIs, VirusTotal API v3, incident response, security automation

### SOC Investigation & Monitoring Labs

Investigated authentication activity, system events, network traffic, endpoint behaviors, and access-control issues to practice structured alert triage and root-cause analysis.

**Tools and concepts:** Splunk, Windows Event Logs, Wireshark, YARA, MITRE ATT&CK, alert triage, escalation, incident documentation

### Splunk Security Analysis

Used Splunk searches, dashboards, and data analysis to identify patterns in security and customer activity and support simulated fraud and incident investigations.

**Tools and concepts:** Splunk, SPL, dashboards, log analysis, event correlation, security monitoring

### Security Incident-Response Simulation

Practiced incident notification, information gathering, containment, escalation, recovery, and security-awareness communication in a simulated enterprise environment.

**Focus:** Incident handling, communication, documentation, containment, recovery

</details>

<details>
<summary><strong>🕵️ Digital Forensics</strong></summary>

<br>

### [Deleted Data Recovery & Forensic Image Analysis](https://github.com/mahimakulkarnii/deleted-data-recovery-dfir) — Published

Created and verified segmented forensic images, examined filesystem artifacts in Autopsy, reviewed unallocated and slack-space entries, and generated a filesystem activity timeline.

**Tools:** FTK Imager, Autopsy, PhotoRec, Plaso, YARA, Kali Linux, `dd`

### Forensic Keyword Search & Office Document Recovery

Analyzed a forensic disk image in Autopsy, searched for sensitive keywords, tagged relevant Office and email files, and identified evidence in carved files, unallocated space, and file slack.

**Tools:** Autopsy, keyword search, file carving, metadata analysis, hash reporting

### Memory and Artifact Analysis

Explored memory-forensics and incident-reconstruction techniques for identifying processes, system artifacts, and suspicious activity.

**Tools:** Volatility, timeline analysis, process examination

</details>

<details>
<summary><strong>☁️ Cloud Security, IAM & Monitoring</strong></summary>

<br>

### [GCP Identity, Access and Monitoring Lab](https://github.com/mahimakulkarnii/gcp-iam-monitoring-lab) — Published

Built a Compute Engine workload with an attached service account, bucket-scoped object read/list permissions, and key-scoped KMS decrypt permissions. Verified two allowed operations and three denied operations without creating service-account JSON keys.

Exported Cloud Audit Logs to BigQuery and validated SQL against controlled IAM changes, role additions, successful decrypts, and a denied encryption event. Tuned the decrypt query against known-benign workload activity using an exact identity/key/success exception, retaining the authorized human comparison event. Queries were run manually; the lab did not implement scheduled alerts or collect VM operating-system logs.

**Tools:** Google Cloud IAM, Compute Engine, Cloud Storage, Cloud KMS, service accounts, Cloud Audit Logs, BigQuery, SQL, gcloud

### Azure IAM & Monitoring Lab

Built an Azure environment with a Linux VM, Storage Account, and Key Vault. Implemented least-privilege RBAC, Entra ID groups, managed identities, secure data-transfer settings, and KQL monitoring for privilege and secret-access activity.

**Tools:** Microsoft Azure, Entra ID, Key Vault, RBAC, Managed Identities, Log Analytics, KQL

### Securing the Cloud: Access Controls in Microsoft Azure

Researched and demonstrated user and group management, role assignments, policy enforcement, monitoring, auditing, and access-control testing in Microsoft Azure.

**Focus:** IAM, RBAC, cloud governance, least privilege, access-control risk

</details>

<details>
<summary><strong>🌐 Network Security & Monitoring</strong></summary>

<br>

### [Enterprise Network Segmentation & Firewall Lab](https://github.com/mahimakulkarnii/enterprise-network-segmentation-lab) — Published

Built a segmented virtual network using pfSense, VirtualBox, and Ubuntu Linux with separate User, Server, and Management security zones. Configured dedicated gateway interfaces, DHCP services, firewall rules, static addressing, and Netplan routing, then validated host-to-gateway connectivity and documented troubleshooting.

**Tools:** pfSense, VirtualBox, Ubuntu Linux, Netplan, TCP/IP, DHCP, DNS, NTP, ICMP

### Router & Switch Configuration Lab

Configured routers and switches with VLANs, DHCP, NAT, WPA2, static and dynamic addressing, and controlled network access. Used packet analysis and simulation to identify connectivity and configuration issues.

**Tools:** Cisco Packet Tracer, Wireshark, routers, switches, DHCP, DNS, NAT

### Secure Link-State Routing Protocol

Developed a Java-based link-state routing project using sockets, threading, neighbor communication, routing-database exchange, and shortest-path calculation.

**Tools:** Java, sockets, threading, authentication, encryption, routing protocols

</details>

<details>
<summary><strong>🛡️ Web, Application & API Security</strong></summary>

<br>

### Web & API Vulnerability Assessment

Built vulnerable application environments and tested web and API endpoints for SQL injection, cross-site scripting, authentication weaknesses, authorization flaws, and insecure data exposure.

**Tools:** Burp Suite, OWASP ZAP, Postman, Nmap, Docker, DVWA, OWASP Top 10

### Third-Party API Security Assessment

Assessed third-party APIs for authentication weaknesses, authorization flaws, token-handling risks, and insecure data exposure. Researched OAuth attack techniques and mapped findings to the OWASP API Security Top 10.

**Tools and concepts:** Burp Suite, Postman, OAuth, API authorization, OWASP API Security Top 10

### Linux & Web Penetration Testing Lab

Conducted reconnaissance and controlled exploitation against exposed FTP, SSH, Telnet, HTTP, and database services. Documented attack paths and applied firewall and authentication improvements.

**Tools:** Kali Linux, Nmap, Metasploit, UFW, service enumeration

</details>

<details>
<summary><strong>📡 Embedded, IoT & OT Security</strong></summary>

<br>

### Bluetooth Device Threat Modeling

Assessed the security of a BLE-connected ESP32-C3 device, examining pairing, encryption, firmware behavior, and low-level communication interfaces.

Created data-flow diagrams, reviewed software components, scored vulnerabilities, and explored fuzzing approaches for memory-corruption and denial-of-service risks.

**Tools and concepts:** BLE, ESP32-C3, IDA Pro, SPI, UART, DFDs, SBOM, CVSS, fuzzing

### Embedded Hardware & Firmware Security

Explored secure boot, firmware security, hardware interfaces, low-level communication protocols, and risks affecting connected and embedded devices.

**Focus:** Secure Boot, BIOS/UEFI, firmware updates, SPI, I2C, UART, BLE, Zigbee

### OT Security Foundations

Studying the security considerations of industrial environments, including network segmentation, legacy protocols, asset availability, safety requirements, and the differences between enterprise IT and operational technology.

**Focus:** SCADA, PLCs, HMIs, Modbus, DNP3, industrial segmentation, IEC 62443 fundamentals

</details>

<details>
<summary><strong>🖥️ Hardware, Systems & Security Baselines</strong></summary>

<br>

### PC Assembly & BIOS/UEFI Security

Assembled and troubleshot computer systems, configured Secure Boot, TPM, boot order, firmware settings, and POST behavior, and resolved component-detection and startup issues.

### macOS Hardening & Baseline

Created a repeatable macOS security baseline covering FileVault, Gatekeeper, firewall and stealth mode, automatic updates, login security, privacy controls, validation, and rollback guidance.

### Linux System Troubleshooting

Investigated simulated service failures, permission errors, disk-utilization problems, and resource exhaustion using Linux logs, processes, and administrative utilities.

### Structured Cabling & Network Connectivity

Built and tested Ethernet cables using the TIA-568B standard and diagnosed physical-layer faults involving pinouts, crimping, continuity, and damaged conductors.

</details>

<details>
<summary><strong>📋 Governance, Risk, Compliance & Privacy</strong></summary>

<br>

### Evaluation of the NIST Privacy Framework

Evaluated privacy-policy options using the NIST Privacy Framework, GDPR, and CCPA. Compared regulatory, operational, cost, and innovation considerations to develop risk-based recommendations.

**Focus:** Privacy risk, data classification, policy evaluation, GDPR, CCPA

### Security Awareness Simulation

Evaluated phishing and social-engineering risk, identified departments requiring targeted support, and designed security-awareness recommendations and procedural improvements.

**Focus:** Phishing, security awareness, risk communication, mitigation planning

</details>

## Research & Writing

### Cloud Security and Privacy Research

#### [Securing the Cloud: A Practical Exploration of Access Controls in Microsoft Azure](https://medium.com/@mahimakulkarni1999/securing-the-cloud-a-practical-exploration-of-access-controls-in-microsoft-azure-45f79e54e45e)

A hands-on exploration of Microsoft Azure access controls covering IAM, user and group management, RBAC, policy configuration, monitoring, auditing, and least-privilege security.

#### [Managing Privacy Risks in the Digital Age: An Analysis of the NIST Privacy Framework and Future Policy Directions](https://medium.com/@mahimakulkarni1999/managing-privacy-risks-in-the-digital-age-an-analysis-of-the-nist-privacy-framework-and-future-ba3c59b19dea)

A policy-focused analysis of the NIST Privacy Framework, GDPR, CCPA, adoption challenges, privacy impact assessments, and risk-based approaches to protecting personal data.

### Published Security Blogs

#### [Capgemini’s Data Disaster: When Hackers Turned Consulting into Chaos](https://vorlon.io/saas-security-blog/capgeminis-data-disaster-when-hackers-turned-consulting-into-chaos)

An analysis of a reported data breach involving sensitive corporate information, third-party exposure, regulatory obligations, and the organizational consequences of inadequate data protection.

#### [Fortinet Hit by Cyber Attack: Third-Party Breach Affects Asia-Pacific Customers](https://vorlon.io/saas-security-blog/fortinet-hit-by-cyber-attack-third-party-breach-affects-asia-pacific-customers)

An examination of third-party cloud risk, breach response, continuous monitoring, API security, access governance, encryption, and practical recommendations for affected customers and organizations.

## Certifications

* [CompTIA CySA+](https://www.credly.com/badges/e7d95faf-5ae0-4240-b55a-448992a1ada0)
* [CompTIA Security+](https://www.credly.com/badges/e2c65998-ea50-4ed5-b1dc-550451b9406f)
* [CompTIA A+](https://www.credly.com/badges/097d5bf9-29d0-4b75-b6b4-bc20f0aca86d)
* [ISC2 Certified in Cybersecurity (CC)](https://www.credly.com/badges/e5c9058e-6b6a-4309-b2c9-673a2d9d0841)
* [Cisco Endpoint Security](https://www.credly.com/badges/5bdb7378-41a9-49cf-87c3-b61e898ea74f)
* [Cisco Cyber Threat Management](https://www.credly.com/badges/75fa4a8a-6b0c-49bf-b6eb-f7b073509fa5)
* [Cisco Network Support and Security](https://www.credly.com/badges/fb5f7871-77c4-4603-a223-dfd794a8798e)

## Education

**University of Colorado Boulder**  
M.S. in Technology, Cybersecurity & Policy  
GPA: 3.9/4.0

**Visvesvaraya Technological University**  
B.E. in Computer Science and Engineering

## What I’m Working On

* Building and evaluating agentic SOC investigation workflows using Splunk, Python, and LLM tool calling
* Expanding detection, evidence-correlation, and incident-response automation scenarios
* Deepening Google Cloud fundamentals after building and validating an IAM and audit-log monitoring lab
* Practicing digital-forensics and incident-response techniques
* Developing network monitoring and segmentation scenarios
* Exploring embedded, firmware, IoT, and OT security
* Connecting technical security findings to practical business risk

## Let’s Connect

I’m interested in connecting with cybersecurity professionals across SOC operations, incident response, security automation, cloud security, network defense, application security, digital forensics, embedded security, OT, and governance.

[Connect with me on LinkedIn](https://www.linkedin.com/in/mahimakulkarni)
