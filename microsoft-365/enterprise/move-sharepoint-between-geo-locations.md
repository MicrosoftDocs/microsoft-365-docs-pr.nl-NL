---
title: Een SharePoint-site verplaatsen naar een andere geografische locatie
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: Meer informatie over hoe u een SharePoint-site kunt verplaatsen naar een andere geografische locatie binnen uw omgeving met meerdere geografische gebieden en de verwachtingen van de wijzigingen aan uw gebruikers kunt communiceren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e96c422b1d2685c9fe3d4c8c45aa8437a6776621
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688931"
---
# <a name="move-a-sharepoint-site-to-a-different-geo-location"></a><span data-ttu-id="0585c-103">Een SharePoint-site verplaatsen naar een andere geografische locatie</span><span class="sxs-lookup"><span data-stu-id="0585c-103">Move a SharePoint site to a different geo location</span></span>

<span data-ttu-id="0585c-104">Met de geo-verplaatsing van de SharePoint-site kunt u SharePoint-sites verplaatsen naar andere geo-locaties binnen uw omgeving met meerdere geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="0585c-104">With SharePoint site geo move, you can move SharePoint sites to other geo locations within your multi-geo environment.</span></span>

<span data-ttu-id="0585c-105">U kunt de volgende typen sites verplaatsen tussen geo-locaties:</span><span class="sxs-lookup"><span data-stu-id="0585c-105">The following types of site can be moved between geo locations:</span></span>

- <span data-ttu-id="0585c-106">Met Microsoft 365 groep verbonden sites</span><span class="sxs-lookup"><span data-stu-id="0585c-106">Microsoft 365 Group-connected sites</span></span>
- <span data-ttu-id="0585c-107">Moderne sites zonder een Microsoft 365-groeps koppeling</span><span class="sxs-lookup"><span data-stu-id="0585c-107">Modern sites without a Microsoft 365 Group association</span></span>
- <span data-ttu-id="0585c-108">Klassieke SharePoint-sites</span><span class="sxs-lookup"><span data-stu-id="0585c-108">Classic SharePoint sites</span></span>
- <span data-ttu-id="0585c-109">Communicatiesites</span><span class="sxs-lookup"><span data-stu-id="0585c-109">Communication sites</span></span>

<span data-ttu-id="0585c-110">U moet een globale beheerder of SharePoint-beheerder zijn als u een site wilt verplaatsen tussen de geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="0585c-110">You must be a Global Administrator or SharePoint Administrator to move a site between geo locations.</span></span>

<span data-ttu-id="0585c-111">Er is een alleen-lezen venster voor de geografische site 4-6 van een SharePoint-site, afhankelijk van de inhoud van de site.</span><span class="sxs-lookup"><span data-stu-id="0585c-111">There is a read-only window during the SharePoint site geo move of approximately 4-6 hours, depending on site contents.</span></span>
 
## <a name="best-practices"></a><span data-ttu-id="0585c-112">Aanbevolen procedures</span><span class="sxs-lookup"><span data-stu-id="0585c-112">Best practices</span></span>

- <span data-ttu-id="0585c-113">Probeer een SharePoint-site op een testsite te zetten om de procedure te leren kennen.</span><span class="sxs-lookup"><span data-stu-id="0585c-113">Try a SharePoint site move on a test site to get familiar with the procedure.</span></span> 
- <span data-ttu-id="0585c-114">Controleer of de site kan worden verplaatst voordat u de verhuizing plant of uitvoert.</span><span class="sxs-lookup"><span data-stu-id="0585c-114">Validate whether the site can be moved prior to scheduling or performing the move.</span></span> 
- <span data-ttu-id="0585c-115">Wanneer mogelijke planning van cross-geografische sites gedurende buiten kantooruren verloopt, kunt u de gevolgen van de gebruikers verminderen.</span><span class="sxs-lookup"><span data-stu-id="0585c-115">When possible schedule cross-geo sites moves for outside business hours to reduce user impact.</span></span>
- <span data-ttu-id="0585c-116">Communiceer met beïnvloede gebruikers voordat ze overstappen op de sites.</span><span class="sxs-lookup"><span data-stu-id="0585c-116">Communicate with impacted users prior to the sites move.</span></span> 

## <a name="communicating-to-your-users"></a><span data-ttu-id="0585c-117">Communiceren met uw gebruikers</span><span class="sxs-lookup"><span data-stu-id="0585c-117">Communicating to your users</span></span>

