---
title: Study & Exam Guide for the Burp Suite Certified Practitioner (BSCP)
summary: Portswigger's Web Security Academy is the best free resource to develop web application penetration testing skills. In this article, I describe my study approach and exam tips and tricks to pass the accompanying BSCP exam.
date: 2023-07-24
authors:
  - admin
tags:
  - career development
  - burp suite certified practitioner
  - mentorship
image:
  caption: 'Image credit: My BSCP Certificate'
---
I was issued the BSCP certificate on Monday 8th May 2023, and as I was the first one in my team to do it I thought it would be useful to create a study and exam guide for others. My certification can be found [here](https://portswigger.net/web-security/e/c/c13dedf1f6ae2f481).

## About the BSCP
The PortSwigger [Burp Suite Certified Practitioner](https://portswigger.net/web-security/certification) (BSCP) is an official certification for web security professionals, from the makers of Burp Suite. Becoming a Burp Suite Certified Practitioner demonstrates a deep knowledge of web security vulnerabilities, the correct mindset to exploit them, and of course, the Burp Suite skills needed to carry this out. Successfully passing the Burp Suite Certified Practitioner exam indicates a high-level proficiency in web security testing. It is aimed at penetration testers, and the organizations that employ them.

The exam consists of two (2) web applications that have three (3) vulnerabilities each, that need to identified and exploited at particular stages within a time period of four (4) hours.

These stages are:
1. Access any user account.
2. Use your user account to access the admin interface at /admin, perhaps by elevating your privileges or compromising the administrator account.
3. Use the admin interface to read the contents of /home/carlos/secret from the server’s file system, and submit it.

## Requirements
Before you can sit the exam, it is mandatory to complete the following practice labs as discussed by PortSwigger [here](https://portswigger.net/web-security/certification/how-to-prepare):
1. Complete one practitioner lab [from every topic](https://portswigger.net/web-security/certification/how-to-prepare/practitioner-labs-prep-step-one) (23 total).
2. Complete the selected labs below which reinforce specific skills for the exam (8 total).
* [Exploiting XSS to steal cookies.](https://portswigger.net/web-security/certification/how-to-prepare/practitioner-labs-prep-step-one)
* [Blind SQL injection with out-of-band data exfiltration](https://portswigger.net/web-security/sql-injection/blind/lab-out-of-band-data-exfiltration).
* [Forced OAuth profile linking](https://portswigger.net/web-security/oauth/lab-oauth-forced-oauth-profile-linking).
* [Brute-forcing a stay-logged-in cookie](https://portswigger.net/web-security/authentication/other-mechanisms/lab-brute-forcing-a-stay-logged-in-cookie).
* [Exploiting HTTP request smuggling to capture other users’ requests](https://portswigger.net/web-security/request-smuggling/exploiting/lab-capture-other-users-requests).
* [SSRF with blacklist-based input filter](https://portswigger.net/web-security/ssrf/lab-ssrf-with-blacklist-filter).
* [SQL injection with filter bypass via XML encoding](https://portswigger.net/web-security/sql-injection/lab-sql-injection-with-filter-bypass-via-xml-encoding).
* [Discovering vulnerabilities with targeted scanning](https://portswigger.net/web-security/essential-skills/using-burp-scanner-during-manual-testing/lab-discovering-vulnerabilities-quickly-with-targeted-scanning)
3. Complete five (5) mystery lab challenges without knowing the objective.
4. Take and pass the practice exam within two (2) hours.

## Cost
The practice labs and training material is all free, though a Burp Suite Professional or Enterprise license is required in order to complete the exam.

Each exam attempt cost is $99 USD (~$150 AUD).

## Study Material
It is highly recommended to complete all of the Apprentice (52 qty) and Practitioner (151 qty) practice labs in preparation for the exam. Completing the Expert (36 qty) practice labs is not required.

Following the [Web Security Academy Learning Path](https://portswigger.net/web-security/learning-path), you can learn these topics and complete the labs in an order of beginner to advanced. Each lab is typically accompanied by a learning page which explains both visually and with verbose text how the technique works.

### Beginner Labs:
1. SQL Injection — [18 Labs](https://portswigger.net/web-security/all-labs#sql-injection)
2. Authentication — [14 Labs](https://portswigger.net/web-security/all-labs#authentication)
3. Path Traversal — [6 Labs](https://portswigger.net/web-security/all-labs#path-traversal)
4. OS Command Injection — [5 Labs](https://portswigger.net/web-security/all-labs#os-command-injection)
5. Business Logic Vulnerabilities — [11 Labs](https://portswigger.net/web-security/all-labs#business-logic-vulnerabilities)
6. Information Disclosure — [5 Labs](https://portswigger.net/web-security/all-labs#information-disclosure)
7. Access Control — [13 Labs](https://portswigger.net/web-security/all-labs#access-control-vulnerabilities)
8. File Upload Vulnerabilities — [7 Labs](https://portswigger.net/web-security/all-labs#file-upload-vulnerabilities)
9. Server-Side Request Forgery — [7 Labs](https://portswigger.net/web-security/all-labs#server-side-request-forgery-ssrf)
10. XXE Injection — [9 Labs](https://portswigger.net/web-security/all-labs#xml-external-entity-xxe-injection)

### Intermediate Labs:
1. Cross-Site Scripting — [30 Labs](https://portswigger.net/web-security/all-labs#cross-site-scripting)
2. Cross-Site Request Forgery — [12 Labs](https://portswigger.net/web-security/all-labs#cross-site-request-forgery-csrf)
3. Cross-Origin Resource Sharing — [4 Labs](https://portswigger.net/web-security/all-labs#cross-origin-resource-sharing-cors)
4. Clickjacking — [5 Labs](https://portswigger.net/web-security/all-labs#clickjacking)
5. DOM-Based Vulnerabilities — [7 Labs](https://portswigger.net/web-security/all-labs#dom-based-vulnerabilities)
6. WebSockets — [3 Labs](https://portswigger.net/web-security/all-labs#websockets)

### Advanced Labs:
1. Insecure Deserialisation — [10 Labs](https://portswigger.net/web-security/all-labs#insecure-deserialization)
2. Server-Side Template Injection — [7 Labs](https://portswigger.net/web-security/all-labs#server-side-template-injection)
3. Web Cache Poisoning — [13 Labs](https://portswigger.net/web-security/all-labs#web-cache-poisoning)
4. HTTP Host Header Attacks — [7 Labs](https://portswigger.net/web-security/all-labs#http-host-header-attacks)
5. HTTP Request Smuggling — [22 Labs](https://portswigger.net/web-security/all-labs#http-request-smuggling)
6. OAuth Authentication — [6 Labs](https://portswigger.net/web-security/all-labs#oauth-authentication)
7. JWT Attacks — [8 Labs](https://portswigger.net/web-security/all-labs#jwt)
8. Prototype Pollution — [10 Labs](https://portswigger.net/web-security/all-labs#prototype-pollution)

### Other Resources
I found significant benefit from the following additional resources.
* [Micah Van Deusen’s BSCP Exam Review](https://micahvandeusen.com/burp-suite-certified-practitioner-exam-review/)
* [Juan Botes’ BSCP Practice Lab Notes](https://github.com/botesjuan/Burp-Suite-Certified-Practitioner-Exam-Study)

I noticed that majority of the YouTube channels online or included in the “Community Solutions” page for each lab did not provide explanations for how the attacks worked. However, the following YouTube channels did:
* [Intigriti](https://www.youtube.com/@intigriti/videos)
* [Daniel Redfern](https://www.youtube.com/@danielredfern9827/videos)
* [Rana Khalil](https://www.youtube.com/@RanaKhalil101/videos)
* [Seven Seas Security](https://www.youtube.com/@7SeasSecurity/videos)

## Exam Tips & Tricks
These are my tips and tricks to assist with passing the exam:
1. Read the exam [hints and guidance](https://portswigger.net/web-security/certification/exam-hints-and-guidance) and [what the exam involves](https://portswigger.net/web-security/certification/how-it-works#what-the-exam-involves) pages.
* Outbound traffic is restricted except for the public Burp Collaborator server and integrated exploit server.
* No pages or files are intentionally hidden, you never need to guess folders, filenames or parameter names.
* There is always an administrator account with the username “administrator”, plus a lower-privileged account called “carlos”.
* If you find a username enumeration vulnerability, you may be able to break into the low-privileged account using the following [username list](https://portswigger.net/web-security/authentication/auth-lab-usernames) and [password list](https://portswigger.net/web-security/authentication/auth-lab-passwords).
* Each application has up to one active user, who will be logged in either as a user or an administrator. You can assume that they will visit the homepage of the site every 15 seconds, and click any links in any emails they receive from the application.
* If you find an SSRF vulnerability, you can use it to read files by accessing an internal-only service service, running on localhost on port 6566.
* Host header attacks are fair game, but the _lab and lab-analytics cookies are part of core exam functionality, don’t waste your time tampering with them.
* The victim is running Chromium. When using the XSS Cheat Sheet, focus on vectors that work on Chrome (e.g. Burp Browser).
2. Use the automated content discovery feature within Burp Suite to identify new functionality.
* You can use Burp’s automated discovery tool to discover hidden directories, files and endpoints.
* When you have completed a stage of the exam, be sure to identify what new functionality is available. For example, after you have obtained a user account, identify which additional functionality wasn’t accessible when unauthenticated.
* There is a [guide here](https://portswigger.net/burp/documentation/desktop/testing-workflow/mapping/hidden-content/automated-discovery) on how to use the content discovery feature.
* This is a [wordlist](https://raw.githubusercontent.com/botesjuan/Burp-Suite-Certified-Practitioner-Exam-Study/main/wordlists/burp-labs-wordlist.txt) for directory fuzzing that is based on all of the practice labs.
3. Use the targeted scanning feature within Burp Suite to identify vulnerabilities to exploit.
* You won’t have time to manually identify all vulnerabilities to exploit within the exam.
* Start scanning as soon as possible, and focus on scanning specific insertion points or particular HTTP requests to ensure results are available quickly.
* Consider creating custom audit configurations within the scanning feature for vulnerabilities you are most interested in.
* This [page](https://portswigger.net/web-security/essential-skills/using-burp-scanner-during-manual-testing#scanning-a-specific-request) will show you how to scan a specific request and scan custom insertion points
4. Ensure you are focusing on vulnerabilities which are only relevant to the stage you are on.
* The three stages of the exam must be completed in order.
* This means that attempting to break into the admin interface if you don’t have a user account is a waste of time.
* Likewise, do not attempt to be reading files on the server’s file system if you don’t have access to the admin panel.
* The following table gives a good visual overview of which vulnerabilities apply at which stage:
![**Vulnerabilities Per Stage BSCP**](/blog/2023-07-24-study-exam-guide-burp-suite-certified-practitioner/vulns-per-stage-bscp.png)
5. Save your own personal notes and write-ups for the labs which include Proof-of-Concept (PoC) code.
* PortSwigger includes PoC code for exploiting the practice labs in the solutions.
* Save a copy of this for all of the practitioner labs in your own personal notes/wiki to refer to during the exam.
* I personally encountered functionality in the exam which I had seen in the practitioner labs, and was able to refer to my notes and modify the exploit code slightly to suit my needs.
* If you have the time, modify all of your PoC code from the practice labs to be suitable for the exam. For example, a lot of the XSS labs require you to simply call the print function. You can modify these to steal cookies instead which will be much more useful in the exam.