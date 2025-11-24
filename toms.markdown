---
title: Technical and Organizational Measures
author: Akenes S.A., under its trademark Exoscale
---

### Introduction

This document describes the concrete technical and organizational measures (TOMs) implemented by Exoscale to ensure an appropriate level of security for the personal data it processes as a data processor. These measures are implemented in accordance with Article 32 of the General Data Protection Regulation (GDPR).

All measures detailed below apply exclusively to the systems and services that constitute the Exoscale platform as a whole. Customer systems, as well as the data stored in those systems, are not directly covered by these processes or measures and remain the sole responsibility of the customer.

The measures take into account the nature, scope, context, and purposes of processing, as well as the risks to the rights and freedoms of natural persons. This document provides specific descriptions of our control environment, which is independently audited and attested through reports such as SOC 2 Type 2 and BSI C5 Type 2.

### 1. Pseudonymization and Encryption of Personal Data

Exoscale implements robust cryptographic controls to protect the confidentiality and integrity of personal data.

#### 1.1. Encryption of Data in Transit

* Protocol Enforcement: All data transmitted over untrusted or public networks (including the internet) is encrypted using Transport Layer Security (TLS) 1.2 or higher.  
* Secure Cipher Suites: We enforce the use of strong, industry-recognized cipher suites (e.g., those including AES and ChaCha20) and disable outdated or weak protocols (e.g., SSL, early TLS versions). This applies to customer access to the Exoscale platform, API calls, and internal data transfers between service components.  
* Secure Remote Access: Remote administrative access to our internal networks is secured via a Virtual Private Network (VPN) that requires multi-factor authentication and enforces TLS encryption for all traffic.

#### 1.2. Encryption of Data at Rest

* Storage Systems: Sensitive data at rest, including personal data in databases and object storage, is protected using strong encryption algorithms like AES-256.  
* Endpoint Encryption: All company-issued workforce endpoints (laptops) are required to use full-disk encryption, which is enforced and monitored via a Mobile Device Management (MDM) solution.  
* Backup Encryption: Database data backups are encrypted.

#### 1.3. Cryptographic Key Management

* Centralized Management: Exoscale operates a centralized key management program to govern the entire lifecycle of cryptographic keys, including generation, storage, distribution, rotation, and revocation.  
* PKI Infrastructure: We maintain an internal Public Key Infrastructure (PKI) to issue and manage digital certificates for internal systems, enabling strong authentication and secure communication channels.

#### 1.4. Pseudonymization

* Data Masking: Where operationally feasible and for specific purposes like analytics, testing, and reporting, personal data is pseudonymized to reduce its direct identifiability and minimize privacy risks.

### 2. Ensuring Data Minimization and Limited Data Retention

* Data Minimization: We adhere to the principle of data minimization by ensuring that personal data collection is limited to what is strictly necessary to provide our services and fulfill our legal obligations. This principle is embedded in our processes, such as through DPIAs.
* Data Retention: We maintain a documented data retention schedule that defines the retention period for different categories of personal data. Data is retained only for as long as necessary for the specified purpose.
* Secure Deletion: Once the retention period expires, personal data is securely and irreversibly deleted or anonymized from our systems, including backups, in accordance with our documented procedures.

### 3. Ensuring Ongoing Confidentiality, Integrity, Availability, and Resilience

Exoscale maintains a multi-layered security program to ensure the ongoing protection and resilience of its processing systems.

#### 3.1. Confidentiality

* Logical Access Control: Access is strictly governed by our Identity and Access Management (IAM) system, which enforces the principles of least privilege and role-based access control (RBAC).  
* Data Classification: We maintain a formal data classification program that categorizes data (e.g., Public, Internal, Confidential) and defines specific handling, storage, and transmission requirements for each category.  
* Secure Media Disposal: Physical media containing personal data is securely sanitized using validated erasure tools or physically destroyed by certified third-party vendors. All disposals are tracked in our asset inventory.  
* Personnel Security: All personnel are subject to confidentiality agreements as part of their employment contracts and receive mandatory data privacy training.

#### 3.2. Integrity

