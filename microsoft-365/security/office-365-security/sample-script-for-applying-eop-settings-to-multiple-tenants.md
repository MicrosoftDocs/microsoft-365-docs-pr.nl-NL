---
title: Voorbeeldscript voor EOP-instellingen - meerdere tenants
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: In dit artikel leert u hoe u PowerShell gebruiken om configuratie-instellingen toe te passen op uw tenants in Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: c25bafe9ece71264931d8f059dd726147a6d28a4
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209137"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>Voorbeeldscript voor het toepassen van EOP-instellingen op meerdere tenants

Met het volgende voorbeeldscript kunnen EOP-beheerders (Microsoft Exchange Online Protection) die meerdere tenants (bedrijven) beheren, Windows PowerShell gebruiken om configuratie-instellingen toe te passen op hun tenants.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>Een script of cmdlet uitvoeren op meerdere tenants

1. Maak met een toepassing zoals Excel een CSV-bestand (bijvoorbeeld c:\scripts\inputfile.csv):

2. Geef in het CSV-bestand twee kolomnamen op: UserName en Cmdlet.

3. Voeg voor elke rij in het CSV-bestand de beheerdersnaam van de tenant toe in de kolom Gebruikersnaam en de cmdlet die voor die tenant moet worden uitgevoerd in de kolom Cmdlet. Gebruik bijvoorbeeld admin@contoso.com en Get-AcceptedDomain.

4. Kopieer het [script RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) naar Kladblok en sla het bestand op een locatie die gemakkelijk te vinden is (bijvoorbeeld c:\scripts).

5. Voer het script uit met de volgende syntaxis:

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   Hier is een voorbeeld:

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenanats.ps1" "c:\scripts\inputfile.csv"
   ```

6. Elke tenant wordt aangemeld bij en het script wordt uitgevoerd.

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants.ps1

```powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#
# .csv input file sample:
# UserName,Cmdlet
# admin@contoso.com,Get-AcceptedDomain | ft Name
# URI for connecting to remote Windows PowerShell
$URI = "https://ps.protection.outlook.com/powershell-liveid/"
# Get the .csv file name as an argument to this script.
$FilePath = $args[0]
# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath
# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {
# Get the current entry's UserName.
$UserName = $Company.UserName
# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet
# Create a PowerShell credential object by using the current entry's UserName. Prompt for the password.
$UserCredential = Get-Credential -username $UserName
# Log on to a new Windows PowerShell session.
$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri $URI -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $Session
# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet
# End the current PowerShell session.
Remove-PsSession -Session $Session
}
```
