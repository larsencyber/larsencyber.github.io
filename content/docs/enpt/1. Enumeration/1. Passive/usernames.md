---
title: Build Usernames List
weight: 7
sidebar:
  open: true
---
## Account Naming Convention
Identify the organisation's account name conventioning using Google dorking, common formats are:
```
first.last@company.com
f.last@company.com
last.f@company.com
flast@company.com
```

## LinkedIn Scraping
1. Create a LinkedIn sock puppet account.
2. Search the target organisation to find their company page.
3. Select the "People" section to see a list of current working employees.
4. Scrape the full names of all "People" in this tab.
5. There is a variety of tools out there that can do this, as well as data mining browser extensions.
6. Convert the list of full names, to email addresses, `John Doe` becomes `john.doe@target.com`.

There is also a quick tool which can be used, called CrossLinked.

https://github.com/m8sec/CrossLinked 

Usage:
```bash
python3 crosslinked.py -f '{first}.{last}@domain.com' company_name
python3 crosslinked.py -f 'domain\{f}{last}' -t 15 -j 2 company_name
```
⚠️ For best results, use the company name as it appears on LinkedIn "Target Company" not the domain name.

By default, CrossLinked will use google and bing search engines to identify employees of the target organization. After execution, two files (names.txt & names.csv) will appear in the current directory, unless modified in the CMD args.
* names.txt - List of unique user accounts in the specified format.
* names.csv - Raw search data. See the Parse section below for more.

Parse:
```bash
python3 crosslinked.py -f '{f}{last}@domain.com' names.csv
```
* This will parse employee names from "names.csv", collect the names, and add the unique names to "names.txt".

## Marketing Leads
Marketing leads websites like ZoomInfo or RocketReach will provide free trials that allow you to access email addresses of personnal at the target organisation. You can simply create a sock puppet account to access a free trial and then grab the relevant email addresses of your target. There are plenty of other websites out there that do this, but these two I have used historically. 

https://www.zoominfo.com/ 

https://rocketreach.co/ 