* Change Management: All changes to production systems, including configurations, software, and network rules, are governed by a formal change management process. A Change Advisory Board (CAB) reviews and approves all changes, which includes a mandatory security impact analysis.  
* File Integrity Monitoring (FIM): We deploy FIM tools on critical systems to detect and generate alerts for unauthorized modifications to system files and configurations.  
* Secure Development: Our Software Development Lifecycle (SDLC) integrates security at every stage. This includes mandatory peer code reviews, the use of static application security testing (SAST) tools to identify vulnerabilities in code, and adherence to secure coding standards (e.g., OWASP Top 10).  
* Data Transfer Integrity: The use of cryptographic protocols like TLS and SSH ensures that data cannot be altered during transmission without detection.

#### 3.3. Availability and Resilience

* Redundant Architecture: Our platform is built on a geographically distributed and redundant infrastructure to mitigate single points of failure. This includes redundant power supplies, network connectivity from multiple providers, and failover capabilities for critical processing systems.  
* Capacity Management: We use automated monitoring tools to track resource utilization (CPU, memory, storage, network bandwidth) in real-time. This data informs our capacity planning process, ensuring resources are available to meet both current demand and contingency scenarios.  
* DDoS Protection: We deploy specialized technologies to detect and mitigate Distributed Denial of Service (DDoS) attacks, preserving the availability of our services.  
* Network Defense: Our network architecture employs a defense-in-depth strategy, including firewalls, network segmentation (VLANs), and Access Control Lists (ACLs) to isolate critical environments and restrict traffic to only authorized flows.

### 4. Restoring Availability and Access to Personal Data

Exoscale maintains a robust Business Continuity and Disaster Recovery (BC/DR) program to ensure data can be restored in a timely manner.

* Data Backups: Regular, automated backups are performed for all critical data, and platform system configurations.  
* Backup Location: Backups are encrypted and stored at a geographically separate alternate storage site to protect against regional disasters.  
* Integrity Verification: We perform regular, automated integrity checks and periodic test restorations of backups to verify their viability and ensure that our recovery procedures are effective.  
* Defined Recovery Objectives: We have established and documented Recovery Time Objectives (RTOs) and Recovery Point Objectives (RPOs) for critical services as part of our Business Impact Analysis (BIA), which guides our BC/DR strategy.  
* Disaster Recovery Plans (DRP): We maintain detailed DRPs for critical systems. These plans are tested at least annually through tabletop exercises or full failover simulations to ensure our technical capabilities and personnel readiness.

### 5. Testing, Assessing, and Evaluating Effectiveness

We continuously validate the effectiveness of our security measures through a multi-faceted testing and assessment program.

* Vulnerability Management:  
  * Continuous Scanning: We perform continuous, automated vulnerability scanning of both our internal and external infrastructure to identify potential security weaknesses.  
  * Prioritization and Remediation: Identified vulnerabilities are ranked based on CVSS scores and environmental context. Remediation is tracked in a centralized system with defined SLAs, and critical vulnerabilities are escalated to management.  
* Penetration Testing: We engage independent third-party security firms to conduct annual penetration tests against our platform and critical systems.  
* Bug Bounty Program: We operate a public bug bounty program to incentivize the responsible disclosure of security vulnerabilities by external researchers.  
* Internal and External Audits: Our control environment is subject to regular internal audits and annual external audits by independent firms to verify compliance with standards such as SOC 2 Type 2 and BSI C5 Type 2.

### 6. User Identification and Authorization

Access to systems processing personal data is strictly controlled and limited to authorized personnel.

* Centralized Identity and Access Management (IAM): We use a centralized IAM solution to manage all user identities and enforce access policies. All users (employees and third parties) are assigned unique user IDs. Shared or generic accounts for administrative access are prohibited.  
* Role-Based Access Control (RBAC): Access permissions are granted based on the principle of least privilege and are tied to predefined roles. This ensures users only have access to the data and systems necessary to perform their job functions.  
* Multi-Factor Authentication (MFA): MFA is mandatory for all remote access to the corporate network (VPN) and for non-console administrative access to production systems which require the use of a hardware security token to access (YubiKeys).  
* Privileged Access Management (PAM): Access to privileged accounts is tightly restricted, requires management approval, is logged in detail, and is subject to regular review. Administrative access to production environments is performed via bastion hosts.  
* Joiner-Mover-Leaver Process:  
  * Provisioning: User access is formally provisioned upon hiring, based on the employee's role.  
  * Review: Access rights are reviewed automatically and manually on a periodic basis (at least quarterly) and immediately upon a change in role or responsibilities.  
  * Revocation: All logical and physical access is revoked immediately upon termination of employment, managed through an automated process integrated with our HR system.