<span data-ttu-id="0585c-118">Als u SharePoint-sites tussen geo-locaties verplaatst, is het belangrijk om te communiceren met de gebruikers van de sites (meestal iedereen met de mogelijkheid om de site te bewerken) wat u kunt verwachten.</span><span class="sxs-lookup"><span data-stu-id="0585c-118">When moving SharePoint sites between geo locations, it's important to communicate to the sites' users (generally anyone with the ability to edit the site) what to expect.</span></span> <span data-ttu-id="0585c-119">Dit kan de gebruikers verwarring en oproepen naar uw helpdesk verminderen.</span><span class="sxs-lookup"><span data-stu-id="0585c-119">This can help reduce user confusion and calls to your help desk.</span></span> <span data-ttu-id="0585c-120">E-mail de gebruikers van uw site vóór de verhuizing en laat de volgende informatie weten:</span><span class="sxs-lookup"><span data-stu-id="0585c-120">Email your sites' users before the move and let them know the following information:</span></span>

- <span data-ttu-id="0585c-121">Wanneer de verplaatsing naar verwachting begint en hoe lang deze duurt</span><span class="sxs-lookup"><span data-stu-id="0585c-121">When the move is expected to start and how long it is expected to take</span></span>
- <span data-ttu-id="0585c-122">De geografische locatie waarnaar de site wordt verplaatst, en de URL voor toegang tot de nieuwe locatie</span><span class="sxs-lookup"><span data-stu-id="0585c-122">What geo location their site is moving to, and the URL to access the new location</span></span>
- <span data-ttu-id="0585c-123">De persoon moet hun bestanden sluiten en geen wijzigingen aanbrengen tijdens de verhuizing.</span><span class="sxs-lookup"><span data-stu-id="0585c-123">They should close their files and not make edits during the move.</span></span>
- <span data-ttu-id="0585c-124">De bestandsmachtigingen en het delen worden niet door de verhuizing gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="0585c-124">File permissions and sharing will not change because of the move.</span></span>
- <span data-ttu-id="0585c-125">Wat kunt u verwachten van de gebruikerservaring in een omgeving met meerdere geografische omgevingen?</span><span class="sxs-lookup"><span data-stu-id="0585c-125">What to expect from the user experience in a multi-geo environment</span></span>

<span data-ttu-id="0585c-126">Zorg ervoor dat u de gebruikers van uw sites een e-mail verzendt wanneer deze is voltooid, zodat ze hun werk op hun site kunnen voortzetten.</span><span class="sxs-lookup"><span data-stu-id="0585c-126">Be sure to send your sites' users an email when the move has successfully completed informing them that they can resume working on their sites.</span></span>

## <a name="scheduling-sharepoint-site-moves"></a><span data-ttu-id="0585c-127">Verplaatsen van SharePoint-site plannen</span><span class="sxs-lookup"><span data-stu-id="0585c-127">Scheduling SharePoint site moves</span></span>

<span data-ttu-id="0585c-128">U kunt instellen dat de SharePoint-site vooraf wordt gepland (verderop in dit artikel wordt beschreven).</span><span class="sxs-lookup"><span data-stu-id="0585c-128">You can schedule SharePoint site moves in advance (described later in this article).</span></span> <span data-ttu-id="0585c-129">U kunt als volgt de agenda verplaatsen:</span><span class="sxs-lookup"><span data-stu-id="0585c-129">You can schedule moves as follows:</span></span>

- <span data-ttu-id="0585c-130">U kunt maximaal 4.000 verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="0585c-130">You can schedule up to 4,000 moves at a time.</span></span>
- <span data-ttu-id="0585c-131">Zoals de verhuizing begint, kunt u meer plannen, met een maximum van 4.000 in behandeling in de wachtrij en op een bepaald moment.</span><span class="sxs-lookup"><span data-stu-id="0585c-131">As the moves begin, you can schedule more, with a maximum of 4,000 pending moves in the queue and any given time.</span></span>
 
<span data-ttu-id="0585c-132">Als u een SharePoint-site wilt plannen voor een later tijdstip, moet u een van de volgende parameters toevoegen wanneer u de verhuizing begint:</span><span class="sxs-lookup"><span data-stu-id="0585c-132">To schedule a SharePoint site geo move for a later time, include one of the following parameters when you start the move:</span></span>
- <span data-ttu-id="0585c-133">`PreferredMoveBeginDate` -De verhuizing begint waarschijnlijk op deze opgegeven tijd.</span><span class="sxs-lookup"><span data-stu-id="0585c-133">`PreferredMoveBeginDate` – The move will likely begin at this specified time.</span></span>
- <span data-ttu-id="0585c-134">`PreferredMoveEndDate` – De verhuizing wordt waarschijnlijk op basis van de opgegeven tijd voltooid.</span><span class="sxs-lookup"><span data-stu-id="0585c-134">`PreferredMoveEndDate` – The move will likely be completed by this specified time, on a best effort basis.</span></span> 

