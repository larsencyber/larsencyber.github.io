---
title: Open Source Intelligence
weight: 3
sidebar:
  open: true
---
Open Source Intelligence (OSINT) is the process of gathering and analysing available information to assess threats, make decisions, or answer specific questions.

The use of OSINT in this example is to enumerate the organisation’s external attack surface through passive techniques. From a blue team perspective, our steps taken using OSINT should generate either zero to minimal logs for alerting and detection. Passive techniques aim to replicate genuine activity and should appear as benign upon any investigation.

## Google Dorking
Look for leaked documents:
```
site:docs.google.com "keyword"
site:dl.dropbox.com "keyword"
site:s3.amazonaws.com "keyword"
```

## Web Archives
Search target on [Wayback Machine](https://web.archive.org/)
```
https://web.archive.org/
```
## Social Media
Search for the target organisation's personnel on social media platforms such as Facebook, Instragram, X Networks, and LinkedIn.

## Public Records
* Vehicle registration and/or VIN searchs
* ABN lookup
* ASIC lookup
* Court hearing data lookup

## Cryptocurrency
Explore data stored on 41 blockchains using [Blockchair](https://blockchair.com/)
```
https://blockchair.com/
```