---
title: Problemen met eDiscovery-bewaring oplossen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Fouten met betrekking tot wettelijke bewaarnemingen oplossen die zijn toegepast op bewaarders en niet-bewaardergegevensbronnen in Core eDiscovery.
ms.openlocfilehash: 3bd417f2eb6bfb8de8d4b5ccaeb48e6ae1c888eb
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "52162598"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a><span data-ttu-id="49ea9-103">Problemen met eDiscovery-bewaring oplossen</span><span class="sxs-lookup"><span data-stu-id="49ea9-103">Troubleshoot eDiscovery hold errors</span></span>

<span data-ttu-id="49ea9-104">In dit artikel worden veelvoorkomende problemen beschreven die kunnen optreden met eDiscovery-in- en op te lossen.</span><span class="sxs-lookup"><span data-stu-id="49ea9-104">This article discusses common issues that may occur with eDiscovery holds and how to resolve them.</span></span> <span data-ttu-id="49ea9-105">Het artikel bevat ook aanbevolen procedures om deze problemen te beperken of te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="49ea9-105">The article also includes recommended practices to help you mitigate or avoid these issues.</span></span>

## <a name="recommended-practices"></a><span data-ttu-id="49ea9-106">Aanbevolen procedures</span><span class="sxs-lookup"><span data-stu-id="49ea9-106">Recommended practices</span></span>

<span data-ttu-id="49ea9-107">Als u het aantal fouten met betrekking tot eDiscovery-bezit wilt beperken, raden we de volgende procedures aan:</span><span class="sxs-lookup"><span data-stu-id="49ea9-107">To reduce the number of errors related to eDiscovery holds, we recommend the following practices:</span></span>

- <span data-ttu-id="49ea9-108">Als een distributie van een wachtpositie nog in behandeling is, met een status van een van beide of , wacht u totdat de distributie van de wachtpositie is voltooid voordat u verdere `On (Pending)` updates aan het maken `Off (Pending)` bent.</span><span class="sxs-lookup"><span data-stu-id="49ea9-108">If a hold distribution is still pending, with a status of either `On (Pending)` or `Off (Pending)`, wait until the hold distribution is complete before you make any further updates.</span></span>

