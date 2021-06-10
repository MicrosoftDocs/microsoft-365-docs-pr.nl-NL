---
title: Een site SharePoint naar een andere geografische locatie verplaatsen
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
description: Meer informatie over het verplaatsen van een SharePoint naar een andere geografische locatie in uw multi-geo-omgeving en de verwachtingen van de wijzigingen aan uw gebruikers communiceren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: eed323b2e2b8f68a4a603052657e17495bb17690
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910928"
---
# <a name="move-a-sharepoint-site-to-a-different-geo-location"></a><span data-ttu-id="686e4-103">Een site SharePoint naar een andere geografische locatie verplaatsen</span><span class="sxs-lookup"><span data-stu-id="686e4-103">Move a SharePoint site to a different geo location</span></span>

<span data-ttu-id="686e4-104">Met SharePoint site geoverplaatsing kunt u SharePoint sites verplaatsen naar andere geografische locaties in uw multi-geo-omgeving.</span><span class="sxs-lookup"><span data-stu-id="686e4-104">With SharePoint site geo move, you can move SharePoint sites to other geo locations within your multi-geo environment.</span></span>

<span data-ttu-id="686e4-105">De volgende typen site kunnen worden verplaatst tussen geografische locaties:</span><span class="sxs-lookup"><span data-stu-id="686e4-105">The following types of site can be moved between geo locations:</span></span>

- <span data-ttu-id="686e4-106">Microsoft 365 Sites met groepsconnectie</span><span class="sxs-lookup"><span data-stu-id="686e4-106">Microsoft 365 Group-connected sites</span></span>
- <span data-ttu-id="686e4-107">Moderne sites zonder een Microsoft 365 groep</span><span class="sxs-lookup"><span data-stu-id="686e4-107">Modern sites without a Microsoft 365 Group association</span></span>
- <span data-ttu-id="686e4-108">Klassieke SharePoint sites</span><span class="sxs-lookup"><span data-stu-id="686e4-108">Classic SharePoint sites</span></span>
- <span data-ttu-id="686e4-109">Communicatiesites</span><span class="sxs-lookup"><span data-stu-id="686e4-109">Communication sites</span></span>

<span data-ttu-id="686e4-110">U moet een globale beheerder of beheerder SharePoint om een site tussen geografische locaties te verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="686e4-110">You must be a Global Administrator or SharePoint Administrator to move a site between geo locations.</span></span>

<span data-ttu-id="686e4-111">Er is een venster alleen-lezen tijdens de SharePoint site geoverplaatsing van ongeveer 4-6 uur, afhankelijk van de site-inhoud.</span><span class="sxs-lookup"><span data-stu-id="686e4-111">There is a read-only window during the SharePoint site geo move of approximately 4-6 hours, depending on site contents.</span></span>

## <a name="best-practices"></a><span data-ttu-id="686e4-112">Aanbevolen procedures</span><span class="sxs-lookup"><span data-stu-id="686e4-112">Best practices</span></span>

- <span data-ttu-id="686e4-113">Probeer een SharePoint site verplaatsen op een testsite om vertrouwd te raken met de procedure.</span><span class="sxs-lookup"><span data-stu-id="686e4-113">Try a SharePoint site move on a test site to get familiar with the procedure.</span></span>
- <span data-ttu-id="686e4-114">Controleer of de site kan worden verplaatst vóór het plannen of uitvoeren van de verhuizing.</span><span class="sxs-lookup"><span data-stu-id="686e4-114">Validate whether the site can be moved prior to scheduling or performing the move.</span></span>
- <span data-ttu-id="686e4-115">Indien mogelijk worden cross-geosites verplaatst voor buiten de werkuren om de impact van de gebruiker te beperken.</span><span class="sxs-lookup"><span data-stu-id="686e4-115">When possible schedule cross-geo sites moves for outside business hours to reduce user impact.</span></span>
- <span data-ttu-id="686e4-116">Communiceer met beïnvloede gebruikers voordat de sites worden verplaatst.</span><span class="sxs-lookup"><span data-stu-id="686e4-116">Communicate with impacted users prior to the sites move.</span></span>

## <a name="communicating-to-your-users"></a><span data-ttu-id="686e4-117">Communiceren met uw gebruikers</span><span class="sxs-lookup"><span data-stu-id="686e4-117">Communicating to your users</span></span>