<span data-ttu-id="0585c-135">Voor beide parameters moet de tijd worden opgegeven in Coordinated Universal Time (UTC).</span><span class="sxs-lookup"><span data-stu-id="0585c-135">Time must be specified in Coordinated Universal Time (UTC) for both parameters.</span></span>

## <a name="moving-the-site"></a><span data-ttu-id="0585c-136">De site verplaatsen</span><span class="sxs-lookup"><span data-stu-id="0585c-136">Moving the site</span></span>

<span data-ttu-id="0585c-137">Voor het verplaatsen van een SharePoint-site moet de locatie van de SharePoint-beheerder verbinding maken en de overstappen van de SharePoint-beheer-URL</span><span class="sxs-lookup"><span data-stu-id="0585c-137">SharePoint site geo move requires that you connect and perform the move from the SharePoint Admin URL in the geo location where the site is.</span></span>

<span data-ttu-id="0585c-138">Als de URL van de site bijvoorbeeld is https://contosohealthcare.sharepoint.com/sites/Turbines , maakt u verbinding met de SharePoint-beheer-URL op https://contosohealthcare-admin.sharepoint.com:</span><span class="sxs-lookup"><span data-stu-id="0585c-138">For example, if the site URL is https://contosohealthcare.sharepoint.com/sites/Turbines, connect to the SharePoint Admin URL at https://contosohealthcare-admin.sharepoint.com:</span></span>

`Connect-SPOService -url https://contosohealthcare-admin.sharepoint.com`

![](../media/move-onedrive-between-geo-locations-image1.png)
 
### <a name="validating-the-environment"></a><span data-ttu-id="0585c-139">De omgeving valideren</span><span class="sxs-lookup"><span data-stu-id="0585c-139">Validating the environment</span></span>

<span data-ttu-id="0585c-140">We raden u aan om te controleren of de site kan worden verplaatst voordat u de verhuizing van een site plant.</span><span class="sxs-lookup"><span data-stu-id="0585c-140">We recommend that before scheduling any site move, you perform a validation to ensure that the site can be moved.</span></span>

<span data-ttu-id="0585c-141">We bieden geen ondersteuning voor het verplaatsen van sites met:</span><span class="sxs-lookup"><span data-stu-id="0585c-141">We do not support moving sites with:</span></span>
-    <span data-ttu-id="0585c-142">Business Connectivity Services</span><span class="sxs-lookup"><span data-stu-id="0585c-142">Business Connectivity Services</span></span>
-    <span data-ttu-id="0585c-143">InfoPath-formulieren</span><span class="sxs-lookup"><span data-stu-id="0585c-143">InfoPath forms</span></span> 
- <span data-ttu-id="0585c-144">IRM-sjablonen (Information Rights Management)</span><span class="sxs-lookup"><span data-stu-id="0585c-144">Information Rights Management (IRM) templates applied</span></span>

<span data-ttu-id="0585c-145">Voer de opdracht uit om ervoor te zorgen dat alle geo-locaties compatibel zijn `Get-SPOGeoMoveCrossCompatibilityStatus` .</span><span class="sxs-lookup"><span data-stu-id="0585c-145">To ensure all geo locations are compatible, run `Get-SPOGeoMoveCrossCompatibilityStatus`.</span></span> <span data-ttu-id="0585c-146">Hiermee worden al uw geografische locaties weergegeven en wordt aangegeven of de omgeving compatibel is met de geografische locatie van de doellocatie.</span><span class="sxs-lookup"><span data-stu-id="0585c-146">This will display all your geo locations and whether the environment is compatible with the destination geo location.</span></span>

<span data-ttu-id="0585c-147">Als u op uw site een validatie wilt uitvoeren, moet u `Start-SPOSiteContentMove` de `-ValidationOnly` parameter gebruiken om te controleren of de site kan worden verplaatst.</span><span class="sxs-lookup"><span data-stu-id="0585c-147">To perform a validation-only check on your site, use `Start-SPOSiteContentMove` with the `-ValidationOnly` parameter to validate if the site is able to be moved.</span></span> <span data-ttu-id="0585c-148">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="0585c-148">For example:</span></span>

