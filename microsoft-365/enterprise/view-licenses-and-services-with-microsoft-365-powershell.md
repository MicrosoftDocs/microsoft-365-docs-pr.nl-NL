---
title: Microsoft 365-licenties en -services weergeven met PowerShell
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
description: Hier wordt uitgelegd hoe u PowerShell gebruikt om informatie weer te geven over de licentieplannen, services en licenties die beschikbaar zijn in uw Microsoft 365-organisatie.
ms.openlocfilehash: 08f48301001ee6a40318428f3310eab8b0d0a351
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924634"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a><span data-ttu-id="2e1f2-103">Microsoft 365-licenties en -services weergeven met PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e1f2-103">View Microsoft 365 licenses and services with PowerShell</span></span>

<span data-ttu-id="2e1f2-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="2e1f2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="2e1f2-105">Elk Microsoft 365-abonnement bestaat uit de volgende elementen:</span><span class="sxs-lookup"><span data-stu-id="2e1f2-105">Every Microsoft 365 subscription consists of the following elements:</span></span>

- <span data-ttu-id="2e1f2-106">**Licentieplannen** Deze worden ook wel licentieplannen of Microsoft 365-abonnementen genoemd.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-106">**Licensing plans** These are also known as license plans or Microsoft 365 plans.</span></span> <span data-ttu-id="2e1f2-107">Licentieplannen definiëren de Microsoft 365-services die beschikbaar zijn voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-107">Licensing plans define the Microsoft 365 services that are available to users.</span></span> <span data-ttu-id="2e1f2-108">Uw Microsoft 365-abonnement kan meerdere licentieplannen bevatten.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-108">Your Microsoft 365 subscription may contain multiple licensing plans.</span></span> <span data-ttu-id="2e1f2-109">Een voorbeeld van een licentieplan is Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-109">An example licensing plan would be Microsoft 365 E3.</span></span>
    
- <span data-ttu-id="2e1f2-110">**Services** Deze worden ook wel serviceplannen genoemd.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-110">**Services** These are also known as service plans.</span></span> <span data-ttu-id="2e1f2-111">Services zijn de Microsoft 365-producten, -functies en -mogelijkheden die beschikbaar zijn in elk licentieplan, bijvoorbeeld Exchange Online en Microsoft 365 Apps voor ondernemingen (eerder Office 365 ProPlus genoemd).</span><span class="sxs-lookup"><span data-stu-id="2e1f2-111">Services are the Microsoft 365 products, features, and capabilities that are available in each licensing plan, for example, Exchange Online and Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="2e1f2-112">Gebruikers kunnen meerdere licenties aan hen hebben toegewezen vanuit verschillende licentieplannen die toegang verlenen tot verschillende services.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-112">Users can have multiple licenses assigned to them from different licensing plans that grant access to different services.</span></span>
    
- <span data-ttu-id="2e1f2-113">**Licenties** Elk licentieplan bevat het aantal licenties dat u hebt gekocht.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-113">**Licenses** Each licensing plan contains the number of licenses that you purchased.</span></span> <span data-ttu-id="2e1f2-114">U wijst licenties toe aan gebruikers, zodat ze de Microsoft 365-services kunnen gebruiken die zijn gedefinieerd in het licentieplan.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-114">You assign licenses to users so they can use the Microsoft 365 services that are defined by the licensing plan.</span></span> <span data-ttu-id="2e1f2-115">Voor elk gebruikersaccount is ten minste één licentie van één licentieplan vereist, zodat ze zich kunnen aanmelden bij Microsoft 365 en de services kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-115">Every user account requires at least one license from one licensing plan so they can log on to Microsoft 365 and use the services.</span></span>
    
<span data-ttu-id="2e1f2-116">U kunt PowerShell voor Microsoft 365 gebruiken om details weer te geven over de beschikbare licentieplannen, licenties en services in uw Microsoft 365-organisatie.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-116">You can use PowerShell for Microsoft 365 to view details about the available licensing plans, licenses, and services in your Microsoft 365 organization.</span></span> <span data-ttu-id="2e1f2-117">Zie Opties voor Office 365-abonnementen voor meer informatie over de producten, functies en services die beschikbaar zijn in verschillende Office [365-abonnementen.](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)</span><span class="sxs-lookup"><span data-stu-id="2e1f2-117">For more information about the products, features, and services that are available in different Office 365 subscriptions, see [Office 365 Plan Options](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options).</span></span>


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="2e1f2-118">De Azure Active Directory PowerShell voor Graph-module gebruiken</span><span class="sxs-lookup"><span data-stu-id="2e1f2-118">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="2e1f2-119">Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="2e1f2-119">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="2e1f2-120">Voer deze opdracht uit als u overzichtsgegevens wilt weergeven over uw huidige licentieplannen en de beschikbare licenties voor elk abonnement:</span><span class="sxs-lookup"><span data-stu-id="2e1f2-120">To view summary information about your current licensing plans and the available licenses for each plan, run this command:</span></span>
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