<span data-ttu-id="686e4-118">Wanneer u SharePoint sites verplaatst tussen geografische locaties, is het belangrijk om te communiceren met de gebruikers van de sites (meestal iedereen met de mogelijkheid om de site te bewerken) wat u kunt verwachten.</span><span class="sxs-lookup"><span data-stu-id="686e4-118">When moving SharePoint sites between geo locations, it's important to communicate to the sites' users (generally anyone with the ability to edit the site) what to expect.</span></span> <span data-ttu-id="686e4-119">Dit kan gebruikersverwarring en oproepen naar uw helpdesk helpen verminderen.</span><span class="sxs-lookup"><span data-stu-id="686e4-119">This can help reduce user confusion and calls to your help desk.</span></span> <span data-ttu-id="686e4-120">E-mail de gebruikers van uw sites vóór de verhuizing en laat ze de volgende informatie weten:</span><span class="sxs-lookup"><span data-stu-id="686e4-120">Email your sites' users before the move and let them know the following information:</span></span>

- <span data-ttu-id="686e4-121">Wanneer de overstap wordt verwacht en hoe lang deze naar verwachting zal duren</span><span class="sxs-lookup"><span data-stu-id="686e4-121">When the move is expected to start and how long it is expected to take</span></span>
- <span data-ttu-id="686e4-122">Naar welke geografische locatie de site wordt verplaatst en de URL voor toegang tot de nieuwe locatie</span><span class="sxs-lookup"><span data-stu-id="686e4-122">What geo location their site is moving to, and the URL to access the new location</span></span>
- <span data-ttu-id="686e4-123">Ze moeten hun bestanden sluiten en geen wijzigingen maken tijdens het verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="686e4-123">They should close their files and not make edits during the move.</span></span>
- <span data-ttu-id="686e4-124">Bestandsmachtigingen en delen worden niet gewijzigd vanwege de verhuizing.</span><span class="sxs-lookup"><span data-stu-id="686e4-124">File permissions and sharing will not change because of the move.</span></span>
- <span data-ttu-id="686e4-125">Wat u kunt verwachten van de gebruikerservaring in een multi-geo-omgeving</span><span class="sxs-lookup"><span data-stu-id="686e4-125">What to expect from the user experience in a multi-geo environment</span></span>

<span data-ttu-id="686e4-126">Zorg ervoor dat u de gebruikers van uw sites een e-mail stuurt wanneer de overstap is voltooid, zodat ze kunnen hervatten met werken op hun sites.</span><span class="sxs-lookup"><span data-stu-id="686e4-126">Be sure to send your sites' users an email when the move has successfully completed informing them that they can resume working on their sites.</span></span>

## <a name="scheduling-sharepoint-site-moves"></a><span data-ttu-id="686e4-127">Site-SharePoint plannen</span><span class="sxs-lookup"><span data-stu-id="686e4-127">Scheduling SharePoint site moves</span></span>

<span data-ttu-id="686e4-128">U kunt de SharePoint van tevoren plannen (verder in dit artikel beschreven).</span><span class="sxs-lookup"><span data-stu-id="686e4-128">You can schedule SharePoint site moves in advance (described later in this article).</span></span> <span data-ttu-id="686e4-129">U kunt bewegingen als volgt plannen:</span><span class="sxs-lookup"><span data-stu-id="686e4-129">You can schedule moves as follows:</span></span>

- <span data-ttu-id="686e4-130">U kunt maximaal 4.000 bewegingen tegelijk plannen.</span><span class="sxs-lookup"><span data-stu-id="686e4-130">You can schedule up to 4,000 moves at a time.</span></span>
- <span data-ttu-id="686e4-131">Wanneer de bewegingen beginnen, kunt u meer plannen, met een maximum van 4.000 in behandeling zijnde bewegingen in de wachtrij en een bepaalde tijd.</span><span class="sxs-lookup"><span data-stu-id="686e4-131">As the moves begin, you can schedule more, with a maximum of 4,000 pending moves in the queue and any given time.</span></span>

<span data-ttu-id="686e4-132">Als u een SharePoint site geo-move voor een later tijdstip wilt plannen, moet u een van de volgende parameters opnemen wanneer u de move start:</span><span class="sxs-lookup"><span data-stu-id="686e4-132">To schedule a SharePoint site geo move for a later time, include one of the following parameters when you start the move:</span></span>

