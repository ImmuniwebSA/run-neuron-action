# ImmuniwebSA/run-neuron-action@main

This is Github action to run ImmuniWeb Neuron automated scan

# How to use it?

First you should have an active ImmuniWeb Neuron project, where you can get API key and set Target URL values.
Save the API key and Target URL using GitHub Secrets with example names APIKEY and TARGET.
Then, use the following example of ./github/workflows/neuron.yml file, that needs to be added to your Github repository to run automated scans:

'''
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
'''