- <span data-ttu-id="49ea9-109">Voeg uw updates samen met een eDiscovery-hold in één bulkaanvraag in plaats van het holdbeleid herhaaldelijk bij te werken voor elke transactie.</span><span class="sxs-lookup"><span data-stu-id="49ea9-109">Merge your updates to an eDiscovery hold in a single bulk request rather than updating the hold policy repeatedly for each transaction.</span></span> <span data-ttu-id="49ea9-110">Als u bijvoorbeeld meerdere gebruikerspostvakken wilt toevoegen aan een bestaand wachtbeleid met de cmdlet [Set-CaseHoldPolicy,](/powershell/module/exchange/set-caseholdpolicy) voert u de opdracht uit (of voegt u deze toe als codeblok aan een script), zodat deze slechts eenmaal wordt uitgevoerd om meerdere gebruikers toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="49ea9-110">For example, to add multiple user mailboxes to an existing hold policy using the [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) cmdlet, run the command (or add as a code block to a script) so that it runs only once to add multiple users.</span></span>

  <span data-ttu-id="49ea9-111">**Correct**</span><span class="sxs-lookup"><span data-stu-id="49ea9-111">**Correct**</span></span>

    ```powershell
    Set-CaseHoldPolicy -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   <span data-ttu-id="49ea9-112">**Onjuist**</span><span class="sxs-lookup"><span data-stu-id="49ea9-112">**Incorrect**</span></span>

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -AddExchangeLocation $user
    }
    ```

   <span data-ttu-id="49ea9-113">In het vorige onjuiste voorbeeld wordt de cmdlet vijf afzonderlijke keren uitgevoerd om de taak te voltooien.</span><span class="sxs-lookup"><span data-stu-id="49ea9-113">In the previous incorrect example, the cmdlet is run five separate times to complete the task.</span></span> <span data-ttu-id="49ea9-114">Zie de sectie [Meer informatie](#more-information) voor meer informatie over de aanbevolen procedures voor het toevoegen van gebruikers aan een hold-beleid.</span><span class="sxs-lookup"><span data-stu-id="49ea9-114">For more information about the recommended practices for adding users to a hold policy, see the [More information](#more-information) section.</span></span>

- <span data-ttu-id="49ea9-115">Voordat u contact op neemt met Microsoft Support over eDiscovery-wachtproblemen, voert u de stappen uit in de sectie [Fout/probleem: Wacht](#errorissue-holds-dont-sync) niet synchroniseren om de distributie in de wacht te zetten.</span><span class="sxs-lookup"><span data-stu-id="49ea9-115">Before contacting Microsoft Support about eDiscovery hold issues, follow the steps in the [Error/issue: Holds don't sync](#errorissue-holds-dont-sync) section to retry the hold distribution.</span></span> <span data-ttu-id="49ea9-116">Dit proces lost vaak tijdelijke problemen op, waaronder interne serverfouten.</span><span class="sxs-lookup"><span data-stu-id="49ea9-116">This process often resolves temporary issues including, internal server errors.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="49ea9-117">Fout/probleem: de synchronisatie van de in-en-uit-standen wordt niet gesynchroniseerd</span><span class="sxs-lookup"><span data-stu-id="49ea9-117">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="49ea9-118">Als u een van de volgende foutberichten ziet bij het in de wacht zetten van beheerders en gegevensbronnen, gebruikt u de oplossingsstappen om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="49ea9-118">If you see one the following error messages when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="49ea9-119">Resources: het implementeren van het beleid duurt langer dan verwacht.</span><span class="sxs-lookup"><span data-stu-id="49ea9-119">Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="49ea9-120">Het kan nog twee uur duren voordat de uiteindelijke implementatiestatus is bijgewerkt, dus kijk over een paar uur terug.</span><span class="sxs-lookup"><span data-stu-id="49ea9-120">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

> <span data-ttu-id="49ea9-121">Beleid kan niet worden geïmplementeerd in de inhoudsbron vanwege een tijdelijk probleem Office 365 datacenter.</span><span class="sxs-lookup"><span data-stu-id="49ea9-121">Policy cannot be deployed to the content source due to a temporary Office 365 datacenter issue.</span></span> <span data-ttu-id="49ea9-122">Het huidige beleid wordt niet toegepast op inhoud in de bron, dus de geblokkeerde implementatie heeft geen invloed.</span><span class="sxs-lookup"><span data-stu-id="49ea9-122">The current policy is not applied to any content in the source, so there's no impact from the blocked deployment.</span></span> <span data-ttu-id="49ea9-123">Als u dit probleem wilt oplossen, probeert u het beleid opnieuw te herschikken.</span><span class="sxs-lookup"><span data-stu-id="49ea9-123">To fix this issue, please try redeploying the policy.</span></span>

> <span data-ttu-id="49ea9-124">Het is helaas niet mogelijk om de gevraagde wijzigingen in het beleid uit te voeren vanwege een tijdelijke interne serverfout.</span><span class="sxs-lookup"><span data-stu-id="49ea9-124">Sorry, we could not perform the requested changes to policy due to a transient internal server error.</span></span> <span data-ttu-id="49ea9-125">Probeer het over 30 minuten opnieuw.</span><span class="sxs-lookup"><span data-stu-id="49ea9-125">Please try again in 30 minutes.</span></span>

### <a name="resolution"></a><span data-ttu-id="49ea9-126">Oplossing</span><span class="sxs-lookup"><span data-stu-id="49ea9-126">Resolution</span></span>

1. <span data-ttu-id="49ea9-127">Verbinding maken naar [Security & Compliance Center PowerShell en](/powershell/exchange/connect-to-scc-powershell) voer de volgende opdracht uit voor een eDiscovery-hold:</span><span class="sxs-lookup"><span data-stu-id="49ea9-127">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command for an eDiscovery hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. <span data-ttu-id="49ea9-128">Bekijk de waarde in de *parameter DistributionDetail.*</span><span class="sxs-lookup"><span data-stu-id="49ea9-128">Examine the value in the *DistributionDetail* parameter.</span></span> <span data-ttu-id="49ea9-129">Zoek naar fouten zoals de volgende:</span><span class="sxs-lookup"><span data-stu-id="49ea9-129">Look for errors like the following:</span></span>

   > <span data-ttu-id="49ea9-130">Fout: Resources: het implementeren van het beleid duurt langer dan verwacht.</span><span class="sxs-lookup"><span data-stu-id="49ea9-130">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="49ea9-131">Het kan nog twee uur duren voordat de uiteindelijke implementatiestatus is bijgewerkt, dus kijk over een paar uur terug.</span><span class="sxs-lookup"><span data-stu-id="49ea9-131">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

3. <span data-ttu-id="49ea9-132">Probeer de opdracht **Set-CaseHoldPolicy -RetryDistribution** uit te voeren op het holdbeleid in kwestie; bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="49ea9-132">Try running the **Set-CaseHoldPolicy -RetryDistribution** command on the hold policy in question; for example:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="more-information"></a><span data-ttu-id="49ea9-133">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="49ea9-133">More information</span></span>

- <span data-ttu-id="49ea9-134">De richtlijnen voor het bijwerken van wachtbeleid voor meerdere gebruikers in de sectie Aanbevolen procedures zijn het gevolg van het feit dat het systeem gelijktijdige updates van een hold-beleid blokkeert.</span><span class="sxs-lookup"><span data-stu-id="49ea9-134">The guidance about updating hold policies for multiple users in the "Recommended practices" section results from the fact that the system blocks simultaneous updates to a hold policy.</span></span> <span data-ttu-id="49ea9-135">Dat betekent dat wanneer een bijgewerkt hold-beleid wordt toegepast op nieuwe inhoudslocaties en het holdbeleid in behandeling is, er geen extra inhoudslocaties kunnen worden toegevoegd aan het holdbeleid.</span><span class="sxs-lookup"><span data-stu-id="49ea9-135">That means when an updated hold policy is applied to new content locations and the hold policy is in a pending state, additional content locations can't be added to the hold policy.</span></span> <span data-ttu-id="49ea9-136">Hier zijn enkele dingen die u in gedachten moet houden om u te helpen dit probleem te beperken:</span><span class="sxs-lookup"><span data-stu-id="49ea9-136">Here are some things to keep in mind to help you mitigate this issue:</span></span>
  
  - <span data-ttu-id="49ea9-137">Elke keer dat een bijgewerkte wachttijd wordt bijgewerkt, wordt deze onmiddellijk in een status in behandeling.</span><span class="sxs-lookup"><span data-stu-id="49ea9-137">Every time a hold updated is updated, it immediately goes into a pending state.</span></span> <span data-ttu-id="49ea9-138">De status in behandeling betekent dat de wachtpositie wordt toegepast op inhoudslocaties.</span><span class="sxs-lookup"><span data-stu-id="49ea9-138">The pending state status means the hold is being applied to content locations.</span></span>
  
  - <span data-ttu-id="49ea9-139">Als u een script hebt waarin een lus wordt uitgevoerd en locaties één voor één aan beleid worden toegevoegd (vergelijkbaar met het onjuiste voorbeeld dat wordt weergegeven in de sectie Aanbevolen procedures), wordt met de eerste inhoudslocatie (bijvoorbeeld een gebruikerspostvak) het synchronisatieproces gestart dat de status in behandeling activeert.</span><span class="sxs-lookup"><span data-stu-id="49ea9-139">If you have a script that runs a loop and adds locations to policy one by one (similar to the incorrect example shown in the "Recommended practices" section), the first content location (for example, a user mailbox) initiates the sync process that triggers the pending state.</span></span> <span data-ttu-id="49ea9-140">Dat betekent dat de andere gebruikers die in volgende lusjes aan het beleid worden toegevoegd, een foutmelding geven.</span><span class="sxs-lookup"><span data-stu-id="49ea9-140">That means the other users that are added to the policy in subsequent loops result in an error.</span></span>
  
  - <span data-ttu-id="49ea9-141">Als uw organisatie een script gebruikt waarin een lus wordt uitgevoerd om de inhoudslocaties voor een hold-beleid bij te werken, moet u het script zo bijwerken dat locaties in één bulkbewerking worden bijgewerkt (zoals wordt weergegeven in het juiste voorbeeld in de sectie Aanbevolen procedures).</span><span class="sxs-lookup"><span data-stu-id="49ea9-141">If your organization is using a script that runs a loop to update the content locations for a hold policy, you must update the script so that it updates locations in a single bulk operation (as shown in the correct example in the "Recommended practices" section).</span></span>