- <span data-ttu-id="686e4-133">`PreferredMoveBeginDate` – De verhuizing begint waarschijnlijk op dit opgegeven tijdstip.</span><span class="sxs-lookup"><span data-stu-id="686e4-133">`PreferredMoveBeginDate` – The move will likely begin at this specified time.</span></span>
- <span data-ttu-id="686e4-134">`PreferredMoveEndDate` – De verhuizing wordt waarschijnlijk voltooid op deze opgegeven tijd, op basis van de beste inspanning.</span><span class="sxs-lookup"><span data-stu-id="686e4-134">`PreferredMoveEndDate` – The move will likely be completed by this specified time, on a best effort basis.</span></span>

<span data-ttu-id="686e4-135">Tijd moet worden opgegeven in UTC (Coordinated Universal Time) voor beide parameters.</span><span class="sxs-lookup"><span data-stu-id="686e4-135">Time must be specified in Coordinated Universal Time (UTC) for both parameters.</span></span>

## <a name="moving-the-site"></a><span data-ttu-id="686e4-136">De site verplaatsen</span><span class="sxs-lookup"><span data-stu-id="686e4-136">Moving the site</span></span>

<span data-ttu-id="686e4-137">SharePoint site geo-move vereist dat u verbinding maakt en de overstap maakt van de url van de beheerder SharePoint de geografische locatie waar de site zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="686e4-137">SharePoint site geo move requires that you connect and perform the move from the SharePoint Admin URL in the geo location where the site is.</span></span>

<span data-ttu-id="686e4-138">Als de url van de site bijvoorbeeld de URL van de site is, maakt u verbinding met <https://contosohealthcare.sharepoint.com/sites/Turbines> de url SharePoint beheerder op <https://contosohealthcare-admin.sharepoint.com> :</span><span class="sxs-lookup"><span data-stu-id="686e4-138">For example, if the site URL is <https://contosohealthcare.sharepoint.com/sites/Turbines>, connect to the SharePoint Admin URL at <https://contosohealthcare-admin.sharepoint.com>:</span></span>

```powershell
Connect-SPOService -Url https://contosohealthcare-admin.sharepoint.com
```

![SharePoint Venster Onlinebeheershell met de Connect-SPOService opdracht](../media/move-onedrive-between-geo-locations-image1.png)

### <a name="validating-the-environment"></a><span data-ttu-id="686e4-140">De omgeving valideren</span><span class="sxs-lookup"><span data-stu-id="686e4-140">Validating the environment</span></span>

<span data-ttu-id="686e4-141">Het is raadzaam om voordat u een site verplaatsen te plannen, een validatie uit te voeren om ervoor te zorgen dat de site kan worden verplaatst.</span><span class="sxs-lookup"><span data-stu-id="686e4-141">We recommend that before scheduling any site move, you perform a validation to ensure that the site can be moved.</span></span>

<span data-ttu-id="686e4-142">We bieden geen ondersteuning voor het verplaatsen van sites met:</span><span class="sxs-lookup"><span data-stu-id="686e4-142">We do not support moving sites with:</span></span>

- <span data-ttu-id="686e4-143">Business Connectivity Services</span><span class="sxs-lookup"><span data-stu-id="686e4-143">Business Connectivity Services</span></span>
- <span data-ttu-id="686e4-144">InfoPath-formulieren</span><span class="sxs-lookup"><span data-stu-id="686e4-144">InfoPath forms</span></span>
- <span data-ttu-id="686e4-145">IRM-sjablonen (Information Rights Management) toegepast</span><span class="sxs-lookup"><span data-stu-id="686e4-145">Information Rights Management (IRM) templates applied</span></span>

<span data-ttu-id="686e4-146">Als u ervoor wilt zorgen dat alle geografische locaties compatibel zijn, moet u `Get-SPOGeoMoveCrossCompatibilityStatus` uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="686e4-146">To ensure all geo locations are compatible, run `Get-SPOGeoMoveCrossCompatibilityStatus`.</span></span> <span data-ttu-id="686e4-147">Hiermee worden al uw geografische locaties weergegeven en wordt bepaald of de omgeving compatibel is met de doellocatie.</span><span class="sxs-lookup"><span data-stu-id="686e4-147">This will display all your geo locations and whether the environment is compatible with the destination geo location.</span></span>

<span data-ttu-id="686e4-148">Als u een validatiecontrole op uw site wilt uitvoeren, gebruikt u de parameter om te valideren of de `Start-SPOSiteContentMove` `-ValidationOnly` site kan worden verplaatst.</span><span class="sxs-lookup"><span data-stu-id="686e4-148">To perform a validation-only check on your site, use `Start-SPOSiteContentMove` with the `-ValidationOnly` parameter to validate if the site is able to be moved.</span></span> <span data-ttu-id="686e4-149">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="686e4-149">For example:</span></span>