<span data-ttu-id="2e1f2-121">De resultaten bevatten:</span><span class="sxs-lookup"><span data-stu-id="2e1f2-121">The results contain:</span></span>
  
- <span data-ttu-id="2e1f2-122">**SkuPartNumber:** Toont de beschikbare licentieplannen voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-122">**SkuPartNumber:** Shows the available licensing plans for your organization.</span></span> <span data-ttu-id="2e1f2-123">Is bijvoorbeeld `ENTERPRISEPACK` de naam van het licentieplan voor Office 365 Enterprise E3.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-123">For example, `ENTERPRISEPACK` is the license plan name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="2e1f2-124">**Ingeschakeld:** Het aantal licenties dat u hebt gekocht voor een specifiek licentieplan.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-124">**Enabled:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="2e1f2-125">**ConsumedUnits:** Het aantal licenties dat u aan gebruikers hebt toegewezen vanuit een specifiek licentieplan.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-125">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="2e1f2-126">Als u details wilt bekijken over de Microsoft 365-services die beschikbaar zijn in al uw licentieplannen, geeft u eerst een lijst met uw licentieplannen weer.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-126">To view details about the Microsoft 365 services that are available in all of your license plans, first display a list of your license plans.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="2e1f2-127">Sla vervolgens de informatie over de licentieplannen op in een variabele.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-127">Next, store the license plans information in a variable.</span></span>

```powershell
$licenses = Get-AzureADSubscribedSku
```

<span data-ttu-id="2e1f2-128">Vervolgens worden de services weergegeven in een specifiek licentieplan.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-128">Next, display the services in a specific license plan.</span></span>

```powershell
$licenses[<index>].ServicePlans
```

<span data-ttu-id="2e1f2-129">\<index> is een geheel getal dat het rijnummer van het licentieplan aangeeft vanaf de weergave van de `Get-AzureADSubscribedSku | Select SkuPartNumber` opdracht, min 1.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-129">\<index> is an integer that specifies the row number of the license plan from the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command, minus 1.</span></span>

<span data-ttu-id="2e1f2-130">Als de weergave van de opdracht bijvoorbeeld de volgende `Get-AzureADSubscribedSku | Select SkuPartNumber` is:</span><span class="sxs-lookup"><span data-stu-id="2e1f2-130">For example, if the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command is this:</span></span>

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

<span data-ttu-id="2e1f2-131">De opdracht om de services voor het ENTERPRISEPREMIUM-licentieplan weer te geven, is de volgende:</span><span class="sxs-lookup"><span data-stu-id="2e1f2-131">Then the command to display the services for the ENTERPRISEPREMIUM license plan is this:</span></span>

```powershell
$licenses[2].ServicePlans
```

<span data-ttu-id="2e1f2-132">ENTERPRISEPREMIUM is de derde rij.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-132">ENTERPRISEPREMIUM is the third row.</span></span> <span data-ttu-id="2e1f2-133">Daarom is de indexwaarde (3 - 1) of 2.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-133">Therefore, the index value is (3 - 1), or 2.</span></span>

<span data-ttu-id="2e1f2-134">Zie Productnamen en [serviceplanaanduidingen](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)voor licenties voor een volledige lijst met licentieplannen (ook wel productnamen genoemd), de bijbehorende serviceplannen en de bijbehorende vriendelijke namen.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-134">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="2e1f2-135">De Microsoft Azure Active Directory-module voor Windows PowerShell gebruiken</span><span class="sxs-lookup"><span data-stu-id="2e1f2-135">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="2e1f2-136">Maak eerst [verbinding met uw Microsoft 365-tenant.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="2e1f2-136">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

