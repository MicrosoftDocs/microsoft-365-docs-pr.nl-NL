---
title: De rapporten weergeven voor preventie van gegevensverlies
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/7/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Gebruik de DLP-rapporten in Office 365 om het aantal DLP-beleidswedstrijden, overschrijven of onwaar-positieven weer te geven en te zien of ze in de tijd omhoog of omlaag trenden.
ms.openlocfilehash: 742f0ef0334e714c7f31cbc2f97559993454f6b7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162266"
---
# <a name="view-the-reports-for-data-loss-prevention"></a><span data-ttu-id="78f97-103">De rapporten weergeven voor preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="78f97-103">View the reports for data loss prevention</span></span>

<span data-ttu-id="78f97-104">Nadat u uw DLP-beleid (Data Loss Prevention) heeft gemaakt, moet u controleren of het werkt zoals u het bedoeld heeft en of het u helpt om aan de regels te blijven voldoen.</span><span class="sxs-lookup"><span data-stu-id="78f97-104">After you create your data loss prevention (DLP) policies, you'll want to verify that they're working as you intended and helping you to stay compliant.</span></span> <span data-ttu-id="78f97-105">Met de DLP-rapporten in het Beveiligings compliancecentrum kunt u snel het &amp; volgende bekijken:</span><span class="sxs-lookup"><span data-stu-id="78f97-105">With the DLP reports in the Security &amp; Compliance Center, you can quickly view:</span></span>
  
- <span data-ttu-id="78f97-106">**DLP-beleid** In dit rapport ziet u het aantal DLP-beleids matches in de tijd.</span><span class="sxs-lookup"><span data-stu-id="78f97-106">**DLP policy matches** This report shows the count of DLP policy matches over time.</span></span> <span data-ttu-id="78f97-107">U kunt het rapport filteren op datum, locatie, beleid of actie.</span><span class="sxs-lookup"><span data-stu-id="78f97-107">You can filter the report by date, location, policy, or action.</span></span> <span data-ttu-id="78f97-108">U kunt dit rapport gebruiken om:</span><span class="sxs-lookup"><span data-stu-id="78f97-108">You can use this report to:</span></span> 
    
  - <span data-ttu-id="78f97-109">U kunt uw DLP-beleid afstemmen of verfijnen terwijl u ze in de testmodus uit runt.</span><span class="sxs-lookup"><span data-stu-id="78f97-109">Tune or refine your DLP policies as you run them in test mode.</span></span> <span data-ttu-id="78f97-110">U kunt de specifieke regel bekijken die overeenkomen met de inhoud.</span><span class="sxs-lookup"><span data-stu-id="78f97-110">You can view the specific rule that matched the content.</span></span>
    
  - <span data-ttu-id="78f97-111">Focus op specifieke tijdsperiodes en begrijp de redenen voor pieken en trends.</span><span class="sxs-lookup"><span data-stu-id="78f97-111">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
  - <span data-ttu-id="78f97-112">Ontdek bedrijfsprocessen die strijdig zijn met het DLP-beleid van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="78f97-112">Discover business processes that violate your organization's DLP policies.</span></span>
    
  - <span data-ttu-id="78f97-113">Inzicht in de zakelijke gevolgen van het DLP-beleid door te zien welke acties worden toegepast op inhoud.</span><span class="sxs-lookup"><span data-stu-id="78f97-113">Understand any business impact of the DLP policies by seeing what actions are being applied to content.</span></span>
    
  - <span data-ttu-id="78f97-114">Controleer de naleving van een specifiek DLP-beleid door alle overeenkomsten voor dat beleid weer te geven.</span><span class="sxs-lookup"><span data-stu-id="78f97-114">Verify compliance with a specific DLP policy by showing any matches for that policy.</span></span>
    
  - <span data-ttu-id="78f97-115">Bekijk een lijst met beste gebruikers en herhaal gebruikers die bijdragen aan incidenten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="78f97-115">View a list of top users and repeat users who are contributing to incidents in your organization.</span></span>
    
  - <span data-ttu-id="78f97-116">Bekijk een lijst met de belangrijkste typen gevoelige informatie in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="78f97-116">View a list of the top types of sensitive information in your organization.</span></span>
    