```PowerShell
Start-SPOSiteContentMove -SourceSiteUrl <SourceSiteUrl> -ValidationOnly -DestinationDataLocation <DestinationLocation>
```

<span data-ttu-id="686e4-150">Dit geeft succes *als* de site klaar is om te worden verplaatst of *Mislukken* als er een van de geblokkeerde voorwaarden aanwezig is.</span><span class="sxs-lookup"><span data-stu-id="686e4-150">This will return *Success* if the site is ready to be moved or *Fail* if any of blocked conditions are present.</span></span>

### <a name="start-a-sharepoint-site-geo-move-for-a-site-with-no-associated-microsoft-365-group"></a><span data-ttu-id="686e4-151">Een geografische SharePoint site starten voor een site zonder gekoppelde Microsoft 365 Groep</span><span class="sxs-lookup"><span data-stu-id="686e4-151">Start a SharePoint site geo move for a site with no associated Microsoft 365 Group</span></span>

<span data-ttu-id="686e4-152">Standaard wordt de oorspronkelijke URL voor de site gewijzigd in de URL van de doellocatie.</span><span class="sxs-lookup"><span data-stu-id="686e4-152">By default, initial URL for the site will change to the URL of the destination geo location.</span></span> <span data-ttu-id="686e4-153">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="686e4-153">For example:</span></span>

<span data-ttu-id="686e4-154"><https://Contoso.sharepoint.com/sites/projectx> Aan <https://ContosoEUR.sharepoint.com/sites/projectx></span><span class="sxs-lookup"><span data-stu-id="686e4-154"><https://Contoso.sharepoint.com/sites/projectx> to <https://ContosoEUR.sharepoint.com/sites/projectx></span></span>

<span data-ttu-id="686e4-155">Voor sites zonder Microsoft 365 groep kunt u de naam van de site ook wijzigen met de `-DestinationUrl` parameter.</span><span class="sxs-lookup"><span data-stu-id="686e4-155">For sites with no Microsoft 365 Group association, you can also rename the site by using the `-DestinationUrl` parameter.</span></span> <span data-ttu-id="686e4-156">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="686e4-156">For example:</span></span>

<span data-ttu-id="686e4-157"><https://Contoso.sharepoint.com/sites/projectx> Aan <https://ContosoEUR.sharepoint.com/sites/projecty></span><span class="sxs-lookup"><span data-stu-id="686e4-157"><https://Contoso.sharepoint.com/sites/projectx> to <https://ContosoEUR.sharepoint.com/sites/projecty></span></span>

<span data-ttu-id="686e4-158">Als u de site wilt verplaatsen, gaat u als volgende te werk:</span><span class="sxs-lookup"><span data-stu-id="686e4-158">To start the site move, run:</span></span>

```powershell
Start-SPOSiteContentMove -SourceSiteUrl <siteURL> -DestinationDataLocation <DestinationDataLocation> -DestinationUrl <DestinationSiteURL>
```

![Schermafbeelding van PowerShell-venster met Start-SPOSiteContentMove cmdlet](../media/multi-geo-sharepoint-site-move-powershell.png)

### <a name="start-a-sharepoint-site-geo-move-for-a-microsoft-365-group-connected-site"></a><span data-ttu-id="686e4-160">Een geoverplaatsing SharePoint site starten voor een Microsoft 365 met groep verbonden site</span><span class="sxs-lookup"><span data-stu-id="686e4-160">Start a SharePoint site geo move for a Microsoft 365 Group-connected site</span></span>

<span data-ttu-id="686e4-161">Als u een Office 365 groep verbonden site wilt verplaatsen, moet de globale beheerder of SharePoint-beheerder eerst het kenmerk Voorkeursgegevenslocatie (PDL) voor de groep Office 365 wijzigen.</span><span class="sxs-lookup"><span data-stu-id="686e4-161">To move an Office 365 Group-connected site, the Global Administrator or SharePoint Administrator must first change the Preferred Data Location (PDL) attribute for the Office 365 Group.</span></span>

<span data-ttu-id="686e4-162">De PDL voor een groep Microsoft 365 instellen:</span><span class="sxs-lookup"><span data-stu-id="686e4-162">To set the PDL for a Microsoft 365 Group:</span></span>

```PowerShell
Set-SPOUnifiedGroup -PreferredDataLocation <PDL> -GroupAlias <GroupAlias>
Get-SPOUnifiedGroup -GroupAlias <GroupAlias>
```

