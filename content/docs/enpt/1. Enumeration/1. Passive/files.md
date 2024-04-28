---
title: File Metadata
weight: 8
sidebar:
  open: true
---
## Exiftool
We can check the file metadata to see if any sensitive information has been disclosed. 

Sometimes the "author" tag will include the name of an individual we could use for further attacks later on.

Usage:
```bash
exiftool file.pdf
```