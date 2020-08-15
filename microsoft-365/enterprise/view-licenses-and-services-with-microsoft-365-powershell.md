---
title: Licenties en services van Microsoft 365 weergeven met PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- O365ITProTrain
- LIL_Placement
- PowerShell
ms.assetid: bb5260a9-a6a3-4f34-b19a-06c6699f6723
description: In dit artikel wordt uitgelegd hoe u PowerShell kunt gebruiken voor het bekijken van informatie over licenties, services en licenties die beschikbaar zijn in uw Microsoft 365-organisatie.
ms.openlocfilehash: 3275a513de3c114076e792ab6c5ef86b1413571c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689190"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a><span data-ttu-id="f4f80-103">Licenties en services van Microsoft 365 weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4f80-103">View Microsoft 365 licenses and services with PowerShell</span></span>

<span data-ttu-id="f4f80-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="f4f80-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="f4f80-105">Elk Microsoft 365-abonnement bestaat uit de volgende onderdelen:</span><span class="sxs-lookup"><span data-stu-id="f4f80-105">Every Microsoft 365 subscription consists of the following elements:</span></span>

- <span data-ttu-id="f4f80-106">**Licentie plannen** Dit zijn ook wel licentie-abonnementen of Microsoft 365-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="f4f80-106">**Licensing plans** These are also known as license plans or Microsoft 365 plans.</span></span> <span data-ttu-id="f4f80-107">Met licentie plannen wordt bepaald welke Microsoft 365-services beschikbaar zijn voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="f4f80-107">Licensing plans define the Microsoft 365 services that are available to users.</span></span> <span data-ttu-id="f4f80-108">Uw Microsoft 365-abonnement kan meerdere licentie abonnementen bevatten.</span><span class="sxs-lookup"><span data-stu-id="f4f80-108">Your Microsoft 365 subscription may contain multiple licensing plans.</span></span> <span data-ttu-id="f4f80-109">Een voorbeeld van een licentie plan is Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="f4f80-109">An example licensing plan would be Microsoft 365 E3.</span></span>
    
- <span data-ttu-id="f4f80-110">**Services** Dit worden ook wel service-abonnementen genoemd.</span><span class="sxs-lookup"><span data-stu-id="f4f80-110">**Services** These are also known as service plans.</span></span> <span data-ttu-id="f4f80-111">Services zijn de Microsoft 365-producten,-functies en-functies die beschikbaar zijn in elk licentie plan, bijvoorbeeld Exchange Online en Microsoft 365-apps voor Enterprise (voorheen Office 365 ProPlus).</span><span class="sxs-lookup"><span data-stu-id="f4f80-111">Services are the Microsoft 365 products, features, and capabilities that are available in each licensing plan, for example, Exchange Online and Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="f4f80-112">Gebruikers kunnen een licentie aan hen toewijzen vanuit verschillende licentie plannen die toegang hebben tot verschillende services.</span><span class="sxs-lookup"><span data-stu-id="f4f80-112">Users can have multiple licenses assigned to them from different licensing plans that grant access to different services.</span></span>
    
- <span data-ttu-id="f4f80-113">**Licentie** Elk licentie plan bevat het aantal licenties dat u hebt aangeschaft.</span><span class="sxs-lookup"><span data-stu-id="f4f80-113">**Licenses** Each licensing plan contains the number of licenses that you purchased.</span></span> <span data-ttu-id="f4f80-114">U kunt licenties toewijzen aan gebruikers, zodat ze gebruikmaken van de Microsoft 365-services die zijn gedefinieerd door het licentie plan.</span><span class="sxs-lookup"><span data-stu-id="f4f80-114">You assign licenses to users so they can use the Microsoft 365 services that are defined by the licensing plan.</span></span> <span data-ttu-id="f4f80-115">Voor elke gebruikersaccount is minimaal één licentie vereist, zodat ze zich kunnen aanmelden bij Microsoft 365 en de services kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f4f80-115">Every user account requires at least one license from one licensing plan so they can log on to Microsoft 365 and use the services.</span></span>
    
