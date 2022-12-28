---
title: GitHub action make executable script
description: bash,github,action,workflow,script
---

In case of usage script in the GitHub Action you might have such error on execution
```bash
/home/runner/work/_temp/adc06633-b88b-406d-b270-52d79b4e6245.sh: line 1: ./.github/scripts/my_script.sh: Permission denied
Error: Process completed with exit code 126.
```
To fix this issue need to run this command locally and push changes to the file's index:
```bash
$ git update-index --chmod=+x ./.github/scripts/my_script.sh
```

---
