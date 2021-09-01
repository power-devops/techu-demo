# Demo Gitlab CI/CD &amp; IBM Cloud PowerVS for IBM vTechU 2021

This is a demonstration how AIX and Linux LPARs in IBM Cloud PowerVS can be used to automate builds using Gitlab CI/CD.

In this repo you will find gitlab-ci.yml with a sample script to create and destroy an AIX LPAR, small C program (hello, world!) and Makefile.

## Prereqs

* IBM Cloud account with API key
* IBM PowerVS service
* Network in IBM PowerVS service
* base image with IBM xlC compiler

IBM Cloud API key (IBMCLOUD_API_KEY), PowerVS Instance ID (IBMCLOUD_PVS_INSTANCE), PowerVS Network ID (IBMCLOUD_PVS_NETWORK) must be set using Project -> Settings -> CI/CD -> Variables.

### Creating API key

```
ibmcloud iam api-key-create mykey -d 'My API key'
```

### Gettings PowerVS instance id

```
ibmcloud pi sl | awk '/My PowerVS Service/ {print $1}'
```

### Getting PowerVS Network ID

```
ibmcloud pi nets | awk '/my_powervs_net/ {print $1}'
```

