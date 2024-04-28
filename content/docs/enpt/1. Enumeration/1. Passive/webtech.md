---
title: Web Technology
weight: 4
sidebar:
  open: true
---
## Wappalyzer
Wappalyzer is both a website and a browser extension that will quickly identify all technologies in-use on a website.
Website: https://www.wappalyzer.com/ 
FireFox Extension: https://addons.mozilla.org/en-US/firefox/addon/wappalyzer/

## GoWitness
GoWitness is a website screenshot utility written in GoLang, that uses Chrome Headless to generate screenshots of web interfaces using the command line, with a handy report viewer to process the results.

This is also really useful after active enumeration, directory fuzzing, to see if we can identify any interesting web pages or login portals. 
Tool: https://github.com/sensepost/gowitness
Wiki: https://github.com/sensepost/gowitness/wiki 
Usage: https://github.com/sensepost/gowitness/wiki/Usage

Run:
```bash
./gowitness file -f targs.txt --fullpage
```
Server:
```bash
./gowitness server 
```

## DNS TXT Records
```bash
nslookup -type=TXT target.com
```