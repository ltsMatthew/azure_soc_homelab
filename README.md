# Building a SOC Homelab with Azure Sentinel

## Introduction

In this guide, I will walk through setting up a SOC (Security Operations Center) homelab using Azure Sentinel for security monitoring. This lab will simulate real-world security analysis, incorporating Sysmon for endpoint logging and Log Analytics for data collection.

## Objectives

*  Deploy a Windows Virtual Machine (VM) on Azure

*  Install and configure Sysmon to collect logs

*  Forward logs to Azure Sentinel

*  Analyze logs using Kusto Query Language (KQL)

---------------------------------------------------------------------

## Step 1: Setting Up an Azure Virtual Machine

### 1.1 Create an Azure VM

1. Log in to the Azure Portal.

2. Go to and Select `Virtual Machines` > `Create` > `Azure virtual machine with preset configuration`

![AzureVM_preset_config](screenshots/AzureVM_preset_config.jpg)

3. On the `Choose recommended defaults that match your workload` page just select `Continue to create VM` at the bottom.

![AzureVM_contunue_to_create_VM](screenshots/AzureVM_contunue_to_create_VM.jpg)

4.1. Configure the following on the Basics Tab:

![AzureVM_basictab1](screenshots/AzureVM_basictab1.jpg)

Resoure Group - this is a container that will hold all the things we'll be creating (you can name it anything).

VM Name - give your VM a name.

Region - this is where your VM will be created.

![AzureVM_basictab1_5](screenshots/AzureVM_basictab1_5.jpg)

Image - Select `Windows 11 Pro, version 24H2 - x64 Gen2`

![AzureVM_basictab2](screenshots/AzureVM_basictab2.jpg)

For the Administrator Account section fill in a Username and Password.

Just below that make sure inbound port rules are configured as in the screenshot.

**Everything else on the Basics tab you can leave as default.**

After you followed all the above steps go ahead and click on:

`Next : Disks >` then `Next : Networking >` ... (just keep clicking next until you get to the `Review + Create` tab)

_The reason why we dont just go to the_ `Review + Create` _tab right away is because the settings won't autofill unless you go onto the tab_