<span data-ttu-id="686e4-163">Nadat u het PDF-bericht hebt bijgewerkt, kunt u de site verplaatsen:</span><span class="sxs-lookup"><span data-stu-id="686e4-163">Once you have updated the PDL, you can start the site move:</span></span>

```PowerShell
Start-SPOUnifiedGroupMove -GroupAlias <GroupAlias> -DestinationDataLocation <DestinationDataLocation>
```

## <a name="cancel-a-sharepoint-site-geo-move"></a><span data-ttu-id="686e4-164">Een geo-SharePoint site annuleren</span><span class="sxs-lookup"><span data-stu-id="686e4-164">Cancel a SharePoint site geo move</span></span>

<span data-ttu-id="686e4-165">U kunt een SharePoint site geoverplaatsing stoppen, mits de beweging niet wordt uitgevoerd of voltooid met behulp van de `Stop-SPOSiteContentMove` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="686e4-165">You can stop a SharePoint site geo move, provided the move is not in progress or completed by using the `Stop-SPOSiteContentMove` cmdlet.</span></span>

## <a name="determining-the-status-of-a-sharepoint-site-geo-move"></a><span data-ttu-id="686e4-166">De status van een geo-SharePoint van een site bepalen</span><span class="sxs-lookup"><span data-stu-id="686e4-166">Determining the status of a SharePoint site geo move</span></span>

<span data-ttu-id="686e4-167">Met de volgende cmdlets kunt u de status van een site verplaatsen in de geo waar u mee verbonden bent bepalen:</span><span class="sxs-lookup"><span data-stu-id="686e4-167">You can determine the status of a site move in our out of the geo that you are connected to by using the following cmdlets:</span></span>

- <span data-ttu-id="686e4-168">[Get-SPOSiteContentMoveState](/powershell/module/sharepoint-online/get-spositecontentmovestate) (sites die niet met groepen zijn verbonden)</span><span class="sxs-lookup"><span data-stu-id="686e4-168">[Get-SPOSiteContentMoveState](/powershell/module/sharepoint-online/get-spositecontentmovestate) (non-Group-connected sites)</span></span>
- <span data-ttu-id="686e4-169">[Get-SPOUnifiedGroupMoveState](/powershell/module/sharepoint-online/get-spounifiedgroupmovestate) (sites met groepsconnectie)</span><span class="sxs-lookup"><span data-stu-id="686e4-169">[Get-SPOUnifiedGroupMoveState](/powershell/module/sharepoint-online/get-spounifiedgroupmovestate) (Group-connected sites)</span></span>

<span data-ttu-id="686e4-170">Gebruik de `-SourceSiteUrl` parameter om de site op te geven waarvoor u de status verplaatsen wilt zien.</span><span class="sxs-lookup"><span data-stu-id="686e4-170">Use the `-SourceSiteUrl` parameter to specify the site for which you want to see move status.</span></span>

<span data-ttu-id="686e4-171">De statussen voor verplaatsen worden in de volgende tabel beschreven.</span><span class="sxs-lookup"><span data-stu-id="686e4-171">The move statuses are described in the following table.</span></span>

****

|<span data-ttu-id="686e4-172">Status</span><span class="sxs-lookup"><span data-stu-id="686e4-172">Status</span></span>|<span data-ttu-id="686e4-173">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="686e4-173">Description</span></span>|
|---|---|
|<span data-ttu-id="686e4-174">Klaar om te activeren</span><span class="sxs-lookup"><span data-stu-id="686e4-174">Ready to Trigger</span></span>|<span data-ttu-id="686e4-175">De move is nog niet gestart.</span><span class="sxs-lookup"><span data-stu-id="686e4-175">The move has not started.</span></span>|
|<span data-ttu-id="686e4-176">Gepland</span><span class="sxs-lookup"><span data-stu-id="686e4-176">Scheduled</span></span>|<span data-ttu-id="686e4-177">De move staat in de wachtrij, maar is nog niet gestart.</span><span class="sxs-lookup"><span data-stu-id="686e4-177">The move is in queue but has not yet started.</span></span>|
|<span data-ttu-id="686e4-178">InProgress (n/4)</span><span class="sxs-lookup"><span data-stu-id="686e4-178">InProgress (n/4)</span></span>|<span data-ttu-id="686e4-179">De move wordt uitgevoerd in een van de volgende staten: Validatie (1/4), Back-up (2/4), Herstellen (3/4), Opschoning (4-4).</span><span class="sxs-lookup"><span data-stu-id="686e4-179">The move is in progress in one of the following states: Validation (1/4), Backup (2/4), Restore (3/4), Cleanup (4/4).</span></span>|
|<span data-ttu-id="686e4-180">Succes</span><span class="sxs-lookup"><span data-stu-id="686e4-180">Success</span></span>|<span data-ttu-id="686e4-181">De verhuizing is voltooid.</span><span class="sxs-lookup"><span data-stu-id="686e4-181">The move has completed successfully.</span></span>|
|<span data-ttu-id="686e4-182">Mislukt</span><span class="sxs-lookup"><span data-stu-id="686e4-182">Failed</span></span>|<span data-ttu-id="686e4-183">De beweging is mislukt.</span><span class="sxs-lookup"><span data-stu-id="686e4-183">The move failed.</span></span>|
|

