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
ms.openlocfilehash: b101bf92c6a304262b3886a4ce0280f427a4a847
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538469"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a><span data-ttu-id="ca7a4-103">Problemen met eDiscovery-bewaring oplossen</span><span class="sxs-lookup"><span data-stu-id="ca7a4-103">Troubleshoot eDiscovery hold errors</span></span>

<span data-ttu-id="ca7a4-104">In dit artikel worden veelvoorkomende problemen beschreven die kunnen optreden met eDiscovery-in- en op te lossen.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-104">This article discusses common issues that may occur with eDiscovery holds and how to resolve them.</span></span> <span data-ttu-id="ca7a4-105">Het artikel bevat ook aanbevolen procedures om deze problemen te beperken of te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-105">The article also includes recommended practices to help you mitigate or avoid these issues.</span></span>

## <a name="recommended-practices"></a><span data-ttu-id="ca7a4-106">Aanbevolen procedures</span><span class="sxs-lookup"><span data-stu-id="ca7a4-106">Recommended practices</span></span>

<span data-ttu-id="ca7a4-107">Als u het aantal fouten met betrekking tot eDiscovery-bezit wilt beperken, raden we de volgende procedures aan:</span><span class="sxs-lookup"><span data-stu-id="ca7a4-107">To reduce the number of errors related to eDiscovery holds, we recommend the following practices:</span></span>

- <span data-ttu-id="ca7a4-108">Als een distributie van een wachtpositie nog in behandeling is, met een status van een van beide of , wacht u totdat de distributie van de wachtpositie is voltooid voordat u verdere `On (Pending)` updates aan het maken `Off (Pending)` bent.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-108">If a hold distribution is still pending, with a status of either `On (Pending)` or `Off (Pending)`, wait until the hold distribution is complete before you make any further updates.</span></span>

- <span data-ttu-id="ca7a4-109">Controleer of er een wachtbeleid in behandeling is voordat u verdere updates aan het beleid kunt geven.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-109">Check whether a hold policy is pending before you make any further updates to it.</span></span> <span data-ttu-id="ca7a4-110">Voer de volgende opdrachten uit of sla ze op in een PowerShell-script.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-110">Run the following commands or save them to a PowerShell script.</span></span>

    ```powershell
    $status = Get-CaseHoldPolicy -Identity <policyname> 
    if($status.DistributionStatus -ne "Pending"){
        # policy no longer pending
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user1
    }else{
        # policy still pending
        Write-Host "Hold policy still pending."
    }
   ```

