---
title: External Penetration Test
toc: true
---
### Objective
The ultimate goal is to compromise the organisation's external perimeter by gainining unauthorised remote access to information systems. 

Unauthorised access to "systems" in this context, is including but not limited to:
* Office 365 applications such as Outlook, SharePoint or Teams.
* Virtual Desktop Infrastructure (VDI) via RDP, RDWeb, VPN, Citrix, or others.
* Customer Relationship Management (CRM) systems such as Salesforce. 
* Content Management Systems (CMS) such as WordPress. 
* Any infrastructure running in the organisation's network, on-prem or cloud based.
* Any other Software as a Service (SaaS) with access to sensitive information.

### Scope
The scope of an External Penetration Test should include:
1. Public IP addresses/ranges
2. Domains
3. Websites 

An organisation that is requesting an External Penetration Test, typically wants to understand if the external perimeter can be compromised. To ensure the intent of this can be met, it important that the scope includes sufficient coverage of the organisation's external attack surface. 

Sometimes the scope that is shared doesn't provide sufficient coverage of the attack surface, or will exclude key activities such as attacking authentication portals. This can severly impact the outcome of the External Penetration Test, and may provide a false sense of assurance to stakeholders. Before commencing this type of a test, I always check if there are any adjacent targets which can be added to scope, based on some preliminary open source intelligence and passive reconnaissance. 

### Methodology
{{% steps %}}

### Step 1: Enumeration

* Passive reconnaissance through OSINT, Shodan, DNS and WHOIS. 
* Active reconnaisance through Nmap port scanning and GoWitness. 
* Building username/email list scraping LinkedIn.
* Validating username/email list with AADInternals. 

### Step 2: Vulnerability Scanning

* Version enumeration through Nessus advanced network scans. 

### Step 3: Attacking Login Portals

* Credential stuffing attacks using historically compromised accounts.
* Password spraying with custom context-driven password list.
* Enumerate conditional access policies.
* Multi-factor authentication bypasses with MFASweep. 

### Step 4: Vulnerability Exploitation

* Search exploit-db, github and google.
* Modify proof-of-concept code for exploitation. 

### Step 5: Post-Exploitation

* Demonstrate impact with screenshots of access to sensitive assets.
* Domain join a Windows 10 VM to Active Directory Domain, to bypass MFA or access other apps.
* Export Global Address List from Office 365 Outlook for additional password spraying.
* Search for other juicy secrets, keys or passwords.

{{% /steps %}}