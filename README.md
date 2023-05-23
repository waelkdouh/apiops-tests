# Overview
This repo is meant to test changes on the official ApiOps repo.

# Setup
1. Fork the repo.
2. Go your forked GitHub repo. Under `Settings` -> `Secrets and variables` -> `Actions`, add the following secrets and variables.
   | Configuration | Type | Purpose |
   | - | - | - |
   | AZURE_CLIENT_ID | Secret | Client ID of app registration for making APIM changes |   
   | AZURE_CLIENT_SECRET | Secret | Client secret of app registration for making APIM changes |
   | AZURE_SUBSCRIPTION_ID | Secret | APIM subscription ID |
   | AZURE_TENANT_ID | Secret | App registration tenant ID |
   | APIOPS_BRANCH_NAME | Variable | Branch name in ApiOps repo that will be used in the test |
   | APIOPS_RELEASE | Variable | Release name in ApiOps repo that will be used in the test |
   | AZURE_RESOURCE_GROUP_NAME | Variable | APIM resource group |
   | DEV_API_MANAGEMENT_SERVICE_NAME | Variable | DEV APIM instance name |
   | PROD_API_MANAGEMENT_SERVICE_NAME | Variable | PROD APIM instance name |
3. Go to ``Actions`` and run the ``Run extractor`` or ``Run publisher`` workflow. Here are the workflow parameters:
   | Parameter | Purpose |
   | - | - |
   | Publisher source | Allowed values are `release` or `branch`. The release or branch used will come from GitHub variables `APIOPS_RELEASE` and `APIOPS_BRANCH_NAME`. |   
   | Only publish artifacts modified in last commit | Self-explanatory (hopefully) |