<span data-ttu-id="f4f80-116">Met PowerShell voor Microsoft 365 kunt u informatie weergeven over de beschikbare licentie-abonnementen, licenties en services in uw Microsoft 365-organisatie.</span><span class="sxs-lookup"><span data-stu-id="f4f80-116">You can use PowerShell for Microsoft 365 to view details about the available licensing plans, licenses, and services in your Microsoft 365 organization.</span></span> <span data-ttu-id="f4f80-117">Zie voor meer informatie over de producten, functies en services die beschikbaar zijn in de verschillende Office 365-abonnementen, [Office 365-abonnement opties](https://go.microsoft.com/fwlink/p/?LinkId=691147).</span><span class="sxs-lookup"><span data-stu-id="f4f80-117">For more information about the products, features, and services that are available in different Office 365 subscriptions, see [Office 365 Plan Options](https://go.microsoft.com/fwlink/p/?LinkId=691147).</span></span>


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="f4f80-118">Azure Active Directory PowerShell voor Graph module gebruiken</span><span class="sxs-lookup"><span data-stu-id="f4f80-118">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="f4f80-119">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="f4f80-119">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="f4f80-120">Voer de volgende opdracht uit om samenvattingsinformatie weer te geven over uw huidige licentie plannen en de beschikbare licenties voor elk abonnement:</span><span class="sxs-lookup"><span data-stu-id="f4f80-120">To view summary information about your current licensing plans and the available licenses for each plan, run this command:</span></span>
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

<span data-ttu-id="f4f80-121">De resultaten bevatten:</span><span class="sxs-lookup"><span data-stu-id="f4f80-121">The results contain:</span></span>
  
- <span data-ttu-id="f4f80-122">**SkuPartNumber:** Hier ziet u de beschikbare licentie plannen voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f4f80-122">**SkuPartNumber:** Shows the available licensing plans for your organization.</span></span> <span data-ttu-id="f4f80-123">Voorbeeld: `ENTERPRISEPACK` de naam van het licentie plan voor Office 365 Enterprise E3.</span><span class="sxs-lookup"><span data-stu-id="f4f80-123">For example, `ENTERPRISEPACK` is the license plan name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="f4f80-124">**Ingeschakeld:** Het aantal licenties dat u hebt aangeschaft voor een specifiek licentie plan.</span><span class="sxs-lookup"><span data-stu-id="f4f80-124">**Enabled:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="f4f80-125">**ConsumedUnits:** Het aantal licenties dat u hebt toegewezen aan gebruikers uit een specifiek licentie plan.</span><span class="sxs-lookup"><span data-stu-id="f4f80-125">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="f4f80-126">Als u informatie wilt bekijken over de Microsoft 365-services die in al uw licentie plannen beschikbaar zijn, geeft u eerst een lijst met uw licentie plannen weer.</span><span class="sxs-lookup"><span data-stu-id="f4f80-126">To view details about the Microsoft 365 services that are available in all of your license plans, first display a list of your license plans.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="f4f80-127">Vervolgens slaat u de gegevens van het licentie plan op in een variabele.</span><span class="sxs-lookup"><span data-stu-id="f4f80-127">Next, store the license plans information in a variable.</span></span>

```powershell
$licenses = Get-AzureADSubscribedSku
```

<span data-ttu-id="f4f80-128">Vervolgens kunt u de services in een specifiek licentie plan weergeven.</span><span class="sxs-lookup"><span data-stu-id="f4f80-128">Next, display the services in a specific license plan.</span></span>

```powershell
$licenses[<index>].ServicePlans
```

<span data-ttu-id="f4f80-129">\<index> is een geheel getal dat het rijnummer van het licentie plan opgeeft in de weergave van de `Get-AzureADSubscribedSku | Select SkuPartNumber` opdracht, min 1.</span><span class="sxs-lookup"><span data-stu-id="f4f80-129">\<index> is an integer that specifies the row number of the license plan from the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command, minus 1.</span></span>

<span data-ttu-id="f4f80-130">Als de weergave van de opdracht bijvoorbeeld `Get-AzureADSubscribedSku | Select SkuPartNumber` :</span><span class="sxs-lookup"><span data-stu-id="f4f80-130">For example, if the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command is this:</span></span>

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

<span data-ttu-id="f4f80-131">Voer de volgende opdracht uit om de services voor het ENTERPRISEPREMIUM-licentie plan weer te geven:</span><span class="sxs-lookup"><span data-stu-id="f4f80-131">Then the command to display the services for the ENTERPRISEPREMIUM license plan is this:</span></span>

```powershell
$licenses[2].ServicePlans
```

<span data-ttu-id="f4f80-132">ENTERPRISEPREMIUM is de derde rij.</span><span class="sxs-lookup"><span data-stu-id="f4f80-132">ENTERPRISEPREMIUM is the third row.</span></span> <span data-ttu-id="f4f80-133">Daarom is de indexwaarde (3-1) of 2.</span><span class="sxs-lookup"><span data-stu-id="f4f80-133">Therefore, the index value is (3 - 1), or 2.</span></span>

<span data-ttu-id="f4f80-134">Voor een volledige lijst met licentie plannen (ook wel productnamen genoemd), de opgenomen serviceplannen en de bijbehorende beschrijvende namen, raadpleegt u [productnamen en serviceplan-id's voor licenties](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span><span class="sxs-lookup"><span data-stu-id="f4f80-134">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="f4f80-135">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="f4f80-135">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="f4f80-136">Maak eerst [verbinding met uw Microsoft 365-Tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="f4f80-136">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

>[!Note]
><span data-ttu-id="f4f80-137">Er is een PowerShell-script beschikbaar waarmee de procedures die in dit onderwerp worden beschreven, worden geautomatiseerd.</span><span class="sxs-lookup"><span data-stu-id="f4f80-137">A PowerShell script is available that automates the procedures described in this topic.</span></span> <span data-ttu-id="f4f80-138">Met name kunt u met het script services weergeven en uitschakelen in uw Microsoft 365-organisatie, waaronder Sway.</span><span class="sxs-lookup"><span data-stu-id="f4f80-138">Specifically, the script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="f4f80-139">Zie [toegang tot Sway met PowerShell uitschakelen](disable-access-to-sway-with-microsoft-365-powershell.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f4f80-139">For more information, see [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span></span>
>
    
<span data-ttu-id="f4f80-140">Voer de volgende opdracht uit om samenvattingsinformatie weer te geven over uw huidige licentie plannen en de beschikbare licenties voor elk abonnement:</span><span class="sxs-lookup"><span data-stu-id="f4f80-140">To view summary information about your current licensing plans and the available licenses for each plan, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="f4f80-141">De PowerShell-core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell module en cmdlets met **MSOL** in de naam.</span><span class="sxs-lookup"><span data-stu-id="f4f80-141">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="f4f80-142">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f4f80-142">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="f4f80-143">De resultaten bevatten de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="f4f80-143">The results contain the following information:</span></span>
  
- <span data-ttu-id="f4f80-144">**AccountSkuId:** Geef de beschikbare licentie plannen voor uw organisatie weer met behulp van de syntaxis `<CompanyName>:<LicensingPlan>` .</span><span class="sxs-lookup"><span data-stu-id="f4f80-144">**AccountSkuId:** Show the available licensing plans for your organization by using the syntax `<CompanyName>:<LicensingPlan>`.</span></span>  <span data-ttu-id="f4f80-145">_\<CompanyName>_ is de waarde die u hebt opgegeven bij het registreren in Microsoft 365 en is uniek voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f4f80-145">_\<CompanyName>_ is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="f4f80-146">De _\<LicensingPlan>_ waarde is hetzelfde voor iedereen.</span><span class="sxs-lookup"><span data-stu-id="f4f80-146">The _\<LicensingPlan>_ value is the same for everyone.</span></span> <span data-ttu-id="f4f80-147">Met de waarde is de bedrijfsnaam bijvoorbeeld de naam van het `litwareinc:ENTERPRISEPACK`  `litwareinc` licentie plan en de naam van het licentie plan  `ENTERPRISEPACK` , de naam van het systeem voor Office 365 Enterprise E3.</span><span class="sxs-lookup"><span data-stu-id="f4f80-147">For example, in the value `litwareinc:ENTERPRISEPACK`, the company name is  `litwareinc`, and the licensing plan name  `ENTERPRISEPACK`, which is the system name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="f4f80-148">**ActiveUnits:** Het aantal licenties dat u hebt aangeschaft voor een specifiek licentie plan.</span><span class="sxs-lookup"><span data-stu-id="f4f80-148">**ActiveUnits:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="f4f80-149">**WarningUnits:** Het aantal licenties in een licentie plan dat u niet hebt verlengd, en dat na de respijtperiode van 30 dagen verloopt.</span><span class="sxs-lookup"><span data-stu-id="f4f80-149">**WarningUnits:** Number of licenses in a licensing plan that you haven't renewed, and that will expire after the 30-day grace period.</span></span>
    
- <span data-ttu-id="f4f80-150">**ConsumedUnits:** Het aantal licenties dat u hebt toegewezen aan gebruikers uit een specifiek licentie plan.</span><span class="sxs-lookup"><span data-stu-id="f4f80-150">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="f4f80-151">Voer de volgende opdracht uit als u meer informatie wilt bekijken over de Microsoft 365-services die beschikbaar zijn in al uw licentie abonnementen:</span><span class="sxs-lookup"><span data-stu-id="f4f80-151">To view details about the Microsoft 365 services that are available in all of your license plans, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="f4f80-152">In de volgende tabel ziet u de Microsoft 365-serviceplannen en de beschrijvende namen voor de meest gebruikte services.</span><span class="sxs-lookup"><span data-stu-id="f4f80-152">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="f4f80-153">Het kan zijn dat uw lijst met Serviceabonnementen verschillend is.</span><span class="sxs-lookup"><span data-stu-id="f4f80-153">Your list of service plans might be different.</span></span> 
  
|<span data-ttu-id="f4f80-154">**Service plan**</span><span class="sxs-lookup"><span data-stu-id="f4f80-154">**Service plan**</span></span>|<span data-ttu-id="f4f80-155">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="f4f80-155">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="f4f80-156">Sway</span><span class="sxs-lookup"><span data-stu-id="f4f80-156">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="f4f80-157">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f4f80-157">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="f4f80-158">Yammer</span><span class="sxs-lookup"><span data-stu-id="f4f80-158">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="f4f80-159">Beheer van Azure Rights Management (RMS)</span><span class="sxs-lookup"><span data-stu-id="f4f80-159">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="f4f80-160">Microsoft 365-apps voor Enterprise *(eerder Office 365 ProPlus)*</span><span class="sxs-lookup"><span data-stu-id="f4f80-160">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="f4f80-161">Skype voor Bedrijven Online</span><span class="sxs-lookup"><span data-stu-id="f4f80-161">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="f4f80-162">Office</span><span class="sxs-lookup"><span data-stu-id="f4f80-162">Office</span></span>  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="f4f80-163">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f4f80-163">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="f4f80-164">Exchange Online Abonnement 2</span><span class="sxs-lookup"><span data-stu-id="f4f80-164">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="f4f80-165">Voor een volledige lijst met licentie plannen (ook wel productnamen genoemd), de opgenomen serviceplannen en de bijbehorende beschrijvende namen, raadpleegt u [productnamen en serviceplan-id's voor licenties](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span><span class="sxs-lookup"><span data-stu-id="f4f80-165">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="f4f80-166">Als u informatie wilt bekijken over de Microsoft 365-services die beschikbaar zijn in een specifiek licentie plan, gebruikt u de volgende syntaxis.</span><span class="sxs-lookup"><span data-stu-id="f4f80-166">To view details about the Microsoft 365 services that are available in a specific licensing plan, use the following syntax.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

<span data-ttu-id="f4f80-167">In dit voorbeeld worden de services weergegeven die beschikbaar zijn in het licentie plan abonnement litwareinc: Enterprise Pack (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="f4f80-167">This example shows the services that are available in the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a><span data-ttu-id="f4f80-168">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f4f80-168">See also</span></span>

[<span data-ttu-id="f4f80-169">Microsoft 365-gebruikersaccounts, licenties en groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4f80-169">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f4f80-170">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4f80-170">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="f4f80-171">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4f80-171">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
