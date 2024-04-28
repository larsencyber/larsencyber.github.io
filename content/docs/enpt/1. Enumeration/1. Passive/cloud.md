---
title: Cloud Resources
weight: 10
sidebar:
  open: true
---
## Cloud_enum
This is a multi-cloud OSINT tool which enumerates public resources in AWS, Azure and Google Cloud. 

https://github.com/initstring/cloud_enum

This is best used in a wildcard scope for an External Penetration Test, as it may be possible to discover cloud assets that are public facing for a target organisation that they were not aware of.

Usage:
```bash
python3 cloud_enum.py -k keyword1 -k keyword2 -k keyword3 -t 10 --logfile output.txt
```