<span data-ttu-id="686e4-184">U kunt de optie ook `-Verbose` toepassen om aanvullende informatie over de verhuizing te bekijken.</span><span class="sxs-lookup"><span data-stu-id="686e4-184">You can also apply the `-Verbose` option to see additional information about the move.</span></span>

## <a name="user-experience"></a><span data-ttu-id="686e4-185">Gebruikerservaring</span><span class="sxs-lookup"><span data-stu-id="686e4-185">User experience</span></span>

<span data-ttu-id="686e4-186">Sitegebruikers moeten minimale onderbrekingen zien wanneer hun site naar een andere geografische locatie wordt verplaatst.</span><span class="sxs-lookup"><span data-stu-id="686e4-186">Site users should notice minimal disruption when their site is moved to a different geo location.</span></span> <span data-ttu-id="686e4-187">Afgezien van een korte status alleen-lezen tijdens het verplaatsen, blijven bestaande koppelingen en machtigingen werken zoals verwacht wanneer de verhuizing is voltooid.</span><span class="sxs-lookup"><span data-stu-id="686e4-187">Aside from a brief read-only state during the move, existing links and permissions will continue to work as expected once the move is completed.</span></span>

### <a name="site"></a><span data-ttu-id="686e4-188">Site</span><span class="sxs-lookup"><span data-stu-id="686e4-188">Site</span></span>

<span data-ttu-id="686e4-189">Terwijl de move wordt uitgevoerd, is de site ingesteld op alleen-lezen.</span><span class="sxs-lookup"><span data-stu-id="686e4-189">While the move is in progress the site is set to read-only.</span></span> <span data-ttu-id="686e4-190">Wanneer de overstap is voltooid, wordt de gebruiker doorgestuurd naar de nieuwe site op de nieuwe geografische locatie wanneer deze op bladwijzers of andere koppelingen naar de site klikt.</span><span class="sxs-lookup"><span data-stu-id="686e4-190">Once the move is completed, the user is directed to the new site in the new geo location when they click on bookmarks or other links to the site.</span></span>

### <a name="permissions"></a><span data-ttu-id="686e4-191">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="686e4-191">Permissions</span></span>

<span data-ttu-id="686e4-192">Gebruikers met een sitemachtiging blijven toegang tot de site hebben tijdens de verhuizing en nadat de site is voltooid.</span><span class="sxs-lookup"><span data-stu-id="686e4-192">Users with permissions to site will continue to have access to the site during the move and after it's complete.</span></span>

### <a name="sync-client"></a><span data-ttu-id="686e4-193">Synchronisatieclient</span><span class="sxs-lookup"><span data-stu-id="686e4-193">Sync Client</span></span>

<span data-ttu-id="686e4-194">De synchronisatieclient detecteert automatisch en schakelt naadloos synchronisatie over naar de nieuwe sitelocatie zodra de siteverplaatsing is voltooid.</span><span class="sxs-lookup"><span data-stu-id="686e4-194">The sync client will automatically detect and seamlessly transfer syncing to the new site location once the site move is complete.</span></span> <span data-ttu-id="686e4-195">De gebruiker hoeft zich niet opnieuw aan te melden of een andere actie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="686e4-195">The user does not need to sign in again or take any other action.</span></span> <span data-ttu-id="686e4-196">(Versie 17.3.6943.0625 of hoger van de synchronisatieclient vereist.)</span><span class="sxs-lookup"><span data-stu-id="686e4-196">(Version 17.3.6943.0625 or later of the sync client required.)</span></span>

<span data-ttu-id="686e4-197">Als een gebruiker een bestand bij werkt terwijl de overstap wordt uitgevoerd, ontvangt de synchronisatieclient een melding dat er een bestand wordt geüpload terwijl de overstap wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="686e4-197">If a user updates a file while the move is in progress, the sync client will notify them that file uploads are pending while the move is underway.</span></span>

