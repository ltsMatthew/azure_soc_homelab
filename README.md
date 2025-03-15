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

1.1.1 Log in to the Azure Portal.

1.1.2. Go to and Select `Virtual Machines` > `Create` > `Azure virtual machine with preset configuration`

![AzureVM_preset_config](screenshots/AzureVM_preset_config.jpg)

1.1.3. On the `Choose recommended defaults that match your workload` page just select `Continue to create VM` at the bottom.

![AzureVM_contunue_to_create_VM](screenshots/AzureVM_contunue_to_create_VM.jpg)

1.1.4. Configure the following on the Basics Tab:

![AzureVM_basictab1](screenshots/AzureVM_basictab1.png)

1.1.5. Resoure Group - this is a container that will hold all the things we'll be creating (you can name it anything).

1.1.6. VM Name - give your VM a name.

![AzureVM_basictab1_5](screenshots/AzureVM_basictab1_5.png)

1.1.7. Region - this is where your VM will be created.

1.1.8. Image - Select `Windows 10 Pro, version 22H2 - x64 Gen2(free services eligible)`

![AzureVM_basictab2](screenshots/AzureVM_basictab2.png)

1.1.9. For the Administrator Account section fill in a Username and Password.

1.1.10. Just below that make sure inbound port rules are configured as in the screenshot.

![AzureVM_basictab2_5](screenshots/AzureVM_basictab2_5.png)

1.1.11. Next make sure to tick the box in the Licensing part.

**Everything else on the Basics tab you can leave as default.**

1.1.12. After you followed all the above steps go ahead and click on `Next : Disks >` then `Next : Networking >` ...... (just keep clicking next until you get to the `Review + Create` tab)

_The reason why we dont just go to the_ `Review + Create` _tab right away is because the settings won't autofill unless you go onto each tab_.

4.1.9. We dont need anymore configurations for this VM so now we can go ahead and create it!