```PowerShell
Start-SPOSiteContentMove -SourceSiteUrl <SourceSiteUrl> -ValidationOnly -DestinationDataLocation <DestinationLocation>
```

<span data-ttu-id="0585c-149">Hierdoor wordt het *resultaat als* de site klaar is om te worden verplaatst of *mislukt* indien een van de geblokkeerde voorwaarden beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="0585c-149">This will return *Success* if the site is ready to be moved or *Fail* if any of blocked conditions are present.</span></span>

### <a name="start-a-sharepoint-site-geo-move-for-a-site-with-no-associated-microsoft-365-group"></a><span data-ttu-id="0585c-150">Een geografische site van een SharePoint-site starten voor een site zonder een gekoppelde Microsoft 365-groep</span><span class="sxs-lookup"><span data-stu-id="0585c-150">Start a SharePoint site geo move for a site with no associated Microsoft 365 Group</span></span>

<span data-ttu-id="0585c-151">De aanvankelijke URL voor de site wordt standaard gewijzigd in de URL van de geografische locatie van de bestemming.</span><span class="sxs-lookup"><span data-stu-id="0585c-151">By default, initial URL for the site will change to the URL of the destination geo location.</span></span> <span data-ttu-id="0585c-152">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="0585c-152">For example:</span></span>

<span data-ttu-id="0585c-153">https://Contoso.sharepoint.com/sites/projectx Aan https://ContosoEUR.sharepoint.com/sites/projectx</span><span class="sxs-lookup"><span data-stu-id="0585c-153">https://Contoso.sharepoint.com/sites/projectx to https://ContosoEUR.sharepoint.com/sites/projectx</span></span>

<span data-ttu-id="0585c-154">Voor sites zonder de groeps koppeling van Microsoft 365 kunt u ook de naam van de site wijzigen met behulp van de `-DestinationUrl` parameter.</span><span class="sxs-lookup"><span data-stu-id="0585c-154">For sites with no Microsoft 365 Group association, you can also rename the site by using the `-DestinationUrl` parameter.</span></span> <span data-ttu-id="0585c-155">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="0585c-155">For example:</span></span>

<span data-ttu-id="0585c-156">https://Contoso.sharepoint.com/sites/projectx Aan https://ContosoEUR.sharepoint.com/sites/projecty</span><span class="sxs-lookup"><span data-stu-id="0585c-156">https://Contoso.sharepoint.com/sites/projectx to https://ContosoEUR.sharepoint.com/sites/projecty</span></span>

<span data-ttu-id="0585c-157">Voer het volgende uit om de site te verplaatsen:</span><span class="sxs-lookup"><span data-stu-id="0585c-157">To start the site move, run:</span></span>

`Start-SPOSiteContentMove -SourceSiteUrl <siteURL> -DestinationDataLocation <DestinationDataLocation> -DestinationUrl <DestinationSiteURL>`

![Schermafbeelding van het PowerShell-venster met de cmdlet start-SPOSiteContentMove](../media/multi-geo-sharepoint-site-move-powershell.png)

### <a name="start-a-sharepoint-site-geo-move-for-a-microsoft-365-group-connected-site"></a><span data-ttu-id="0585c-159">Een geografische site van een SharePoint-site starten voor een site met een Microsoft 365-groep</span><span class="sxs-lookup"><span data-stu-id="0585c-159">Start a SharePoint site geo move for a Microsoft 365 Group-connected site</span></span>

<span data-ttu-id="0585c-160">Als u een site met een Office 365-groep wilt verplaatsen, moet de globale beheerder of SharePoint-beheerder eerst het kenmerk van de gewenste gegevenslocatie (PDL) voor de Office 365-groep wijzigen.</span><span class="sxs-lookup"><span data-stu-id="0585c-160">To move an Office 365 Group-connected site, the Global Administrator or SharePoint Administrator must first change the Preferred Data Location (PDL) attribute for the Office 365 Group.</span></span>

<span data-ttu-id="0585c-161">De PDL voor een Microsoft 365-groep instellen:</span><span class="sxs-lookup"><span data-stu-id="0585c-161">To set the PDL for a Microsoft 365 Group:</span></span>

```PowerShell
Set-SPOUnifiedGroup -PreferredDataLocation <PDL> -GroupAlias <GroupAlias>
Get-SPOUnifiedGroup -GroupAlias <GroupAlias>
```
<span data-ttu-id="0585c-162">Wanneer u de PDL-update hebt bijgewerkt, kunt u de verhuizing van de site starten:</span><span class="sxs-lookup"><span data-stu-id="0585c-162">Once you have updated the PDL, you can start the site move:</span></span> 