>[!Note]
><span data-ttu-id="2e1f2-137">Er is een PowerShell-script beschikbaar dat de procedures automatiseert die in dit onderwerp worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-137">A PowerShell script is available that automates the procedures described in this topic.</span></span> <span data-ttu-id="2e1f2-138">Met het script kunt u services weergeven en uitschakelen in uw Microsoft 365-organisatie, inclusief Sway.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-138">Specifically, the script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="2e1f2-139">Zie Toegang tot [Sway uitschakelen met PowerShell voor meer informatie.](disable-access-to-sway-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="2e1f2-139">For more information, see [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span></span>
>
    
<span data-ttu-id="2e1f2-140">Voer de volgende opdracht uit als u overzichtsinformatie wilt weergeven over uw huidige licentieplannen en de beschikbare licenties voor elk abonnement:</span><span class="sxs-lookup"><span data-stu-id="2e1f2-140">To view summary information about your current licensing plans and the available licenses for each plan, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="2e1f2-141">PowerShell Core biedt geen ondersteuning voor de Microsoft Azure Active Directory-module voor Windows PowerShell-module en cmdlets met **Msol** in hun naam.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-141">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="2e1f2-142">Als u deze cmdlets wilt blijven gebruiken, moet u deze uitvoeren vanuit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-142">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="2e1f2-143">De resultaten bevatten de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="2e1f2-143">The results contain the following information:</span></span>
  
- <span data-ttu-id="2e1f2-144">**AccountSkuId:** Laat de beschikbare licentieplannen voor uw organisatie zien met de syntaxis `<CompanyName>:<LicensingPlan>` .</span><span class="sxs-lookup"><span data-stu-id="2e1f2-144">**AccountSkuId:** Show the available licensing plans for your organization by using the syntax `<CompanyName>:<LicensingPlan>`.</span></span>  <span data-ttu-id="2e1f2-145">_\<CompanyName>_ is de waarde die u hebt opgegeven toen u zich hebt geregistreerd bij Microsoft 365 en uniek is voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-145">_\<CompanyName>_ is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="2e1f2-146">De _\<LicensingPlan>_ waarde is voor iedereen hetzelfde.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-146">The _\<LicensingPlan>_ value is the same for everyone.</span></span> <span data-ttu-id="2e1f2-147">In de waarde is bijvoorbeeld de bedrijfsnaam en de naam van het licentieplan de systeemnaam voor `litwareinc:ENTERPRISEPACK`  `litwareinc` Office  `ENTERPRISEPACK` 365 Enterprise E3.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-147">For example, in the value `litwareinc:ENTERPRISEPACK`, the company name is  `litwareinc`, and the licensing plan name  `ENTERPRISEPACK`, which is the system name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="2e1f2-148">**ActiveUnits:** Het aantal licenties dat u hebt gekocht voor een specifiek licentieplan.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-148">**ActiveUnits:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="2e1f2-149">**WarningUnits:** Het aantal licenties in een licentieplan dat u niet hebt verlengd en dat na de respijtperiode van 30 dagen verloopt.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-149">**WarningUnits:** Number of licenses in a licensing plan that you haven't renewed, and that will expire after the 30-day grace period.</span></span>
    
- <span data-ttu-id="2e1f2-150">**ConsumedUnits:** Het aantal licenties dat u aan gebruikers hebt toegewezen vanuit een specifiek licentieplan.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-150">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="2e1f2-151">Voer de volgende opdracht uit om details weer te geven over de Microsoft 365-services die beschikbaar zijn in al uw licentieplannen:</span><span class="sxs-lookup"><span data-stu-id="2e1f2-151">To view details about the Microsoft 365 services that are available in all of your license plans, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="2e1f2-152">In de volgende tabel ziet u de Microsoft 365-serviceplannen en hun vriendelijke namen voor de meest voorkomende services.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-152">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="2e1f2-153">Uw lijst met serviceplannen kan anders zijn.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-153">Your list of service plans might be different.</span></span> 
  
|<span data-ttu-id="2e1f2-154">**Serviceplan**</span><span class="sxs-lookup"><span data-stu-id="2e1f2-154">**Service plan**</span></span>|<span data-ttu-id="2e1f2-155">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="2e1f2-155">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="2e1f2-156">Sway</span><span class="sxs-lookup"><span data-stu-id="2e1f2-156">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="2e1f2-157">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2e1f2-157">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="2e1f2-158">Yammer</span><span class="sxs-lookup"><span data-stu-id="2e1f2-158">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="2e1f2-159">Azure Rights Management (RMS)</span><span class="sxs-lookup"><span data-stu-id="2e1f2-159">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="2e1f2-160">Microsoft 365 Apps voor ondernemingen *(voorheen Office 365 ProPlus genoemd)*</span><span class="sxs-lookup"><span data-stu-id="2e1f2-160">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="2e1f2-161">Skype voor Bedrijven Online</span><span class="sxs-lookup"><span data-stu-id="2e1f2-161">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="2e1f2-162">Office</span><span class="sxs-lookup"><span data-stu-id="2e1f2-162">Office</span></span>  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="2e1f2-163">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2e1f2-163">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="2e1f2-164">Exchange Online Abonnement 2</span><span class="sxs-lookup"><span data-stu-id="2e1f2-164">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="2e1f2-165">Zie Productnamen en [serviceplanaanduidingen](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)voor licenties voor een volledige lijst met licentieplannen (ook wel productnamen genoemd), de bijbehorende serviceplannen en de bijbehorende vriendelijke namen.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-165">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="2e1f2-166">Als u details wilt bekijken over de Microsoft 365-services die beschikbaar zijn in een specifiek licentieplan, gebruikt u de volgende syntaxis.</span><span class="sxs-lookup"><span data-stu-id="2e1f2-166">To view details about the Microsoft 365 services that are available in a specific licensing plan, use the following syntax.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

<span data-ttu-id="2e1f2-167">In dit voorbeeld ziet u de services die beschikbaar zijn in het licentieplan litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3).</span><span class="sxs-lookup"><span data-stu-id="2e1f2-167">This example shows the services that are available in the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a><span data-ttu-id="2e1f2-168">Zie ook</span><span class="sxs-lookup"><span data-stu-id="2e1f2-168">See also</span></span>

[<span data-ttu-id="2e1f2-169">Microsoft 365-gebruikersaccounts, -licenties en -groepen beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e1f2-169">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="2e1f2-170">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e1f2-170">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="2e1f2-171">Aan de slag met PowerShell voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2e1f2-171">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)