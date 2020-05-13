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
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="5c4cc-103">Voorbeeldscript voor het toepassen van EOP-instellingen op meerdere tenants</span><span class="sxs-lookup"><span data-stu-id="5c4cc-103">Sample script for applying EOP settings to multiple tenants</span></span>

<span data-ttu-id="5c4cc-104">Met het volgende voorbeeldscript kunnen EOP-beheerders (Microsoft Exchange Online Protection) die meerdere tenants (bedrijven) beheren, Windows PowerShell gebruiken om configuratie-instellingen toe te passen op hun tenants.</span><span class="sxs-lookup"><span data-stu-id="5c4cc-104">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Windows PowerShell to apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="5c4cc-105">Een script of cmdlet uitvoeren op meerdere tenants</span><span class="sxs-lookup"><span data-stu-id="5c4cc-105">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="5c4cc-106">Maak met een toepassing zoals Excel een CSV-bestand (bijvoorbeeld c:\scripts\inputfile.csv):</span><span class="sxs-lookup"><span data-stu-id="5c4cc-106">Using an application such as Excel, create a .csv file (for example, c:\scripts\inputfile.csv):</span></span>

2. <span data-ttu-id="5c4cc-107">Geef in het CSV-bestand twee kolomnamen op: UserName en Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5c4cc-107">In the .csv file, specify two column names: UserName and Cmdlet.</span></span>

3. <span data-ttu-id="5c4cc-108">Voeg voor elke rij in het CSV-bestand de beheerdersnaam van de tenant toe in de kolom Gebruikersnaam en de cmdlet die voor die tenant moet worden uitgevoerd in de kolom Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5c4cc-108">For each row in the .csv file, add the tenant's admin name in the UserName column and the cmdlet to run for that tenant in the Cmdlet column.</span></span> <span data-ttu-id="5c4cc-109">Gebruik bijvoorbeeld admin@contoso.com en Get-AcceptedDomain.</span><span class="sxs-lookup"><span data-stu-id="5c4cc-109">For example, use admin@contoso.com and Get-AcceptedDomain.</span></span>

4. <span data-ttu-id="5c4cc-110">Kopieer het [script RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) naar Kladblok en sla het bestand op een locatie die gemakkelijk te vinden is (bijvoorbeeld c:\scripts).</span><span class="sxs-lookup"><span data-stu-id="5c4cc-110">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find  (for example, c:\scripts).</span></span>

5. <span data-ttu-id="5c4cc-111">Voer het script uit met de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="5c4cc-111">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="5c4cc-112">Hier is een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="5c4cc-112">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenanats.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="5c4cc-113">Elke tenant wordt aangemeld bij en het script wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="5c4cc-113">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="5c4cc-114">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="5c4cc-114">RunCmdletOnMultipleTenants.ps1</span></span>

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