```PowerShell
Start-SPOUnifiedGroupMove -GroupAlias <GroupAlias> -DestinationDataLocation <DestinationDataLocation>
```

## <a name="cancel-a-sharepoint-site-geo-move"></a><span data-ttu-id="0585c-163">Een SharePoint-site verplaatsen naar geo</span><span class="sxs-lookup"><span data-stu-id="0585c-163">Cancel a SharePoint site geo move</span></span>

<span data-ttu-id="0585c-164">U kunt een geografische verplaatsing van een SharePoint-site stoppen, mits de overstap niet wordt uitgevoerd of voltooid met behulp van de `Stop-SPOSiteContentMove` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0585c-164">You can stop a SharePoint site geo move, provided the move is not in progress or completed by using the `Stop-SPOSiteContentMove` cmdlet.</span></span>

## <a name="determining-the-status-of-a-sharepoint-site-geo-move"></a><span data-ttu-id="0585c-165">De status van de geografische verhuizing van een SharePoint-site bepalen</span><span class="sxs-lookup"><span data-stu-id="0585c-165">Determining the status of a SharePoint site geo move</span></span>

<span data-ttu-id="0585c-166">Met behulp van de volgende cmdlets kunt u de status van een site bepalen in ons van de geo waarmee u bent verbonden.</span><span class="sxs-lookup"><span data-stu-id="0585c-166">You can determine the status of a site move in our out of the geo that you are connected to by using the following cmdlets:</span></span>

- <span data-ttu-id="0585c-167">[Get-SPOSiteContentMoveState](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spositecontentmovestate) (niet met een groep verbonden sites)</span><span class="sxs-lookup"><span data-stu-id="0585c-167">[Get-SPOSiteContentMoveState](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spositecontentmovestate) (non-Group-connected sites)</span></span>
- <span data-ttu-id="0585c-168">Get-SPOUnifiedGroupMoveState (met een groep verbonden sites)</span><span class="sxs-lookup"><span data-stu-id="0585c-168">Get-SPOUnifiedGroupMoveState (Group-connected sites)</span></span>

<span data-ttu-id="0585c-169">Met behulp `-SourceSiteUrl` van de parameter kunt u de site opgeven waarvoor u de status van verplaatsen wilt weergeven.</span><span class="sxs-lookup"><span data-stu-id="0585c-169">Use the `-SourceSiteUrl` parameter to specify the site for which you want to see move status.</span></span>

<span data-ttu-id="0585c-170">De verplaatsings status wordt beschreven in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="0585c-170">The move statuses are described in the following table.</span></span>

|<span data-ttu-id="0585c-171">Status</span><span class="sxs-lookup"><span data-stu-id="0585c-171">Status</span></span>|<span data-ttu-id="0585c-172">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="0585c-172">Description</span></span>|
|:-----|:----------|
|<span data-ttu-id="0585c-173">Klaar om te activeren</span><span class="sxs-lookup"><span data-stu-id="0585c-173">Ready to Trigger</span></span>|<span data-ttu-id="0585c-174">De verhuizing is niet gestart.</span><span class="sxs-lookup"><span data-stu-id="0585c-174">The move has not started.</span></span>|
|<span data-ttu-id="0585c-175">Geplande</span><span class="sxs-lookup"><span data-stu-id="0585c-175">Scheduled</span></span>|<span data-ttu-id="0585c-176">De verhuizing bevindt zich in de wachtrij maar is nog niet gestart.</span><span class="sxs-lookup"><span data-stu-id="0585c-176">The move is in queue but has not yet started.</span></span>|
|<span data-ttu-id="0585c-177">Invoortgang (n/4)</span><span class="sxs-lookup"><span data-stu-id="0585c-177">InProgress (n/4)</span></span>|<span data-ttu-id="0585c-178">De verplaatsing wordt uitgevoerd in een van de volgende staten: validering (1/4), back-up (2/4), herstellen (3/4), opruimen (4/4).</span><span class="sxs-lookup"><span data-stu-id="0585c-178">The move is in progress in one of the following states: Validation (1/4), Backup (2/4), Restore (3/4), Cleanup (4/4).</span></span>|
|<span data-ttu-id="0585c-179">Bevestiging</span><span class="sxs-lookup"><span data-stu-id="0585c-179">Success</span></span>|<span data-ttu-id="0585c-180">De verhuizing is voltooid.</span><span class="sxs-lookup"><span data-stu-id="0585c-180">The move has completed successfully.</span></span>|
|<span data-ttu-id="0585c-181">Mislukt</span><span class="sxs-lookup"><span data-stu-id="0585c-181">Failed</span></span>|<span data-ttu-id="0585c-182">Verplaatsen mislukt.</span><span class="sxs-lookup"><span data-stu-id="0585c-182">The move failed.</span></span>|

