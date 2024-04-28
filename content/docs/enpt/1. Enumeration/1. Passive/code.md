---
title: Code Repos
weight: 11
sidebar:
  open: true
---
## GitGot
GitGot is a semi-automated, feedback-driven tool to empower users to rapidly search through troves of public data on GitHub for sensitive secrets.

https://github.com/BishopFox/GitGot

Usage:
```bash
./gitgot-docker.sh -q example.com
```

It is best to create a sock puppet GitHub account and then create a GitHub API token with no permissios/no scope and copy the token into GitGot python code.
```bash
ACCESS_TOKEN = "<NO-PERMISSION-GITHUB-TOKEN-HERE>"
```

## Grep.App
Searches code from over ~500,000 public repositories on GitHub.

https://grep.app/