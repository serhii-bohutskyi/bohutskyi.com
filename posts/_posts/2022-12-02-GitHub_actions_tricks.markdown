---
title: GitHub Action tricks
description: github,action,workflow,tricks
---

### Environment variables
[GitHub Action Documentation](https://docs.github.com/en/actions/learn-github-actions/environment-variables#default-environment-variables)

Sample
{% raw %}
```yaml
${{ github.workspace }}
```
{% endraw %}

Usage
{% raw %}
```yaml
- name: Archive 
  uses: actions/upload-artifact@v3
  with:
    name: test-report
    path: ${{ github.workspace }}/test_report.zip
```
{% endraw %}

### Workflow with manual run

Workflow with manual run and input for branch

{% raw %}
```yaml
name: Workflow_name
on:
  workflow_dispatch:
    inputs:
      branch:
        description: 'Branch'
        required: true
        default: 'main'
```
{% endraw %}

### Concurrency in the workflow
{% raw %}
```yaml
concurrency:
  group: workflow_name-${{ inputs.branch || github.ref }}
  cancel-in-progress: true
```
{% endraw %}

### Checkout action
Checkout GitHub repository with corresponding branch
{% raw %}
```yaml
- uses: actions/checkout@v3
  with:
    ref: ${{ inputs.branch }}
```
{% endraw %}

### Java setup action
{% raw %}
```yaml
- uses: actions/setup-java@v3
  with:
    distribution: 'adopt'
    java-version: 17
```
{% endraw %}

### Archive action

{% raw %}
```yaml
- name: Archive 
  uses: actions/upload-artifact@v3
  with:
    name: test-report
    path: ${{ github.workspace }}/test_report.zip
    retention-days: 5
```
{% endraw %}

### Zip action

https://github.com/marketplace/actions/easy-zip-files

{% raw %}
```yaml
- uses: vimtor/action-zip@v1.1
  with:
    files: your_folder_in_workspace
    recursive: false
    dest: archive_name.zip
```
{% endraw %}

### Bash script in action
{% raw %}
```yaml
- name: Run script
  run: ./.github/scripts/my_custom_script.sh -w ${{ github.workspace }} -d true
  shell: bash
```
{% endraw %}

### Permission for a script

In case of usage script in the GitHub Action you might have such error on execution
```bash
/home/runner/work/_temp/adc06633-b88b-406d-b270-52d79b4e6245.sh: line 1: ./.github/scripts/my_script.sh: Permission denied
Error: Process completed with exit code 126.
```
To fix this issue need to run this command locally and push changes to the file's index:
```bash
$ git update-index --chmod=+x ./.github/scripts/my_script.sh
```

### Google Java Format Action
https://github.com/axel-op/googlejavaformat-action

{% raw %}
```yaml
- uses: axel-op/googlejavaformat-action@v3
  with:
    args: "--skip-sorting-imports --replace"
```
{% endraw %}

## Template for the java workflow
{% raw %}
```yaml
name: Run coverage
#manual run
on:
  workflow_dispatch:
    inputs:
      branch:
        description: 'Branch'
        required: true
        default: 'main'

concurrency:
  group: coverage-${{ inputs.branch || github.ref }}
  cancel-in-progress: true

jobs:
  run_coverage:
    name: Coverage (${{ inputs.branch || github.ref }})
    runs-on: ubuntu-latest
    steps:
#     checkout
      - uses: actions/checkout@v3
        with:
          ref: ${{ inputs.branch }}
#     java install
      - uses: actions/setup-java@v3
        with:
          distribution: 'adopt'
          java-version: 17
#     run command
      - run: ./gradlew coverage --continue
        
#     sample of usage bash, copy coverage report to ${{ github.workspace }}/coverage
      - name: Copy report
        run: ./.github/scripts/copy.sh -f ${{ github.workspace }}/coverage
        shell: bash
#     zip folder
      - uses: vimtor/action-zip@v1.1
        with:
          files: coverage
          recursive: false
          dest: coverage_report.zip
#     archive result and save
      - name: Archive results
        uses: actions/upload-artifact@v3
        with:
          name: coverage-report
          path: ${{ github.workspace }}/coverage_report.zip
          retention-days: 5
```
{% endraw %}