<span data-ttu-id="0585c-183">U kunt ook de `-Verbose` optie gebruiken om aanvullende informatie over de verhuizing te zien.</span><span class="sxs-lookup"><span data-stu-id="0585c-183">You can also apply the `-Verbose` option to see additional information about the move.</span></span>

## <a name="user-experience"></a><span data-ttu-id="0585c-184">Gebruikerservaring</span><span class="sxs-lookup"><span data-stu-id="0585c-184">User experience</span></span>

<span data-ttu-id="0585c-185">Sitegebruikers dienen de minimale overlast te zien wanneer hun site naar een andere geografische locatie wordt verplaatst.</span><span class="sxs-lookup"><span data-stu-id="0585c-185">Site users should notice minimal disruption when their site is moved to a different geo location.</span></span> <span data-ttu-id="0585c-186">Als u tijdens de verhuizing een kortere alleen-lezen status wilt hebben, blijven bestaande koppelingen en machtigingen op de verwachte manier werken als de verplaatsing is voltooid.</span><span class="sxs-lookup"><span data-stu-id="0585c-186">Aside from a brief read-only state during the move, existing links and permissions will continue to work as expected once the move is completed.</span></span>

### <a name="site"></a><span data-ttu-id="0585c-187">Site</span><span class="sxs-lookup"><span data-stu-id="0585c-187">Site</span></span>

<span data-ttu-id="0585c-188">Tijdens de uitvoering wordt de site ingesteld op alleen-lezen.</span><span class="sxs-lookup"><span data-stu-id="0585c-188">While the move is in progress the site is set to read-only.</span></span> <span data-ttu-id="0585c-189">Wanneer de overstap is voltooid, wordt de gebruiker doorgestuurd naar de nieuwe site op de nieuwe geo-locatie wanneer ze op bladwijzers of andere koppelingen naar de site klikken.</span><span class="sxs-lookup"><span data-stu-id="0585c-189">Once the move is completed, the user is directed to the new site in the new geo location when they click on bookmarks or other links to the site.</span></span>

### <a name="permissions"></a><span data-ttu-id="0585c-190">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="0585c-190">Permissions</span></span>

<span data-ttu-id="0585c-191">Gebruikers met machtigingen voor de site hebben nog steeds toegang tot de site tijdens de verhuizing en nadat deze is voltooid.</span><span class="sxs-lookup"><span data-stu-id="0585c-191">Users with permissions to site will continue to have access to the site during the move and after it's complete.</span></span>

### <a name="sync-client"></a><span data-ttu-id="0585c-192">Synchronisatieclient</span><span class="sxs-lookup"><span data-stu-id="0585c-192">Sync Client</span></span>

<span data-ttu-id="0585c-193">De synchronisatieclient detecteert automatisch de synchronisatie naar de nieuwe sitelocatie en verstuurt automatisch de synchronisatie naar de nieuwe sitelocatie zodra de site is verplaatst.</span><span class="sxs-lookup"><span data-stu-id="0585c-193">The sync client will automatically detect and seamlessly transfer syncing to the new site location once the site move is complete.</span></span> <span data-ttu-id="0585c-194">De gebruiker hoeft zich niet opnieuw aan te melden of een andere actie te ondernemen.</span><span class="sxs-lookup"><span data-stu-id="0585c-194">The user does not need to sign in again or take any other action.</span></span> <span data-ttu-id="0585c-195">(Versie 17.3.6943.0625 of hoger van de synchronisatieclient vereist.)</span><span class="sxs-lookup"><span data-stu-id="0585c-195">(Version 17.3.6943.0625 or later of the sync client required.)</span></span>

<span data-ttu-id="0585c-196">Als een gebruiker een bestand bijwerkt terwijl de overstap wordt uitgevoerd, wordt door de synchronisatieclient aangegeven dat het uploaden van bestanden in behandeling is terwijl de verhuizing plaatsvindt.</span><span class="sxs-lookup"><span data-stu-id="0585c-196">If a user updates a file while the move is in progress, the sync client will notify them that file uploads are pending while the move is underway.</span></span>