### <a name="sharing-links"></a><span data-ttu-id="686e4-198">Koppelingen voor delen</span><span class="sxs-lookup"><span data-stu-id="686e4-198">Sharing links</span></span>

<span data-ttu-id="686e4-199">Wanneer de SharePoint site geoverplaatsing is voltooid, worden de bestaande gedeelde koppelingen voor de bestanden die zijn verplaatst, automatisch omgeleid naar de nieuwe geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="686e4-199">When the SharePoint site geo move completes, the existing shared links for the files that were moved will automatically redirect to the new geo location.</span></span>

### <a name="most-recently-used-files-in-office-mru"></a><span data-ttu-id="686e4-200">Meest recent gebruikte bestanden in Office (MRU)</span><span class="sxs-lookup"><span data-stu-id="686e4-200">Most Recently Used files in Office (MRU)</span></span>

<span data-ttu-id="686e4-201">De MRU-service wordt bijgewerkt met de url van de site en de inhouds-URL's van de site zodra de overstap is voltooid.</span><span class="sxs-lookup"><span data-stu-id="686e4-201">The MRU service is updated with the site url and its content URLs once the move completes.</span></span> <span data-ttu-id="686e4-202">Dit geldt voor Word, Excel en PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="686e4-202">This applies to Word, Excel, and PowerPoint.</span></span>

### <a name="onenote-experience"></a><span data-ttu-id="686e4-203">OneNote ervaring</span><span class="sxs-lookup"><span data-stu-id="686e4-203">OneNote experience</span></span>

<span data-ttu-id="686e4-204">OneNote win32-client en uwp-app (Universal) worden notitieblokken automatisch gedetecteerd en naadloos gesynchroniseerd met de nieuwe sitelocatie zodra de site is verplaatst.</span><span class="sxs-lookup"><span data-stu-id="686e4-204">OneNote win32 client and UWP (Universal) App will automatically detect and seamlessly sync notebooks to the new site location once site move is complete.</span></span> <span data-ttu-id="686e4-205">De gebruiker hoeft zich niet opnieuw aan te melden of een andere actie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="686e4-205">The user does not need to sign in again or take any other action.</span></span> <span data-ttu-id="686e4-206">De enige zichtbare indicator voor de gebruiker is dat de synchronisatie van notitieblokken mislukt wanneer de site wordt verplaatst.</span><span class="sxs-lookup"><span data-stu-id="686e4-206">The only visible indicator to the user is notebook sync would fail when site move is in progress.</span></span> <span data-ttu-id="686e4-207">Deze ervaring is beschikbaar in de volgende OneNote clientversies:</span><span class="sxs-lookup"><span data-stu-id="686e4-207">This experience is available on the following OneNote client versions:</span></span>

- <span data-ttu-id="686e4-208">OneNote win32 – Versie 16.0.8326.2096 (en hoger)</span><span class="sxs-lookup"><span data-stu-id="686e4-208">OneNote win32 – Version 16.0.8326.2096 (and later)</span></span>
- <span data-ttu-id="686e4-209">OneNote UWP – Versie 16.0.8431.1006 (en hoger)</span><span class="sxs-lookup"><span data-stu-id="686e4-209">OneNote UWP – Version 16.0.8431.1006 (and later)</span></span>
- <span data-ttu-id="686e4-210">OneNote Mobiele app : versie 16.0.8431.1011 (en hoger)</span><span class="sxs-lookup"><span data-stu-id="686e4-210">OneNote Mobile App – Version 16.0.8431.1011 (and later)</span></span>

### <a name="teams-applicable-to-microsoft-365-group-connected-sites"></a><span data-ttu-id="686e4-211">Teams (van toepassing op verbonden Microsoft 365 groep)</span><span class="sxs-lookup"><span data-stu-id="686e4-211">Teams (applicable to Microsoft 365 Group connected sites)</span></span>

<span data-ttu-id="686e4-212">Wanneer de SharePoint site geo move is voltooid, hebben gebruikers toegang tot hun Microsoft 365 Groepssitebestanden in de Teams app.</span><span class="sxs-lookup"><span data-stu-id="686e4-212">When the SharePoint site geo move completes, users will have access to their Microsoft 365 Group site files on the Teams app.</span></span> <span data-ttu-id="686e4-213">Bovendien blijven bestanden die worden gedeeld via Teams chat vanaf hun site vóór geo-move, werken nadat de move is voltooid.</span><span class="sxs-lookup"><span data-stu-id="686e4-213">Additionally, files shared via Teams chat from their site prior to geo move will continue to work after move is complete.</span></span>

