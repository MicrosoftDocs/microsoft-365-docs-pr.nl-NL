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
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="2b898-103">Voorbeeldscript voor het toepassen van EOP-instellingen op meerdere tenants</span><span class="sxs-lookup"><span data-stu-id="2b898-103">Sample script for applying EOP settings to multiple tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2b898-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="2b898-104">**Applies to**</span></span>
-  [<span data-ttu-id="2b898-105">Zelfstandige versie van Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2b898-105">Exchange Online Protection standalone</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

<span data-ttu-id="2b898-106">Met het volgende voorbeeldscript kunnen EOP-beheerders (Microsoft Exchange Online Protection) die meerdere tenants (bedrijven) beheren, Gebruikmaken van Exchange Online PowerShell om configuratie-instellingen te bekijken en/of toe te passen op hun tenants.</span><span class="sxs-lookup"><span data-stu-id="2b898-106">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Exchange Online PowerShell to view and/or apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="2b898-107">Een script of cmdlet uitvoeren op meerdere tenants</span><span class="sxs-lookup"><span data-stu-id="2b898-107">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="2b898-108">Als u dat nog niet hebt gedaan, [installeert u de Exchange Online V2-module.](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)</span><span class="sxs-lookup"><span data-stu-id="2b898-108">If you haven't already, [install the Exchange Online V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

2. <span data-ttu-id="2b898-109">Met een spreadsheet-app (bijvoorbeeld Excel) maakt u een CSV-bestand met de volgende details:</span><span class="sxs-lookup"><span data-stu-id="2b898-109">Using an spreadsheet app (for example, Excel), create a .csv file with the following details:</span></span>

   - <span data-ttu-id="2b898-110">UserName column: Het account dat u gebruikt om verbinding te maken `admin@contoso.onmicrosoft.com` (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="2b898-110">UserName column: The account that you'll use to connect (for example, `admin@contoso.onmicrosoft.com`).</span></span>
   - <span data-ttu-id="2b898-111">Cmdlet column: The cmdlet or command to run (example, `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name` ).</span><span class="sxs-lookup"><span data-stu-id="2b898-111">Cmdlet column: The cmdlet or command to run (for example, `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name`).</span></span>

   <span data-ttu-id="2b898-112">Het bestand ziet er zo uit:</span><span class="sxs-lookup"><span data-stu-id="2b898-112">The file will look like this:</span></span>

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. <span data-ttu-id="2b898-113">Sla het CSV-bestand op een locatie op die u eenvoudig kunt vinden (bijvoorbeeld c:\scripts\inputfile.csv).</span><span class="sxs-lookup"><span data-stu-id="2b898-113">Save the .csv file in a location that's easy to find (for example, c:\scripts\inputfile.csv).</span></span>

4. <span data-ttu-id="2b898-114">Kopieer het [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script in Kladblok en sla het bestand op een locatie op die u eenvoudig kunt vinden (bijvoorbeeld c:\scripts).</span><span class="sxs-lookup"><span data-stu-id="2b898-114">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find (for example, c:\scripts).</span></span>

5. <span data-ttu-id="2b898-115">Voer het script uit met behulp van de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="2b898-115">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="2b898-116">Hier is een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="2b898-116">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="2b898-117">Elke tenant wordt aangemeld en het script wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="2b898-117">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="2b898-118">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="2b898-118">RunCmdletOnMultipleTenants.ps1</span></span>

> [!NOTE]
> <span data-ttu-id="2b898-119">Mogelijk moet u de regel `Connect-IPPSSession` in het script aanpassen aan uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="2b898-119">You might need to modify the `Connect-IPPSSession` line in the script to match your environment.</span></span> <span data-ttu-id="2b898-120">Voor Office 365 Germany is bijvoorbeeld een andere _ConnectionUri-waarde_ vereist dan de huidige waarde in een script.</span><span class="sxs-lookup"><span data-stu-id="2b898-120">For example, Office 365 Germany requires a different _ConnectionUri_ value than the current value in a script.</span></span> <span data-ttu-id="2b898-121">Zie Connect to Exchange Online Powershell (Verbinding maken met [Exchange Online Powershell) voor meer informatie.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)</span><span class="sxs-lookup"><span data-stu-id="2b898-121">For details, see Connect to [Exchange Online Powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

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
