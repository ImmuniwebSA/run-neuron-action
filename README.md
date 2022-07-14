# ImmuniwebSA/run-neuron-action@main

This is Github action to run ImmuniWeb Neuron automated project scan.

## How to use it?

1. First, you should have an active ImmuniWeb Neuron project, where you can get API key and set Target URL values.

2. Save the API key and Target URL to your Github repository using Github Secrets with example names APIKEY and TARGET.

3. Then, use the following example of ./github/workflows/neuron.yml file, that needs to be added to your repository to run automated scans:

```
# An example .yml file to run ImmuniWeb Neuron scan
name: Run ImmuniWeb Neuron scan

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Run ImmuniWeb Neuron scan
        uses: ImmuniwebSA/run-neuron-action@main
        with:
            apikey: ${{ secrets.APIKEY }}
            target: ${{ secrets.TARGET }}
```
