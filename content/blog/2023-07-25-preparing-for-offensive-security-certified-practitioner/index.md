---
title: Preparing for the Offensive Security Certified Practitioner (OSCP) on a Budget
summary: Often the barrier to entry with the OSCP exam is not just the time investment required, but the actual financial cost. This begs the question of what preparation can you complete before signing up to the course?
date: 2023-07-25
authors:
  - admin
tags:
  - study guide
  - oscp
  - offensive security
image:
  caption: 'Image credit: My OSCP Certificate'
---
## Background
The Offensive Security Certified Professional (OSCP) is often seen as the "holy grail" of penetration testing certifications in the cyber security industry. This is because, unlike many other industry certifications, your technical skills are put to the test in a grueling 24 hour exam where you are required to exploit an Active Directory environment, and a combination of additional 3 standalone Linux or Windows machines.

However, after studying the PEN-200 course and completing the exam in July 2023, I believe it is not as difficult as the industry makes it out to be. There is a significant amount of knowledge that is required to be understood and applied, however the depth of expertise required is really only at the beginner to intermediate level. As such, I think anyone even considering completing the course, should just throw themselves in the deep end and give it a red hot go. 

Often the barrier to entry with the PEN-200 course and the OSCP exam is not just the time investment required, but the actual financial investment as well. It is well worth it, however paying upfront $1500 USD for 90 day lab access or $2500 USD for 365 days lab access, and then including GST in Australia is a hefty $2450 AUD and $4100 AUD respectively. This begs the question of what preparation can you complete before signing up to the course? This article aims to answer this question and provide guidance. 

## Overview
I think the following 5 critical concepts must not only be understood, but also have been practiced in order to successfully pass the OSCP exam. In the next sections, I will go through each of these concepts and suggest high quality and affordable training options. Most training options overlap with each of the categories below.
1. Fundamental IT & Security Knowledge
2. Basic Network & Web Attacks
3. Active Directory Enumeration, Attacks & Lateral Movement 
4. Windows Privilege Escalation
5. Linux Privilege Escalation