- <span data-ttu-id="ca7a4-111">Voeg uw updates samen met een eDiscovery-hold in één bulkaanvraag in plaats van het holdbeleid herhaaldelijk bij te werken voor elke transactie.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-111">Merge your updates to an eDiscovery hold in a single bulk request rather than updating the hold policy repeatedly for each transaction.</span></span> <span data-ttu-id="ca7a4-112">Als u bijvoorbeeld meerdere gebruikerspostvakken wilt toevoegen aan een bestaand wachtbeleid met de cmdlet [Set-CaseHoldPolicy,](/powershell/module/exchange/set-caseholdpolicy) voert u de opdracht uit (of voegt u deze toe als codeblok aan een script), zodat deze slechts eenmaal wordt uitgevoerd om meerdere gebruikers toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-112">For example, to add multiple user mailboxes to an existing hold policy using the [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) cmdlet, run the command (or add as a code block to a script) so that it runs only once to add multiple users.</span></span>

  <span data-ttu-id="ca7a4-113">**Juist**</span><span class="sxs-lookup"><span data-stu-id="ca7a4-113">**Correct**</span></span>

    ```powershell
    Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   <span data-ttu-id="ca7a4-114">**Onjuist**</span><span class="sxs-lookup"><span data-stu-id="ca7a4-114">**Incorrect**</span></span>

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -Identity <policyname> -AddExchangeLocation $user
    }
    ```

   <span data-ttu-id="ca7a4-115">In het vorige onjuiste voorbeeld wordt de cmdlet vijf afzonderlijke keren uitgevoerd om de taak te voltooien.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-115">In the previous incorrect example, the cmdlet is run five separate times to complete the task.</span></span> <span data-ttu-id="ca7a4-116">Zie de sectie [Meer informatie](#more-information) voor meer informatie over de aanbevolen procedures voor het toevoegen van gebruikers aan een hold-beleid.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-116">For more information about the recommended practices for adding users to a hold policy, see the [More information](#more-information) section.</span></span>

- <span data-ttu-id="ca7a4-117">Voordat u contact op neemt met Microsoft Support over eDiscovery-wachtproblemen, voert u de stappen uit in de sectie [Fout/probleem: Wacht](#errorissue-holds-dont-sync) niet synchroniseren om de distributie in de wacht te zetten.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-117">Before contacting Microsoft Support about eDiscovery hold issues, follow the steps in the [Error/issue: Holds don't sync](#errorissue-holds-dont-sync) section to retry the hold distribution.</span></span> <span data-ttu-id="ca7a4-118">Dit proces lost vaak tijdelijke problemen op, waaronder interne serverfouten.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-118">This process often resolves temporary issues including, internal server errors.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="ca7a4-119">Fout/probleem: de synchronisatie van de in-en-uit-standen wordt niet gesynchroniseerd</span><span class="sxs-lookup"><span data-stu-id="ca7a4-119">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="ca7a4-120">Als u een van de volgende foutberichten ziet bij het in de wacht zetten van beheerders en gegevensbronnen, gebruikt u de oplossingsstappen om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-120">If you see one the following error messages when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="ca7a4-121">Resources: het implementeren van het beleid duurt langer dan verwacht.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-121">Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="ca7a4-122">Het kan nog twee uur duren voordat de uiteindelijke implementatiestatus is bijgewerkt, dus kijk over een paar uur terug.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-122">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

> <span data-ttu-id="ca7a4-123">Beleid kan niet worden geïmplementeerd in de inhoudsbron vanwege een tijdelijk probleem Office 365 datacenter.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-123">Policy cannot be deployed to the content source due to a temporary Office 365 datacenter issue.</span></span> <span data-ttu-id="ca7a4-124">Het huidige beleid wordt niet toegepast op inhoud in de bron, dus de geblokkeerde implementatie heeft geen invloed.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-124">The current policy is not applied to any content in the source, so there's no impact from the blocked deployment.</span></span> <span data-ttu-id="ca7a4-125">Als u dit probleem wilt oplossen, probeert u het beleid opnieuw te herschikken.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-125">To fix this issue, please try redeploying the policy.</span></span>

> <span data-ttu-id="ca7a4-126">Het is helaas niet mogelijk om de gevraagde wijzigingen in het beleid uit te voeren vanwege een tijdelijke interne serverfout.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-126">Sorry, we could not perform the requested changes to policy due to a transient internal server error.</span></span> <span data-ttu-id="ca7a4-127">Probeer het over 30 minuten opnieuw.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-127">Please try again in 30 minutes.</span></span>

### <a name="resolution"></a><span data-ttu-id="ca7a4-128">Oplossing</span><span class="sxs-lookup"><span data-stu-id="ca7a4-128">Resolution</span></span>

1. <span data-ttu-id="ca7a4-129">Verbinding maken naar [Security & Compliance Center PowerShell en](/powershell/exchange/connect-to-scc-powershell) voer de volgende opdracht uit voor een eDiscovery-hold:</span><span class="sxs-lookup"><span data-stu-id="ca7a4-129">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command for an eDiscovery hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. <span data-ttu-id="ca7a4-130">Bekijk de waarde in de *parameter DistributionDetail.*</span><span class="sxs-lookup"><span data-stu-id="ca7a4-130">Examine the value in the *DistributionDetail* parameter.</span></span> <span data-ttu-id="ca7a4-131">Zoek naar fouten zoals de volgende:</span><span class="sxs-lookup"><span data-stu-id="ca7a4-131">Look for errors like the following:</span></span>

   > <span data-ttu-id="ca7a4-132">Fout: Resources: het implementeren van het beleid duurt langer dan verwacht.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-132">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="ca7a4-133">Het kan nog twee uur duren voordat de uiteindelijke implementatiestatus is bijgewerkt, dus kijk over een paar uur terug.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-133">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

3. <span data-ttu-id="ca7a4-134">Probeer de opdracht **Set-CaseHoldPolicy -RetryDistribution** uit te voeren op het holdbeleid in kwestie; bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="ca7a4-134">Try running the **Set-CaseHoldPolicy -RetryDistribution** command on the hold policy in question; for example:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="error-the-sharepoint-site-is-read-only-or-not-accessible"></a><span data-ttu-id="ca7a4-135">Fout: de SharePoint site is alleen-lezen of niet toegankelijk</span><span class="sxs-lookup"><span data-stu-id="ca7a4-135">Error: The SharePoint site is read-only or not accessible</span></span>

<span data-ttu-id="ca7a4-136">Als u het volgende foutbericht ziet bij het in de wacht zetten van beheerders en gegevensbronnen, betekent dit dat de globale beheerder van uw organisatie of SharePoint [de](/sharepoint/sharepoint-admin-role) site heeft vergrendeld.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-136">If you see the following error message when putting custodians and data sources on hold, it means that your organization's [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) has locked the site.</span></span> <span data-ttu-id="ca7a4-137">Een vergrendelde site blokkeert dat eDiscovery een wacht op de site plaatst.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-137">A locked site blocks eDiscovery from placing a hold on the site.</span></span>

> <span data-ttu-id="ca7a4-138">De SharePoint site is alleen-lezen of niet toegankelijk.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-138">The SharePoint site is read-only or not accessible.</span></span> <span data-ttu-id="ca7a4-139">Neem contact op met de sitebeheerder om de site te kunnen maken en pas dit beleid opnieuw toe.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-139">Please contact the site administrator to make the site writable, and then redeploy this policy.</span></span>

### <a name="resolution"></a><span data-ttu-id="ca7a4-140">Oplossing</span><span class="sxs-lookup"><span data-stu-id="ca7a4-140">Resolution</span></span>

<span data-ttu-id="ca7a4-141">Ontgrendel de site (of vraag een beheerder om deze te ontgrendelen) om dit probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-141">Unlock the site (or ask an admin to unlock it) to resolve this issue.</span></span> <span data-ttu-id="ca7a4-142">Zie Sites vergrendelen en ontgrendelen voor meer informatie over het wijzigen van de vergrendelingstoestand voor [een site.](/sharepoint/manage-lock-status)</span><span class="sxs-lookup"><span data-stu-id="ca7a4-142">To learn more about how to change the lock state for a site, see [Lock and unlock sites](/sharepoint/manage-lock-status).</span></span>

## <a name="error-the-mailbox-or-sharepoint-site-may-not-exist"></a><span data-ttu-id="ca7a4-143">Fout: Het postvak of SharePoint site bestaat mogelijk niet</span><span class="sxs-lookup"><span data-stu-id="ca7a4-143">Error: The mailbox or SharePoint site may not exist</span></span>

<span data-ttu-id="ca7a4-144">Als u het volgende foutbericht ziet bij het in de wacht zetten van beheerders en gegevensbronnen, gebruikt u de oplossingsstappen om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-144">If you see the following error message when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="ca7a4-145">Het postvak of SharePoint site bestaat mogelijk niet.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-145">The mailbox or SharePoint site may not exist.</span></span>  <span data-ttu-id="ca7a4-146">Als dit onjuist is, neem dan contact op met microsoft-ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-146">If this is incorrect, please contact Microsoft support.</span></span>  <span data-ttu-id="ca7a4-147">Als u dit niet doet, verwijdert u het uit dit beleid.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-147">Otherwise, please remove it from this policy.</span></span>

### <a name="resolution"></a><span data-ttu-id="ca7a4-148">Oplossing</span><span class="sxs-lookup"><span data-stu-id="ca7a4-148">Resolution</span></span>

- <span data-ttu-id="ca7a4-149">Voer het [Get-Mailbox](/powershell/module/exchange/get-mailbox) in Exchange Online PowerShell uit om te controleren of het postvak van de gebruiker in uw organisatie bestaat.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-149">Run the [Get-Mailbox](/powershell/module/exchange/get-mailbox) in Exchange Online PowerShell to check if the user mailbox exists in your organization.</span></span>

- <span data-ttu-id="ca7a4-150">Voer de [cmdlet Get-SPOSite](/powershell/module/sharepoint-online/get-sposite) uit in SharePoint Online PowerShell om te controleren of de site in uw organisatie bestaat.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-150">Run the [Get-SPOSite](/powershell/module/sharepoint-online/get-sposite) cmdlet in SharePoint Online PowerShell to check if the site exists in your organization.</span></span>

- <span data-ttu-id="ca7a4-151">Controleer of de SITE-URL is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-151">Check to see if the site URL has changed.</span></span>

## <a name="more-information"></a><span data-ttu-id="ca7a4-152">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="ca7a4-152">More information</span></span>

<span data-ttu-id="ca7a4-153">De richtlijnen voor het bijwerken van wachtbeleid voor meerdere gebruikers in de sectie Aanbevolen procedures zijn het gevolg van het feit dat het systeem gelijktijdige updates van een hold-beleid blokkeert.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-153">The guidance about updating hold policies for multiple users in the "Recommended practices" section results from the fact that the system blocks simultaneous updates to a hold policy.</span></span> <span data-ttu-id="ca7a4-154">Dat betekent dat wanneer een bijgewerkt hold-beleid wordt toegepast op nieuwe inhoudslocaties en het holdbeleid in behandeling is, er geen extra inhoudslocaties kunnen worden toegevoegd aan het holdbeleid.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-154">That means when an updated hold policy is applied to new content locations and the hold policy is in a pending state, additional content locations can't be added to the hold policy.</span></span> <span data-ttu-id="ca7a4-155">Hier zijn enkele dingen die u in gedachten moet houden om u te helpen dit probleem te beperken:</span><span class="sxs-lookup"><span data-stu-id="ca7a4-155">Here are some things to keep in mind to help you mitigate this issue:</span></span>
  
- <span data-ttu-id="ca7a4-156">Elke keer dat een bijgewerkte wachttijd wordt bijgewerkt, wordt deze onmiddellijk in een status in behandeling.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-156">Every time a hold updated is updated, it immediately goes into a pending state.</span></span> <span data-ttu-id="ca7a4-157">De status in behandeling betekent dat de wachtpositie wordt toegepast op inhoudslocaties.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-157">The pending state status means the hold is being applied to content locations.</span></span>
  
- <span data-ttu-id="ca7a4-158">Als u een script hebt waarin een lus wordt uitgevoerd en locaties één voor één aan beleid worden toegevoegd (vergelijkbaar met het onjuiste voorbeeld dat wordt weergegeven in de sectie Aanbevolen procedures), wordt met de eerste inhoudslocatie (bijvoorbeeld een gebruikerspostvak) het synchronisatieproces gestart dat de status in behandeling activeert.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-158">If you have a script that runs a loop and adds locations to policy one by one (similar to the incorrect example shown in the "Recommended practices" section), the first content location (for example, a user mailbox) initiates the sync process that triggers the pending state.</span></span> <span data-ttu-id="ca7a4-159">Dat betekent dat de andere gebruikers die in volgende lusjes aan het beleid worden toegevoegd, een foutmelding geven.</span><span class="sxs-lookup"><span data-stu-id="ca7a4-159">That means the other users that are added to the policy in subsequent loops result in an error.</span></span>
  
- <span data-ttu-id="ca7a4-160">Als uw organisatie een script gebruikt waarin een lus wordt uitgevoerd om de inhoudslocaties voor een hold-beleid bij te werken, moet u het script zo bijwerken dat locaties in één bulkbewerking worden bijgewerkt (zoals wordt weergegeven in het juiste voorbeeld in de sectie Aanbevolen procedures).</span><span class="sxs-lookup"><span data-stu-id="ca7a4-160">If your organization is using a script that runs a loop to update the content locations for a hold policy, you must update the script so that it updates locations in a single bulk operation (as shown in the correct example in the "Recommended practices" section).</span></span>
