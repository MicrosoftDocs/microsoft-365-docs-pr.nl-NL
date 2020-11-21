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
ms.openlocfilehash: dbb4135c89ac8d351c40bd7d9ce5301500a9b81b
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376565"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="b9589-103">Voorbeeldscript voor het toepassen van EOP-instellingen op meerdere tenants</span><span class="sxs-lookup"><span data-stu-id="b9589-103">Sample script for applying EOP settings to multiple tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b9589-104">Met behulp van het volgende voorbeeldscript kunnen beheerders van Microsoft Exchange Online Protection (EOP) die meerdere tenants beheren, Exchange Online PowerShell gebruiken voor het weergeven en/of toepassen van configuratie-instellingen voor hun tenants.</span><span class="sxs-lookup"><span data-stu-id="b9589-104">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Exchange Online PowerShell to view and/or apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="b9589-105">Een script of cmdlet uitvoeren op meerdere tenants</span><span class="sxs-lookup"><span data-stu-id="b9589-105">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="b9589-106">Als u dat nog niet hebt [gedaan, installeert u de module Exchange Online v2](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span><span class="sxs-lookup"><span data-stu-id="b9589-106">If you haven't already, [install the Exchange Online V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

2. <span data-ttu-id="b9589-107">Met behulp van een spreadsheet-app (bijvoorbeeld Excel), maakt u een CSV-bestand met de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="b9589-107">Using an spreadsheet app (for example, Excel), create a .csv file with the following details:</span></span>

   - <span data-ttu-id="b9589-108">Gebruikersnaam: het account dat u gebruikt om verbinding te maken (bijvoorbeeld `admin@contoso.onmicrosoft.com` ).</span><span class="sxs-lookup"><span data-stu-id="b9589-108">UserName column: The account that you'll use to connect (for example, `admin@contoso.onmicrosoft.com`).</span></span>
   - <span data-ttu-id="b9589-109">Cmdlet-kolom: de cmdlet of opdracht die moet worden uitgevoerd (bijvoorbeeld `Get-AcceptedDomain` of `Get-AcceptedDomain | FT Name` ).</span><span class="sxs-lookup"><span data-stu-id="b9589-109">Cmdlet column: The cmdlet or command to run (for example, `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name`).</span></span>

   <span data-ttu-id="b9589-110">Het bestand ziet er zo uit:</span><span class="sxs-lookup"><span data-stu-id="b9589-110">The file will look like this:</span></span>

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. <span data-ttu-id="b9589-111">Sla het CSV-bestand op een locatie op die gemakkelijk te vinden is (bijvoorbeeld c:\scripts\inputfile.csv).</span><span class="sxs-lookup"><span data-stu-id="b9589-111">Save the .csv file in a location that's easy to find (for example, c:\scripts\inputfile.csv).</span></span>

4. <span data-ttu-id="b9589-112">Kopieer het [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script naar Kladblok en sla het bestand op een locatie op die gemakkelijk te vinden is (bijvoorbeeld c:\scripts).</span><span class="sxs-lookup"><span data-stu-id="b9589-112">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find (for example, c:\scripts).</span></span>

5. <span data-ttu-id="b9589-113">Voer het script uit met behulp van de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="b9589-113">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="b9589-114">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="b9589-114">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="b9589-115">Elke Tenant wordt aangemeld en het script wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="b9589-115">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="b9589-116">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="b9589-116">RunCmdletOnMultipleTenants.ps1</span></span>

> [!NOTE]
> <span data-ttu-id="b9589-117">Mogelijk moet u de `Connect-IPPSSession` regel in het script wijzigen zodat deze overeenkomt met uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="b9589-117">You might need to modify the `Connect-IPPSSession` line in the script to match your environment.</span></span> <span data-ttu-id="b9589-118">In Office 365 Duitsland is bijvoorbeeld een andere _ConnectionUri_ waarde vereist dan de huidige waarde in een script.</span><span class="sxs-lookup"><span data-stu-id="b9589-118">For example, Office 365 Germany requires a different _ConnectionUri_ value than the current value in a script.</span></span> <span data-ttu-id="b9589-119">Zie verbinding maken met [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b9589-119">For details, see Connect to [Exchange Online Powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

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
