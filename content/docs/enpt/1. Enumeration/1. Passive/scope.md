---
title: Validate Scope Ownership
weight: 2
sidebar:
  open: true
---
Before I begin anything, I always validate that the scope the project sponsor has provided belongs to the organisation being targeted.

If I have any doubt, I will ask the project sponsor for any additional evidence required that permission has been granted.

## Whois lookup
Usage:
```bash
whois google.com
whois 1.1.1.1
```

## Scopebuddy
A utility that accepts a file containing target hosts (IP or DNS, one per line) and provides details on the ownership of those hosts. 

The ownership information is gathered from Border Gateway Protocol (BGP) and Whois data.
[https://github.com/kronicd/scopebuddy.py](https://github.com/kronicd/scopebuddy.py) 
Usage:
```bash
python3 scopebuddy.py hosts.txt -w -o output.txt -v
```
Example output:
```bash
IP,DNS,RDNS,ASN,IP Hoster,BGP CIDR,IP Owner,Whois CIDR,Shodan Ports
142.250.67.14,google.com,None,15169,"GOOGLE, US",142.250.67.0/24,GOOGLE,142.250.67.0/24,"80, 443"
2404:6800:4006:811::200e,google.com,None,15169,"GOOGLE, US",2404:6800:4006::/48,GOOGLE_IPV6_AP-20080930,2404:6800:4006::/48,No Data/Failed
1.1.1.1,1.1.1.1,None,13335,"CLOUDFLARENET, US",1.1.1.0/24,APNIC-LABS,1.1.1.0/24,"53, 80, 443, 2083, 2086, 2087, 8080, 8443, 8880"
```

## Cloud hosting
* Amazon Web Services does not require pre-authorisation as per [here](https://aws.amazon.com/security/penetration-testing/)
* Microsoft Azure does not require pre-authorisation as per [here](https://www.microsoft.com/en-us/msrc/pentest-rules-of-engagement)
* Google Cloud Platform does not require pre-authorisation as per [here](https://support.google.com/cloud/answer/6262505)

## Shared hosting
Sometimes an organisation will be using shared hosting for their primary website. 

In this instance, I must request taht the project sponsor provides written consent and permission from the hosting provider for the testing to be conducted. The most common responses from hosting providers are:
1. Testing cannot occur.
2. Testing can occur, but it must not impact the other services running on the shared hosting.

In both of these instances, it effectively negates any testing being completed. Very minimal "light touch" testing can be done when option 2 is suggested by the hosting provider. The best recommendation is for the organisation to migrate their web assets to private hosting so that thorough testing can be completed. Shared hosting will need to be added as a caveat in any reporting as a project limitation for external penetration testing.