### <a name="sharing-links"></a><span data-ttu-id="0585c-197">Koppelingen voordelen</span><span class="sxs-lookup"><span data-stu-id="0585c-197">Sharing links</span></span>

<span data-ttu-id="0585c-198">Wanneer de geografische site van de SharePoint-site is verplaatst, worden de bestaande gedeelde koppelingen voor de bestanden die zijn verplaatst automatisch omgeleid naar de nieuwe geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="0585c-198">When the SharePoint site geo move completes, the existing shared links for the files that were moved will automatically redirect to the new geo location.</span></span>

### <a name="most-recently-used-files-in-office-mru"></a><span data-ttu-id="0585c-199">Meest recent gebruikte bestanden in Office (MRU)</span><span class="sxs-lookup"><span data-stu-id="0585c-199">Most Recently Used files in Office (MRU)</span></span>

<span data-ttu-id="0585c-200">De MRU-service wordt bijgewerkt met de URL van de site en de inhoud van de inhoud nadat de verplaatsing is voltooid.</span><span class="sxs-lookup"><span data-stu-id="0585c-200">The MRU service is updated with the site url and its content URLs once the move completes.</span></span> <span data-ttu-id="0585c-201">Dit geldt voor Word, Excel en PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="0585c-201">This applies to Word, Excel, and PowerPoint.</span></span>

### <a name="onenote-experience"></a><span data-ttu-id="0585c-202">OneNote-ervaring</span><span class="sxs-lookup"><span data-stu-id="0585c-202">OneNote experience</span></span>

<span data-ttu-id="0585c-203">Met de apps van OneNote Win32 client en UWP (Universal) wordt automatisch notitieblokken automatisch herkend en gesynchroniseerd met de nieuwe sitelocatie zodra de verhuizing van de site is voltooid.</span><span class="sxs-lookup"><span data-stu-id="0585c-203">OneNote win32 client and UWP (Universal) App will automatically detect and seamlessly sync notebooks to the new site location once site move is complete.</span></span> <span data-ttu-id="0585c-204">De gebruiker hoeft zich niet opnieuw aan te melden of een andere actie te ondernemen.</span><span class="sxs-lookup"><span data-stu-id="0585c-204">The user does not need to sign in again or take any other action.</span></span> <span data-ttu-id="0585c-205">De enige zichtbare indicator voor de gebruiker is het synchroniseren van notitieblokken mislukt wanneer de site wordt verplaatst.</span><span class="sxs-lookup"><span data-stu-id="0585c-205">The only visible indicator to the user is notebook sync would fail when site move is in progress.</span></span> <span data-ttu-id="0585c-206">Deze ervaring is beschikbaar in de volgende versies van OneNote-clients:</span><span class="sxs-lookup"><span data-stu-id="0585c-206">This experience is available on the following OneNote client versions:</span></span>

- <span data-ttu-id="0585c-207">OneNote Win32-versie 16.0.8326.2096 (en later)</span><span class="sxs-lookup"><span data-stu-id="0585c-207">OneNote win32 – Version 16.0.8326.2096 (and later)</span></span>
- <span data-ttu-id="0585c-208">OneNote UWP: versie 16.0.8431.1006 (en later)</span><span class="sxs-lookup"><span data-stu-id="0585c-208">OneNote UWP – Version 16.0.8431.1006 (and later)</span></span>
- <span data-ttu-id="0585c-209">App OneNote Mobile: versie 16.0.8431.1011 (en later)</span><span class="sxs-lookup"><span data-stu-id="0585c-209">OneNote Mobile App – Version 16.0.8431.1011 (and later)</span></span>

### <a name="teams-applicable-to-microsoft-365-group-connected-sites"></a><span data-ttu-id="0585c-210">Teams (van toepassing op Microsoft 365-groep verbonden sites)</span><span class="sxs-lookup"><span data-stu-id="0585c-210">Teams (applicable to Microsoft 365 Group connected sites)</span></span>

<span data-ttu-id="0585c-211">Wanneer de geografische site van de SharePoint-site is verplaatst, hebben gebruikers toegang tot hun Microsoft 365-groepssite bestanden in de teams-app.</span><span class="sxs-lookup"><span data-stu-id="0585c-211">When the SharePoint site geo move completes, users will have access to their Microsoft 365 Group site files on the Teams app.</span></span> <span data-ttu-id="0585c-212">Daarnaast werken bestanden die zijn gedeeld via teams-chat van de site voordat de geo-overstap is voltooid, verder.</span><span class="sxs-lookup"><span data-stu-id="0585c-212">Additionally, files shared via Teams chat from their site prior to geo move will continue to work after move is complete.</span></span>

