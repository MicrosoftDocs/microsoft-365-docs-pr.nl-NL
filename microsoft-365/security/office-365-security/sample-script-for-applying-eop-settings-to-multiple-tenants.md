---
title: Voorbeeldscript voor EOP-instellingen - meerdere tenants
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: In dit artikel leert u hoe u PowerShell gebruikt om configuratie-instellingen toe te passen op uw tenants in Microsoft Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b7d856a7cec3bddc32455ba3afadf0323ddce935
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166589"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>Voorbeeldscript voor het toepassen van EOP-instellingen op meerdere tenants

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
-  [Zelfstandige versie van Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)

Met het volgende voorbeeldscript kunnen EOP-beheerders (Microsoft Exchange Online Protection) die meerdere tenants (bedrijven) beheren, Gebruikmaken van Exchange Online PowerShell om configuratie-instellingen te bekijken en/of toe te passen op hun tenants.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>Een script of cmdlet uitvoeren op meerdere tenants

1. Als u dat nog niet hebt gedaan, [installeert u de Exchange Online V2-module.](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)

2. Met een spreadsheet-app (bijvoorbeeld Excel) maakt u een CSV-bestand met de volgende details:

   - UserName column: Het account dat u gebruikt om verbinding te maken `admin@contoso.onmicrosoft.com` (bijvoorbeeld).
   - Cmdlet column: The cmdlet or command to run (example, `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name` ).

   Het bestand ziet er zo uit:

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. Sla het CSV-bestand op een locatie op die u eenvoudig kunt vinden (bijvoorbeeld c:\scripts\inputfile.csv).

4. Kopieer het [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script in Kladblok en sla het bestand op een locatie op die u eenvoudig kunt vinden (bijvoorbeeld c:\scripts).

5. Voer het script uit met behulp van de volgende syntaxis:

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   Hier is een voorbeeld:

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. Elke tenant wordt aangemeld en het script wordt uitgevoerd.

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants.ps1

> [!NOTE]
> Mogelijk moet u de regel `Connect-IPPSSession` in het script aanpassen aan uw omgeving. Voor Office 365 Germany is bijvoorbeeld een andere _ConnectionUri-waarde_ vereist dan de huidige waarde in een script. Zie Connect to Exchange Online Powershell (Verbinding maken met [Exchange Online Powershell) voor meer informatie.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)

```powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
#
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#
# .csv input file sample:
#
# UserName,Cmdlet
# admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
# admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name

# Get the .csv file name as an argument to this script.
$FilePath = $args[0]

# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath

# Load the EXO V2 module
Import-Module ExchangeOnlineManagement

# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {

# Get the current entry's UserName.
$UserName = $Company.UserName

# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet

# Connect to EOP PowerShell by using the current entry's UserName. Prompt for the password.
Connect-IPPSSession -UserPrincipalName $UserName -ConnectionUri https://ps.protection.outlook.com/powershell-liveid/

# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet

# End the current PowerShell session.
Disconnect-ExchangeOnline -Confirm:$false
}
```
