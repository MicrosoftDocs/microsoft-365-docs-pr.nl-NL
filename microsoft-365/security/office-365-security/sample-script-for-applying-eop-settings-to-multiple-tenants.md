---
title: Voorbeeldscript voor EOP instellingen-meerdere tenants
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: In dit artikel leert u hoe u PowerShell gebruikt om configuratie-instellingen toe te passen op uw tenants in Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: 6e33ceb6a9daa88bfefd4ec08ac9f2a9f34a942f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198677"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>Voorbeeldscript voor het toepassen van EOP-instellingen op meerdere tenants

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Met behulp van het volgende voorbeeldscript kunnen beheerders van Microsoft Exchange Online Protection (EOP) die meerdere tenants beheren (bedrijven), Windows PowerShell gebruiken om de configuratie-instellingen op hun tenants toe te passen.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>Een script of cmdlet uitvoeren op meerdere tenants

1. Maak een CSV-bestand met behulp van een toepassing, zoals Excel, en maak een CSV-bestand (bijvoorbeeld c:\scripts\inputfile.csv):

2. Geef in het CSV-bestand twee kolomnamen op: gebruikersnaam en cmdlet.

3. Voor elke rij in het CSV-bestand voegt u de naam van de beheerder van de Tenant toe in de kolom gebruikersnaam en de cmdlet voor het uitvoeren van de Tenant in de kolom cmdlet. Gebruik bijvoorbeeld admin@contoso.com en Get-AcceptedDomain.

4. Kopieer het [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script naar Kladblok en sla het bestand op een locatie op die gemakkelijk te vinden is (bijvoorbeeld c:\scripts).

5. Voer het script uit met behulp van de volgende syntaxis:

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   Hier ziet u een voorbeeld:

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. Elke Tenant wordt aangemeld en het script wordt uitgevoerd.

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
