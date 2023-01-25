# Introduction

Github action to install azure-cli on a debian-based system (eg: Ubuntu).

This is useful to test a workflow locally using [act](https://github.com/nektos/act) or on a self-hosted machine.

## Usage

```yaml
name: automatic-deploy

on:
  pull-request:
  push:
  workflow_dispatch:

jobs:
  deploy:
    # Replace `self-hosted-ubuntu` with the label of your self-hosted runner(s)
    runs-on: self-hosted-ubuntu
  steps:
    # install azure-cli
    - uses: pietrobolcato/install-azure-cli-action@v1
    # now run any step that would require the `az` command line utility, eg:
    - uses: azure/webapps-deploy@v2
```
