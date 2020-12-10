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
ms.openlocfilehash: b18fc71171a93e2a2f415800bcf2b5abd5c5a526
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615862"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>Voorbeeldscript voor het toepassen van EOP-instellingen op meerdere tenants

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Met behulp van het volgende voorbeeldscript kunnen beheerders van Microsoft Exchange Online Protection (EOP) die meerdere tenants beheren, Exchange Online PowerShell gebruiken voor het weergeven en/of toepassen van configuratie-instellingen voor hun tenants.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>Een script of cmdlet uitvoeren op meerdere tenants

1. Als u dat nog niet hebt [gedaan, installeert u de module Exchange Online v2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).

2. Met behulp van een spreadsheet-app (bijvoorbeeld Excel), maakt u een CSV-bestand met de volgende informatie:

   - Gebruikersnaam: het account dat u gebruikt om verbinding te maken (bijvoorbeeld `admin@contoso.onmicrosoft.com` ).
   - Cmdlet-kolom: de cmdlet of opdracht die moet worden uitgevoerd (bijvoorbeeld `Get-AcceptedDomain` of `Get-AcceptedDomain | FT Name` ).

   Het bestand ziet er zo uit:

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. Sla het CSV-bestand op een locatie op die gemakkelijk te vinden is (bijvoorbeeld c:\scripts\inputfile.csv).

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

> [!NOTE]
> Mogelijk moet u de `Connect-IPPSSession` regel in het script wijzigen zodat deze overeenkomt met uw omgeving. In Office 365 Duitsland is bijvoorbeeld een andere _ConnectionUri_ waarde vereist dan de huidige waarde in een script. Zie verbinding maken met [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)voor meer informatie.

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
