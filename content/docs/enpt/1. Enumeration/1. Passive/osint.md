---
title: Open Source Intelligence
weight: 3
sidebar:
  open: true
---
Open Source Intelligence (OSINT) is the process of gathering and analysing available information to assess threats, make decisions, or answer specific questions.

The use of OSINT in this example is to enumerate the organisation’s external attack surface through passive techniques. From a blue team perspective, our steps taken using OSINT should generate either zero to minimal logs for alerting and detection. Passive techniques aim to replicate genuine activity and should appear as benign upon any investigation.

## Google Dorking
Further Reading: https://www.exploit-db.com/google-hacking-database 

Look for emails:
```
site:target.com "email" OR "@"
```
Look for leaked documents on cloud storage:
```
site:docs.google.com "target"
site:dl.dropbox.com "target"
site:s3.amazonaws.com "target"
```
Look for any other interesting files:
```
site:target.com type:php
```
Other tricks:
```
inurl:target ## Requires a string or phrase to be in the URL
after:timestamp ## searches for pages created after a certain time
before:timestamp ## searches for pages created before a certain time
```

## Web Archives
Search target website on [Wayback Machine](https://web.archive.org/) to find historic pages and information disclosures.

## Social Media
Search for the target organisation's personnel on social media platforms such as Facebook, Instragram, X Networks, and LinkedIn. 

I am looking for leaked identification badges, employee ID formatting, and any other sensitive information disclosures. 

## Public Records
There are often a significant amount of public records available on businesses, properties, court hearing data, holding companies, shareholders and much more. The links for each of these vary depending on the jurisdiction and headquarters of the company. I won't be albe to include links to all of these here as there is just too many. 
* Vehicle registration and/or VIN searchs
* ABN lookup
* ASIC lookup
* Court hearing data lookup

## Cryptocurrency
Explore data stored on 41 blockchains using [Blockchair](https://blockchair.com/)