## Summary (TL;DR)
1. If you are a complete beginner, sign up to the [eJPT](https://security.ine.com/certifications/ejpt-certification/), $299 USD once-off. 
2. Sign up to [HackTheBox VIP](https://www.hackthebox.com/hacker/pricing) for lab machine access, $14 USD monthly.
3. Sign up to the [TCM Security Academy](https://academy.tcm-sec.com/courses/), $30 USD monthly.
4. Sign up to [Tib3rius Windows & Linux Priv Esc](https://www.udemy.com/user/tib3rius/) courses, $35 USD once-off.
5. Get support from an [OSCP mentor](https://www.oscpmentor.com/), $25 USD per hour.

## Complete Beginners (eJPT)
This section applies to complete beginners, those who have no experience using Linux, and those who only have a conceptual understanding of how networking and operating systems work. This section can be skipped by those who feel confident in their ability to work in a command line interface and use tools. 

I recommend checking out the [eLearnSecurity Junior Penetration Tester (eJPT)](https://security.ine.com/certifications/ejpt-certification/). Access to the course content is available in the Fundamentals Monthly subscription at $39 USD ($60 AUD) per month. Or alternatively you can sign up for 1 year of course access which includes an eJPT exam attempt voucher for $299 USD ($450 AUD). 

This is a great entry level course which covers not only beginner penetration testing skills, but also important fundamental concepts such as:
* The information security industry
* Cryptography and VPNs
* Binary arithmetic basics
* Protocols and routing
* TCP and UDP
* Firewalls and network defence
* DNS
* Programming and command line scripting

The course also covers the basics of the following:
* Information gathering
* Footprinting & scanning
* Vulnerability assessments
* Web attacks
* System attacks
* Network attacks

I personally completed the eJPT 3 years ago when I was still a beginner in the cyber security industry and found it very valuable. However, I don't think it's required to progress to the next stage of learning, so if you are on a fast tracked timeline, get started on the next stage straight away.

## Starting Point - TCM Security Academy
I highly recommend [The Cyber Mentor (TCM) Security Academy](https://academy.tcm-sec.com/courses/). They have a variety of courses on their academy website which costs $30 USD per month for unlimited access. You can also get access to portions of their course content for free on their [YouTube channel](https://www.youtube.com/@TCMSecurityAcademy/videos). Their courses reference labs from [TryHackMe](https://tryhackme.com/) and [HackTheBox](https://www.hackthebox.com/hacker/pricing), so you may require a premium subscription on those sites to practice hands-on skills. 

**External Penetration Test Playbook**
The first course you will want to enroll in is the [External Penetration Test Playbook](https://academy.tcm-sec.com/p/external-pentest-playbook). One of the first types of engagements you will be assigned to as a beginner penetration tester is an External Network Penetration Test (ENPT). This type of testing is completed from unauthenticated perspective, with the objective of compromising internal network access. This course will teach you the following concepts:
* External penetration test strategies
* Vulnerability scanning
* OSINT and information gathering techniques
* Attacking login portals
* Bypassing MFA 
* Escalating access 

**Practical Ethical Hacker**
The second course you will want to enroll in is the [Practical Ethical Hacker course](https://academy.tcm-sec.com/p/practical-ethical-hacking-the-complete-course). They have posted two videos on their YouTube channel going through some of the content from the course for free, which you can access [here](https://www.youtube.com/watch?v=3FNYvj2U0HM&ab_channel=TheCyberMentor) and [here](https://www.youtube.com/watch?v=sH4JCwjybGs&ab_channel=TheCyberMentor). This teaches the following concepts:

Fundamental IT & Security Knowledge:
* Effective note taking
* Networking 
* IP addresses & MAC addresses
* TCP and UDP
* Ports & protocols
* The OSI model
* IP subnetting 
* Installing VMWare / VirtualBox
* Kali Linux overview
* Navigating the file system
* Users and privileges
* Bash scripting
* Introduction to Python

Web Application Attacks:
* SQL injection
* Broken authentication
* Sensitive data exposure
* XML external entities
* Broken access control
* Security misconfigurations
* Cross-site scripting
* Insecure deserialisation
* Using components with known vulnerabilities
* Insufficient logging and monitoring

Active Directory Attacks:
* LLMNR poisoning
* SMB relays
* IPv6 DNS takeovers
* Pass-The-Hash attacks
* Token impersonation
* Kerberoasting
* GPP attacks
* Golden ticket attacks
* Using tools like Mimikatz, Bloodhound and PowerView

**Windows Privilege Escalation for Beginners**
The third course you will want to enroll in is the [Windows Privilege Escalation for Beginners](https://academy.tcm-sec.com/p/windows-privilege-escalation-for-beginners). This covers the following types of privilege escalation attacks:
* Kernel exploits
* Password hunting
* Impersonation attacks
* Registry attacks
* Executable files
* Schedule tasks
* Startup applications
* DLL hijacking
* Service permissions
* Windows subsytem for Linux
* CVE-2019-1388

**Linux Privilege Escalation for Beginners**
The fourth and final course you will want to enroll in by TCM Security Academy is the [Linux Privilege Escalation for Beginners](https://academy.tcm-sec.com/p/linux-privilege-escalation). This covers the following types of privilege escalation attacks:
* Kernel exploits
* Password hunting
* File permissions
* Sudo attacks
* Shell escaping
* Intended functionality
* LD_PRELOAD
* CVE-2019-14287
* CVE-2019-18634
* SUID attacks
* Shared object injection
* Binary symlinks
* Environment variables
* Capabilities attacks
* Scheduled tasks
* NFS
* Docker

## Next Up - Tib3rius Privilege Escalation Courses
I found the following two courses by Tib3rius exceptional at rounding out my privilege escalation skills. Whilst the courses provided don't include labs, they are short, sharp and to the point and are priced very affordably at $17.50 USD each once-off.

[Tib3rius Linux Privilege Escalation for OSCP](https://www.udemy.com/course/linux-privilege-escalation/)
* Kernel exploits
* Service exploits
* Weak file permissions
* Sudo
* Cron jobs
* SUID / SGID executables
* Passwords and keys
* NFS
* Privilege escalation strategy

[Tib3rius Windows Privilege Escalation for OSCP](https://www.udemy.com/course/windows-privilege-escalation/)
* Kernel exploits
* Service exploits
* Registry exploits
* Passwords
* Scheduled tasks
* Insecure GUI apps
* Startup apps
* Installed apps
* Hot potato
* Token impersonation
* Port forwarding
* Privilege escalation strategy

## Finally - Active Directory on HackTheBox
I found the following machines on HacktheBox very beneficial for practicing my Active Directory exploitation skills. You can find write-ups for these machines by [Juggernaut-Sec](https://juggernaut-sec.com/category/walkthroughs/active-directory/) or [IppSec](https://www.youtube.com/watch?v=jUc1J31DNdw&list=PLbK3lpDL_g6ChnJ9E8LB30dezPfuzgaBI&ab_channel=IppSec). 
* Active
* Blackfield
* Cascade
* Forest
* Mantis
* Monteverde
* Sauna

Finally, I would also recommend considering getting an OSCP mentor or tutor. I received advice from a tutor named [Tim Bandors](https://www.oscpmentor.com/) at the hourly rate of $25 USD per hour. He provided mentorship through notes, explanation of topics, and completion of HackTheBox machines together whilst on video call. I had a total of 6 hours of mentorship from Tim in the final weeks before my OSCP exam and found it incredibly beneficial. 

## Conclusion
Concluding this blog post, if you have completed all of the above course content and lab machines, my recommendation would only be to apply for [OSCP 90 Day Lab Access](https://offsec.com/courses/pen-200/) which is $1499 USD or $2450 AUD inclusive of GST.

You are unlikely to need more than 90 days lab access, however it is important this time is spent completing the OffSec challenge labs, rather than the course content and module exercises. I recommend completing the following OffSec challenge labs in order:
* Medtech
* Relia
* OSCP A
* OSCP B
* OSCP C
* Skylark

With the 90 days lab access, this might not be sufficient to complete 80% or more of the module exercises for each chapter overall, unless a significant time investment of 30+ hours per week is available. As such, it is recommended to focus on completing the OffSec challenge labs instead. 