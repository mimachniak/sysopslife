---
title: "Microsoft 365 Add Shared Contact to user personal mailbox for phone caller identification and more."
classes: wide
date: 2024-07-26
excerpt: "Run by Azure Automation account PowerShell script that will add to user personal mailbox contact and update contact. You can distribution contacts to users based on organization requirements."
toc: true
header:
categories:
 - Microsoft365
 - PowerShell
 - Azure
tags:
  - PowerShell
  - Automation
  - M365
published: true
hidden: false
---


## Key features

* Shared conntacts will be added to user personal mailbox.
* Multiple contacts can be added / updated.
* Caller ID will be displayed on user Phone.
* Contact will be displayed in user contact section on mailbox.
* Contact will be synchonized to user phone contact.


## Prerequisites

* Azure Automation Account
* Service Principal for credentials

## Configuration 

Here you can find how to configure your environment step by step. Script is running in version **7** as for big organization reqaired paraller objecte in the same time. 

### Configure Service Principal

1.	Logon to https://entra.microsoft.com/ 
1.	Create app registration

![](../assets/images/ShareContact/M365-EXO-PS-01.png)  

    ![](../assets/images/ShareContact/M365-EXO-PS-01.png)  


    ![](../assets/images/ShareContact/M365-EXO-PS-02.png)  

1.	Permission granted for application

    ![](../assets/images/ShareContact/M365-EXO-PS-03.png)  

### Configure Azure Automation Account

### Import Microsoft.Graph modules


```powershell

Import-Module Microsoft.Graph.Authentication
Import-Module Microsoft.Graph.Beta.Users
Import-Module Microsoft.Graph.Users
Import-Module Microsoft.Graph.PersonalContacts
Import-Module Microsoft.Graph.Beta.PersonalContacts

```

1.	Logon to https://portal.azure.com
1.	Navigate to automation account
1.	On Menu select Modules -> Add module


    ![](../assets/images/ShareContact/M365-EXO-PS-04.png)  
    ![](../assets/images/ShareContact/M365-EXO-PS-05.png)  
    ![](../assets/images/ShareContact/M365-EXO-PS-06.png)  

1. Create credentials for **Runbook** used in script.

**User Name:** Application ID 
**Password:** Application secret 

    ![](../assets/images/ShareContact/M365-EXO-PS-07.png)

1. Create **Runbook** with PowerShell version **7.X**    
    ![](../assets/images/ShareContact/M365-EXO-PS-08.png)    


### PowerShell script on GitHub run by Automation Account

> GitHub Link 

Link to script on **GitHub** [M365-MgGraph-Add-Multiple-contact-Personal-Mailbox.ps1](https://github.com/mimachniak/sysopslife-scripts/blob/master/M365/M365-MgGraph-Add-Multiple-contact-Personal-Mailbox.ps1) can also be shown.

## Example of contact created in user personal mailbox

Example of output

   ![](../assets/images/ShareContact/M365-EXO-PS-09.png)  