- <span data-ttu-id="78f97-117">**DLP-incidenten** In dit rapport ziet u ook beleidswedstrijden in de tijd, zoals het rapport beleid dat overeenkomt met het beleid.</span><span class="sxs-lookup"><span data-stu-id="78f97-117">**DLP incidents** This report also shows policy matches over time, like the policy matches report.</span></span> <span data-ttu-id="78f97-118">Het rapport beleid komt overeen met overeenkomsten op regelniveau. Als een e-mailbericht bijvoorbeeld overeenkomt met drie verschillende regels, worden er drie verschillende regelitems in het rapport beleid gevonden.</span><span class="sxs-lookup"><span data-stu-id="78f97-118">However, the policy matches report shows matches at a rule level; for example, if an email matched three different rules, the policy matches report shows three different line items.</span></span> <span data-ttu-id="78f97-119">Het rapport incidenten daarentegen bevat overeenkomsten op itemniveau. Als een e-mailbericht bijvoorbeeld aan drie verschillende regels heeft gematcht, wordt in het rapport incidenten één regelitem voor dat inhoudsartikel gebruikt.</span><span class="sxs-lookup"><span data-stu-id="78f97-119">By contrast, the incidents report shows matches at an item level; for example, if an email matched three different rules, the incidents report shows a single line item for that piece of content.</span></span> 
    
  <span data-ttu-id="78f97-120">Omdat de rapporttellingen anders worden samengevoegd, is het rapport beleidsafstemmingen beter voor het identificeren van overeenkomsten met specifieke regels en het afstemmen van DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="78f97-120">Because the report counts are aggregated differently, the policy matches report is better for identifying matches with specific rules and fine tuning DLP policies.</span></span> <span data-ttu-id="78f97-121">Het rapport incidenten is beter voor het identificeren van specifieke inhoudsstukken die problematisch zijn voor uw DLP-beleid.</span><span class="sxs-lookup"><span data-stu-id="78f97-121">The incidents report is better for identifying specific pieces of content that are problematic for your DLP policies.</span></span>
    
- <span data-ttu-id="78f97-122">**DLP false positives and overrides** Als gebruikers met uw DLP-beleid het kunnen overschrijven of een onwaar positief rapport kunnen rapporteren, wordt in dit rapport een aantal van dergelijke exemplaren in de tijd berekent.</span><span class="sxs-lookup"><span data-stu-id="78f97-122">**DLP false positives and overrides** If your DLP policy allows users to override it or report a false positive, this report shows a count of such instances over time.</span></span> <span data-ttu-id="78f97-123">U kunt het rapport filteren op datum, locatie of beleid.</span><span class="sxs-lookup"><span data-stu-id="78f97-123">You can filter the report by date, location, or policy.</span></span> <span data-ttu-id="78f97-124">U kunt dit rapport gebruiken om:</span><span class="sxs-lookup"><span data-stu-id="78f97-124">You can use this report to:</span></span> 
    
  - <span data-ttu-id="78f97-125">U kunt uw DLP-beleid afstemmen of verfijnen door te zien welk beleid een hoog aantal onwaar-positieven veroorzaakt.</span><span class="sxs-lookup"><span data-stu-id="78f97-125">Tune or refine your DLP policies by seeing which policies incur a high number of false positives.</span></span>
    
  - <span data-ttu-id="78f97-126">Bekijk de rechtvaardigingen die door gebruikers zijn ingediend wanneer ze een beleidstip oplossen door het beleid te overschrijven.</span><span class="sxs-lookup"><span data-stu-id="78f97-126">View the justifications submitted by users when they resolve a policy tip by overriding the policy.</span></span>
    
  - <span data-ttu-id="78f97-127">Ontdek waar DLP-beleid strijdig is met geldige bedrijfsprocessen door een groot aantal gebruikers te overschrijven.</span><span class="sxs-lookup"><span data-stu-id="78f97-127">Discover where DLP policies conflict with valid business processes by incurring a high number of user overrides.</span></span>
    
<span data-ttu-id="78f97-128">Alle DLP-rapporten kunnen gegevens uit de meest recente periode van vier maanden laten zien.</span><span class="sxs-lookup"><span data-stu-id="78f97-128">All DLP reports can show data from the most recent four-month time period.</span></span> <span data-ttu-id="78f97-129">Het kan 24 uur duren voordat de meest recente gegevens in de rapporten worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="78f97-129">The most recent data can take up to 24 hours to appear in the reports.</span></span>
  
<span data-ttu-id="78f97-130">U vindt deze rapporten in het dashboard Rapporten van het &amp; Beveiligings \>  \> **compliancecentrum.**</span><span class="sxs-lookup"><span data-stu-id="78f97-130">You can find these reports in the Security &amp; Compliance Center \> **Reports** \> **Dashboard**.</span></span>
  