### 7. Ensuring Physical Security of Locations

Exoscale ensures the physical security of its data processing environments by exclusively using third-party colocation data centers that are independently audited and certified against internationally recognized standards (e.g., ISO/IEC 27001, SOC 2). Their measures include:

* Perimeter Security: Facilities are protected by security fencing, vehicle traps, and 24/7/365 on-site security personnel.  
* Access Control: Multi-layered access control is enforced, requiring biometric scans and electronic key card authentication to pass through mantraps before reaching the data halls. All access is logged and monitored.  
* Video Surveillance: CCTV monitors the interior and exterior of the facilities.  
* Visitor Management: All visitors must be pre-approved, provide government-issued identification upon arrival, and are escorted by authorized personnel at all times within secure areas.  
* Environmental Controls: Data centers are equipped with redundant power (UPS, backup generators with 48+ hours of fuel), advanced fire detection and suppression systems (e.g., VESDA, gas-based systems), and precise temperature and humidity controls.

### 8. Ensuring Events Logging

We implement comprehensive logging to enable security monitoring, incident investigation, and accountability.

* Centralized Logging and SIEM: Logs from all critical systems, network devices, and applications are forwarded to a centralized Security Information and Event Management (SIEM) system for aggregation, correlation, and analysis.  
* Log Content: Logs are configured to capture detailed event information, including user ID, source IP address, timestamp, event type (e.g., login success/failure, file access), and outcome. Timestamps are synchronized with an authoritative time source.  
* Log Protection: Access to logs and logging systems is restricted to authorized security personnel. Measures are in place to prevent unauthorized modification or deletion of log data.  
* Log Retention: Logs are retained in accordance with legal, regulatory, and business requirements to support forensic investigations and compliance audits. Security logs are retained for a minimum of 12 months.

### 9. Ensuring System Configuration

We enforce secure configurations to harden our systems against attack.

* Secure Baselines: We develop and maintain secure baseline configurations for all operating systems, network devices, and applications.  
* Infrastructure as Code (IaC): We use IaC tools to automate the deployment and management of our infrastructure. This ensures that all systems are built according to our secure baselines and prevents unauthorized configuration drift.  
* Least Functionality: Systems are configured to provide only essential capabilities. All unnecessary ports, protocols, and services are disabled to minimize the attack surface.  
* Separation of Environments: We maintain logically and physically separate environments for development, testing, and production. Changes must be tested and validated in lower environments before being promoted to production.

### 10. Internal IT and IT Security Governance

Our security program is managed through a formal governance structure.

* Information Security Management System (ISMS): We operate an ISMS aligned with international standards. The ISMS includes a comprehensive set of documented policies, standards, and procedures that are reviewed and approved by management at least annually.  
* Defined Roles: We have designated a Chief Information Security Officer (CISO) with overall responsibility for the security program and a Data Protection Officer (DPO) to oversee data privacy compliance. A Security Committee composed of senior leadership provides oversight and strategic direction.  
* Risk Management: We maintain a formal risk management program that includes at least annual risk assessments, the identification and analysis of threats, and the tracking of mitigation actions in a risk register.  
* Data Protection Impact Assessments (DPIAs): DPIAs are conducted for any new or significantly changed processing of personal data that is likely to result in a high risk to individuals.

### 11. Ensuring Accountability and Assistance to the Controller

Exoscale implements measures to demonstrate accountability and assist our customers (controllers) in meeting their GDPR obligations.

* Accountability: Our security program is evidenced by our comprehensive documentation (policies, procedures, risk assessments) and validated by independent third-party audits (SOC 2, BSI C5, ISO 27001:2020, ISO27018:2019), which are made available to customers upon request. We maintain records of processing activities as required by Article 30 GDPR.  
* Assistance with Data Subject Rights: We provide customers with the necessary technical tools and APIs to enable them to respond to Data Subject Rights requests (e.g., access, rectification, erasure, and portability) related to the data they store on our platform.  
* Incident Notification: In the event of a personal data breach affecting a customer, we will notify the customer without undue delay, providing them with the necessary information to fulfill their own notification obligations to supervisory authorities and data subjects.  
* DPIA Support: We provide customers with the necessary information about our services and security measures to help them conduct their Data Protection Impact Assessments.