### <a name="sharepoint-mobile-app-iosandroid"></a><span data-ttu-id="686e4-214">SharePoint Mobiele app (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="686e4-214">SharePoint Mobile App (iOS/Android)</span></span>

<span data-ttu-id="686e4-215">De SharePoint mobiele app is compatibel met cross geo en kan de nieuwe geografische locatie van de site detecteren.</span><span class="sxs-lookup"><span data-stu-id="686e4-215">The SharePoint Mobile App is cross geo compatible and able to detect the site's new geo location.</span></span>

### <a name="sharepoint-workflows"></a><span data-ttu-id="686e4-216">SharePoint werkstromen</span><span class="sxs-lookup"><span data-stu-id="686e4-216">SharePoint workflows</span></span>

<span data-ttu-id="686e4-217">SharePoint 2013-werkstromen moeten opnieuw worden gepubliceerd nadat de site is verplaatst.</span><span class="sxs-lookup"><span data-stu-id="686e4-217">SharePoint 2013 workflows need to be republished after the site move.</span></span> <span data-ttu-id="686e4-218">SharePoint 2010-werkstromen moeten normaal blijven werken.</span><span class="sxs-lookup"><span data-stu-id="686e4-218">SharePoint 2010 workflows should continue to function normally.</span></span>

### <a name="apps"></a><span data-ttu-id="686e4-219">Apps</span><span class="sxs-lookup"><span data-stu-id="686e4-219">Apps</span></span>

<span data-ttu-id="686e4-220">Als u een site met apps verplaatst, moet u de app opnieuw instantieren op de nieuwe geografische locatie van de site, omdat de app en de verbindingen mogelijk niet beschikbaar zijn op de geografische locatie van de bestemming.</span><span class="sxs-lookup"><span data-stu-id="686e4-220">If you are moving a site with apps, you must re-instantiate the app in the site's new geo location as the app and its connections may not be available in the destination geo location.</span></span>

### <a name="flow"></a><span data-ttu-id="686e4-221">Flow</span><span class="sxs-lookup"><span data-stu-id="686e4-221">Flow</span></span>

<span data-ttu-id="686e4-222">In de meeste gevallen blijven stromen werken na een SharePoint site geo-move.</span><span class="sxs-lookup"><span data-stu-id="686e4-222">In most cases Flows will continue to work after a SharePoint site geo move.</span></span> <span data-ttu-id="686e4-223">U wordt aangeraden ze te testen zodra de verhuizing is voltooid.</span><span class="sxs-lookup"><span data-stu-id="686e4-223">We recommend that you test them once the move has completed.</span></span>

### <a name="powerapps"></a><span data-ttu-id="686e4-224">PowerApps</span><span class="sxs-lookup"><span data-stu-id="686e4-224">PowerApps</span></span>

<span data-ttu-id="686e4-225">PowerApps moeten opnieuw worden gemaakt op de doellocatie.</span><span class="sxs-lookup"><span data-stu-id="686e4-225">PowerApps need to be recreated in the destination location.</span></span>

### <a name="data-movement-between-geo-locations"></a><span data-ttu-id="686e4-226">Gegevensbewegingen tussen geografische locaties</span><span class="sxs-lookup"><span data-stu-id="686e4-226">Data movement between geo locations</span></span>

<span data-ttu-id="686e4-227">SharePoint gebruikt Azure Blob-opslag voor de inhoud ervan, terwijl de metagegevens die zijn gekoppeld aan sites en de bijbehorende bestanden, worden opgeslagen in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="686e4-227">SharePoint uses Azure Blob storage for its content, while the metadata associated with sites and its files is stored within SharePoint.</span></span> <span data-ttu-id="686e4-228">Nadat de site is verplaatst van de bronlocatie naar de geografische locatie van de bestemming, wordt ook de bijbehorende Blob-locatie Storage.</span><span class="sxs-lookup"><span data-stu-id="686e4-228">After the site is moved from its source geo location to its destination geo location, the service will also move its associated Blob Storage.</span></span> <span data-ttu-id="686e4-229">Blob Storage wordt in ongeveer 40 dagen voltooid verplaatst.</span><span class="sxs-lookup"><span data-stu-id="686e4-229">Blob Storage moves complete in approximately 40 days.</span></span>