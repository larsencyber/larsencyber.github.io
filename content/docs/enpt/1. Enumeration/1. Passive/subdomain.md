---
title: Subdomains
weight: 5
sidebar:
  open: true
---
## DNS Dumpster
DNS Dumpster is a free domain research tool that can discover hosts related to a domain. 

https://dnsdumpster.com/

## DNS History
Over 12 billion DNS records archived since 2009.

https://dnshistory.org/ 

## Amass
The OWASP Amass Project performs network mapping of attack surfaces and external asset discovery using open source information gathering and active reconnaissance techniques.

It requires API keys to be supplied from a variety of other websites.

Tool: https://github.com/owasp-amass/amass

DNS enumeration:
```bash
amass enum -v -src -ip -brute -min-for-recursive 2 -d example.com
```

## Subfinder
Subfinder is a fast tool for passive subdomain enumeration.

Tool: https://github.com/projectdiscovery/subfinder 

Usage:
```bash
subfinder -d target.com
```

## Shodan
Using a premium Shodan account ($5 on Black Friday sales) you can search for SSL certificates based on target domain.

```bash
ssl:target.com
```