![Rapport DLP-beleid overeenkomt](../media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a><span data-ttu-id="78f97-132">De rechtvaardiging weergeven die door een gebruiker is ingediend voor een overschrijven</span><span class="sxs-lookup"><span data-stu-id="78f97-132">View the justification submitted by a user for an override</span></span>

<span data-ttu-id="78f97-133">Als uw DLP-beleid gebruikers toestaat dit te overschrijven, kunt u het fout-positieve rapport gebruiken en het rapport overschrijven gebruiken om de tekst weer te geven die door gebruikers is verzonden in de beleidstip.</span><span class="sxs-lookup"><span data-stu-id="78f97-133">If your DLP policy allows users to override it, you can use the false positive and override report to view the text submitted by users in the policy tip.</span></span>
  
![Veld Uitvullen in details van het DLP-rapport onwaar positief en overschrijven](../media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a><span data-ttu-id="78f97-135">Actie ondernemen op basis van inzichten en aanbevelingen</span><span class="sxs-lookup"><span data-stu-id="78f97-135">Take action on insights and recommendations</span></span>

<span data-ttu-id="78f97-136">Rapporten kunnen inzichten en aanbevelingen weergeven waarin u op het rode waarschuwingspictogram kunt klikken om details over mogelijke problemen te zien en mogelijke herstelactie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="78f97-136">Reports can show insights and recommendations where you can click the red warning icon to see details about potential issues and take possible remedial action.</span></span>
  
![Op een inzichtenpictogram klikken om details en acties te zien die u moet uitvoeren](../media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a><span data-ttu-id="78f97-138">Machtigingen voor DLP-rapporten</span><span class="sxs-lookup"><span data-stu-id="78f97-138">Permissions for DLP reports</span></span>

<span data-ttu-id="78f97-139">Als u DLP-rapporten wilt weergeven in het & compliancecentrum, moet u het volgende krijgen:</span><span class="sxs-lookup"><span data-stu-id="78f97-139">To view DLP reports in the Security & Compliance Center, you have to be assigned the:</span></span>

- <span data-ttu-id="78f97-140">**Rol beveiligingslezer** in het Exchange beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="78f97-140">**Security Reader** role in the Exchange admin center.</span></span> <span data-ttu-id="78f97-141">Deze rol is standaard toegewezen aan de rollengroepen Organisatiebeheer en Beveiligingslezer in het Exchange beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="78f97-141">By default, this role is assigned to the Organization Management and Security Reader role groups in the Exchange admin center.</span></span>

- <span data-ttu-id="78f97-142">**De functie View-Only DLP Compliance Management** in & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="78f97-142">**View-Only DLP Compliance Management** role in the Security & Compliance Center.</span></span> <span data-ttu-id="78f97-143">Deze rol is standaard toegewezen aan de rollengroepen Compliancebeheerder, Organisatiebeheer, Beveiligingsbeheerder en Beveiligingslezer in het beveiligingscentrum & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="78f97-143">By default, this role is assigned to the Compliance Administrator, Organization Management, Security Administrator, and Security Reader role groups in the Security & Compliance Center.</span></span>

- <span data-ttu-id="78f97-144">**De rol Alleen-weergeven geadresseerden** in het Exchange beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="78f97-144">**View-Only Recipients** role in the Exchange admin center.</span></span> <span data-ttu-id="78f97-145">Deze rol is standaard toegewezen aan de rollengroepen Compliancebeheer, Organisatiebeheer en View-Only organisatiebeheer in het Exchange beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="78f97-145">By default, this role is assigned to the Compliance Management, Organization Management, and View-Only Organization Management role groups in the Exchange admin center.</span></span>

## <a name="find-the-cmdlets-for-the-dlp-reports"></a><span data-ttu-id="78f97-146">De cmdlets voor de DLP-rapporten zoeken</span><span class="sxs-lookup"><span data-stu-id="78f97-146">Find the cmdlets for the DLP reports</span></span>

<span data-ttu-id="78f97-147">Als u de meeste cmdlets wilt gebruiken voor het Beveiligings &amp; compliancecentrum, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="78f97-147">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. [<span data-ttu-id="78f97-148">Verbinding maken naar het Beveiligings &amp; compliancecentrum met behulp van externe PowerShell</span><span class="sxs-lookup"><span data-stu-id="78f97-148">Connect to the Security &amp; Compliance Center using remote PowerShell</span></span>](/powershell/exchange/connect-to-scc-powershell&amp;clcid=0x409)
    
2. <span data-ttu-id="78f97-149">Een van deze [ &amp; cmdlets van het Beveiligings compliancecentrum gebruiken](/powershell/exchange/exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="78f97-149">Use any of these [Security &amp; Compliance Center cmdlets](/powershell/exchange/exchange-online-powershell)</span></span>
    
<span data-ttu-id="78f97-150">In DLP-rapporten moeten echter gegevens uit verschillende Office 365 worden verzameld, inclusief Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="78f97-150">However, DLP reports need pull data from across Office 365, including Exchange Online.</span></span> <span data-ttu-id="78f97-151">Daarom zijn de cmdlets voor de DLP-rapporten beschikbaar in Exchange Online Powershell, niet in Security &amp; Compliance Center Powershell.</span><span class="sxs-lookup"><span data-stu-id="78f97-151">For this reason, the cmdlets for the DLP reports are available in Exchange Online Powershell—not in Security &amp; Compliance Center Powershell.</span></span> <span data-ttu-id="78f97-152">Als u de cmdlets voor de DLP-rapporten wilt gebruiken, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="78f97-152">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. [<span data-ttu-id="78f97-153">Maak verbinding met Exchange Online via externe PowerShell</span><span class="sxs-lookup"><span data-stu-id="78f97-153">Connect to Exchange Online using remote PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)
    
2. <span data-ttu-id="78f97-154">Gebruik een van deze cmdlets voor de DLP-rapporten:</span><span class="sxs-lookup"><span data-stu-id="78f97-154">Use any of these cmdlets for the DLP reports:</span></span>
    
      - [<span data-ttu-id="78f97-155">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="78f97-155">Get-DlpDetectionsReport</span></span>](/powershell/module/exchange/get-dlpdetectionsreport)
    
      - [<span data-ttu-id="78f97-156">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="78f97-156">Get-DlpDetailReport</span></span>](/powershell/module/exchange/get-dlpdetailreport)
