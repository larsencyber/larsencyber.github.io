---
title: Directory Fuzzing
weight: 3
sidebar:
  open: true
---

## Favourite Wordlists
```
Work in progress.
```

## Feroxbuster
Includes recursion by default.
* Proxy via Burp
* Extension
* Wordlist
```bash
feroxbuster -u https://target.com -k -w wordlist.txt --insecure --proxy http://127.0.0.1:8080 -x aspx
```

## Gobuster
No recursion.
```bash
gobuster dir -u https://target.com -k -w wordlist.txt -x aspx
```