### <a name="sharepoint-mobile-app-iosandroid"></a><span data-ttu-id="0585c-213">Mobiele SharePoint-app (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="0585c-213">SharePoint Mobile App (iOS/Android)</span></span>

<span data-ttu-id="0585c-214">De mobiele SharePoint-app is door Geo compatibel en kan de nieuwe geografische locatie van de site detecteren.</span><span class="sxs-lookup"><span data-stu-id="0585c-214">The SharePoint Mobile App is cross geo compatible and able to detect the site's new geo location.</span></span>

### <a name="sharepoint-workflows"></a><span data-ttu-id="0585c-215">SharePoint-werkstromen</span><span class="sxs-lookup"><span data-stu-id="0585c-215">SharePoint workflows</span></span>

<span data-ttu-id="0585c-216">SharePoint 2013-werkstromen moeten opnieuw worden gepubliceerd na de site verhuizing.</span><span class="sxs-lookup"><span data-stu-id="0585c-216">SharePoint 2013 workflows need to be republished after the site move.</span></span> <span data-ttu-id="0585c-217">SharePoint 2010-werkstromen moeten normaal blijven functioneren.</span><span class="sxs-lookup"><span data-stu-id="0585c-217">SharePoint 2010 workflows should continue to function normally.</span></span>

### <a name="apps"></a><span data-ttu-id="0585c-218">Cloud</span><span class="sxs-lookup"><span data-stu-id="0585c-218">Apps</span></span>

<span data-ttu-id="0585c-219">Als u een site verplaatst met apps, moet u de app opnieuw instantiëren op de nieuwe geo-locatie van de site als de app en zijn de verbindingen mogelijk niet beschikbaar op de geografische locatie van de doellocatie.</span><span class="sxs-lookup"><span data-stu-id="0585c-219">If you are moving a site with apps, you must re-instantiate the app in the site's new geo location as the app and its connections may not be available in the destination geo location.</span></span>

### <a name="flow"></a><span data-ttu-id="0585c-220">Besturing</span><span class="sxs-lookup"><span data-stu-id="0585c-220">Flow</span></span>

<span data-ttu-id="0585c-221">In de meeste gevallen blijven de kasstromen werken nadat u de geografische site van een SharePoint-site hebt verplaatst.</span><span class="sxs-lookup"><span data-stu-id="0585c-221">In most cases Flows will continue to work after a SharePoint site geo move.</span></span> <span data-ttu-id="0585c-222">We raden u aan ze te testen wanneer de overstap is voltooid.</span><span class="sxs-lookup"><span data-stu-id="0585c-222">We recommend that you test them once the move has completed.</span></span>

### <a name="powerapps"></a><span data-ttu-id="0585c-223">PowerApps</span><span class="sxs-lookup"><span data-stu-id="0585c-223">PowerApps</span></span>

<span data-ttu-id="0585c-224">PowerApps moet opnieuw worden gemaakt op de doellocatie.</span><span class="sxs-lookup"><span data-stu-id="0585c-224">PowerApps need to be recreated in the destination location.</span></span>

### <a name="data-movement-between-geo-locations"></a><span data-ttu-id="0585c-225">Gegevensverplaatsing tussen geo-locaties</span><span class="sxs-lookup"><span data-stu-id="0585c-225">Data movement between geo locations</span></span>

<span data-ttu-id="0585c-226">SharePoint gebruikt Azure Blob Storage voor de inhoud, terwijl de metagegevens van sites en de bijbehorende bestanden in SharePoint zijn opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="0585c-226">SharePoint uses Azure Blob storage for its content, while the metadata associated with sites and its files is stored within SharePoint.</span></span> <span data-ttu-id="0585c-227">Wanneer de site van de geografische locatie van de site naar de geografische locatie van de doellocatie wordt verplaatst, wordt de bijbehorende Blobopslag ook verplaatst met de service.</span><span class="sxs-lookup"><span data-stu-id="0585c-227">After the site is moved from its source geo location to its destination geo location, the service will also move its associated Blob Storage.</span></span> <span data-ttu-id="0585c-228">Blobopslag wordt met een gehele 40 dagen afgerond.</span><span class="sxs-lookup"><span data-stu-id="0585c-228">Blob Storage moves complete in approximately 40 days.</span></span> 
