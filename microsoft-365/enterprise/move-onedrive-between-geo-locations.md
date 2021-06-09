---
title: Een site OneDrive naar een andere geografische locatie verplaatsen
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Informatie over het verplaatsen van een OneDrive naar een andere geografische locatie, zoals het plannen van siteverplaatsing en het communiceren van verwachtingen aan gebruikers.
ms.openlocfilehash: 59b3fb47fd195967e7af056c7a71fb4e736471d1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688925"
---
# <a name="move-a-onedrive-site-to-a-different-geo-location"></a><span data-ttu-id="3491d-103">Een site OneDrive naar een andere geografische locatie verplaatsen</span><span class="sxs-lookup"><span data-stu-id="3491d-103">Move a OneDrive site to a different geo location</span></span> 

<span data-ttu-id="3491d-104">Met OneDrive geo-move kunt u de gegevens van een gebruiker OneDrive naar een andere geografische locatie verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="3491d-104">With OneDrive geo move, you can move a user's OneDrive to a different geo location.</span></span> <span data-ttu-id="3491d-105">OneDrive geo-move wordt uitgevoerd door de SharePoint onlinebeheerder of de Microsoft 365 globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="3491d-105">OneDrive geo move is performed by the SharePoint Online administrator or the Microsoft 365 global administrator.</span></span> <span data-ttu-id="3491d-106">Voordat u een geo-OneDrive start, moet u de gebruiker op de hoogte stellen van wie de OneDrive wordt verplaatst en raden ze aan alle bestanden te sluiten gedurende de duur van de verhuizing.</span><span class="sxs-lookup"><span data-stu-id="3491d-106">Before you start a OneDrive geo move, be sure to notify the user whose OneDrive is being moved and recommend they close all files for the duration of the move.</span></span> <span data-ttu-id="3491d-107">(Als de gebruiker een document heeft geopend met de Office client tijdens de verhuizing, moet het document na het verplaatsen worden opgeslagen op de nieuwe locatie.) De verhuizing kan desgewenst voor een toekomstige periode worden gepland.</span><span class="sxs-lookup"><span data-stu-id="3491d-107">(If the user has a document open using the Office client during the move, then upon move completion the document will need to be saved to the new location.) The move can be scheduled for a future time, if desired.</span></span>

<span data-ttu-id="3491d-108">De OneDrive-service gebruikt Azure Blob Storage om inhoud op te slaan.</span><span class="sxs-lookup"><span data-stu-id="3491d-108">The OneDrive service uses Azure Blob Storage to store content.</span></span> <span data-ttu-id="3491d-109">De Storage blob die is gekoppeld aan de OneDrive van de gebruiker, wordt binnen 40 dagen na de OneDrive voor de gebruiker van de bron naar de doellocatie verplaatst.</span><span class="sxs-lookup"><span data-stu-id="3491d-109">The Storage blob associated with the user's OneDrive will be moved from the source to destination geo location within 40 days of destination OneDrive being available to the user.</span></span> <span data-ttu-id="3491d-110">De toegang tot de OneDrive van de gebruiker wordt hersteld zodra de OneDrive beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="3491d-110">The access to the user's OneDrive will be restored as soon as the destination OneDrive is available.</span></span>

<span data-ttu-id="3491d-111">Tijdens OneDrive geoverhuisvenster (ongeveer 2-6 uur) is de OneDrive van de gebruiker ingesteld op alleen-lezen.</span><span class="sxs-lookup"><span data-stu-id="3491d-111">During OneDrive geo move window (about 2-6 hours) the user's OneDrive is set to read-only.</span></span> <span data-ttu-id="3491d-112">De gebruiker heeft nog steeds toegang tot zijn bestanden via de OneDrive-synchronisatieclient of via OneDrive site in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="3491d-112">The user can still access their files via the OneDrive sync client or their OneDrive site in SharePoint Online.</span></span> <span data-ttu-id="3491d-113">Nadat OneDrive geoverplaatsing is voltooid, wordt de gebruiker automatisch verbonden met zijn of haar OneDrive op de geografische locatie van de bestemming wanneer hij of zij naar OneDrive in het start startstation voor Microsoft 365 app navigeert.</span><span class="sxs-lookup"><span data-stu-id="3491d-113">After OneDrive geo move is complete, the user will be automatically connected to their OneDrive at the destination geo location when they navigate to OneDrive in the Microsoft 365 app launcher.</span></span> <span data-ttu-id="3491d-114">De synchronisatieclient wordt automatisch vanaf de nieuwe locatie gesynchroniseerd.</span><span class="sxs-lookup"><span data-stu-id="3491d-114">The sync client will automatically begin syncing from the new location.</span></span>

<span data-ttu-id="3491d-115">Voor de procedures in dit artikel is Microsoft Office SharePoint Online [PowerShell-module vereist.](https://www.microsoft.com/download/details.aspx?id=35588)</span><span class="sxs-lookup"><span data-stu-id="3491d-115">The procedures in this article require the [Microsoft SharePoint Online PowerShell Module](https://www.microsoft.com/download/details.aspx?id=35588).</span></span>

## <a name="communicating-to-your-users"></a><span data-ttu-id="3491d-116">Communiceren met uw gebruikers</span><span class="sxs-lookup"><span data-stu-id="3491d-116">Communicating to your users</span></span>

<span data-ttu-id="3491d-117">Wanneer u OneDrive sites verplaatst tussen geografische locaties, is het belangrijk om uw gebruikers te laten weten wat ze kunnen verwachten.</span><span class="sxs-lookup"><span data-stu-id="3491d-117">When moving OneDrive sites between geo locations, it's important to communicate to your users what to expect.</span></span> <span data-ttu-id="3491d-118">Dit kan gebruikersverwarring en oproepen naar uw helpdesk helpen verminderen.</span><span class="sxs-lookup"><span data-stu-id="3491d-118">This can help reduce user confusion and calls to your help desk.</span></span> <span data-ttu-id="3491d-119">E-mail uw gebruikers vóór de verhuizing en laat ze de volgende informatie weten:</span><span class="sxs-lookup"><span data-stu-id="3491d-119">Email your users before the move and let them know the following information:</span></span>

- <span data-ttu-id="3491d-120">Wanneer de overstap wordt verwacht en hoe lang deze naar verwachting zal duren</span><span class="sxs-lookup"><span data-stu-id="3491d-120">When the move is expected to start and how long it is expected to take</span></span>
- <span data-ttu-id="3491d-121">Naar welke geografische locatie de OneDrive wordt verplaatst en de URL voor toegang tot de nieuwe locatie</span><span class="sxs-lookup"><span data-stu-id="3491d-121">What geo location their OneDrive is moving to, and the URL to access the new location</span></span>
- <span data-ttu-id="3491d-122">Ze moeten hun bestanden sluiten en geen wijzigingen maken tijdens het verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="3491d-122">They should close their files and not make edits during the move.</span></span>
- <span data-ttu-id="3491d-123">Bestandsmachtigingen en delen worden niet gewijzigd als gevolg van de verhuizing.</span><span class="sxs-lookup"><span data-stu-id="3491d-123">File permissions and sharing will not change as a result of the move.</span></span>
- <span data-ttu-id="3491d-124">Wat u kunt verwachten van [de gebruikerservaring in een multi-geo-omgeving](multi-geo-user-experience.md)</span><span class="sxs-lookup"><span data-stu-id="3491d-124">What to expect from the [user experience in a multi-geo environment](multi-geo-user-experience.md)</span></span>

<span data-ttu-id="3491d-125">Zorg ervoor dat u uw gebruikers een e-mail stuurt wanneer de overstap is voltooid, zodat ze kunnen zien dat ze weer kunnen werken in OneDrive.</span><span class="sxs-lookup"><span data-stu-id="3491d-125">Be sure to send your users an email when the move has successfully completed informing them that they can resume working in OneDrive.</span></span>

## <a name="scheduling-onedrive-site-moves"></a><span data-ttu-id="3491d-126">Site-OneDrive plannen</span><span class="sxs-lookup"><span data-stu-id="3491d-126">Scheduling OneDrive site moves</span></span>

<span data-ttu-id="3491d-127">U kunt de OneDrive van tevoren plannen (verder in dit artikel beschreven).</span><span class="sxs-lookup"><span data-stu-id="3491d-127">You can schedule OneDrive site moves in advance (described later in this article).</span></span> <span data-ttu-id="3491d-128">Het is raadzaam om te beginnen met een klein aantal gebruikers om uw werkstromen en communicatiestrategieën te valideren.</span><span class="sxs-lookup"><span data-stu-id="3491d-128">We recommend that you start with a small number of users to validate your workflows and communication strategies.</span></span> <span data-ttu-id="3491d-129">Zodra u vertrouwd bent met het proces, kunt u de volgende stappen plannen:</span><span class="sxs-lookup"><span data-stu-id="3491d-129">Once you are comfortable with the process, you can schedule moves as follows:</span></span>

- <span data-ttu-id="3491d-130">U kunt maximaal 4.000 bewegingen tegelijk plannen.</span><span class="sxs-lookup"><span data-stu-id="3491d-130">You can schedule up to 4,000 moves at a time.</span></span>
- <span data-ttu-id="3491d-131">Wanneer de bewegingen beginnen, kunt u meer plannen, met een maximum van 4.000 in behandeling zijnde bewegingen in de wachtrij en een bepaalde tijd.</span><span class="sxs-lookup"><span data-stu-id="3491d-131">As the moves begin, you can schedule more, with a maximum of 4,000 pending moves in the queue and any given time.</span></span>
- <span data-ttu-id="3491d-132">De maximale grootte van een OneDrive die kan worden verplaatst, is 1 terabyte (1 TB).</span><span class="sxs-lookup"><span data-stu-id="3491d-132">The maximum size of a OneDrive that can be moved is 1 terabyte (1 TB).</span></span>

## <a name="moving-a-onedrive-site"></a><span data-ttu-id="3491d-133">Een site OneDrive verplaatsen</span><span class="sxs-lookup"><span data-stu-id="3491d-133">Moving a OneDrive site</span></span>

<span data-ttu-id="3491d-134">Als u een OneDrive geo-move wilt uitvoeren, moet de tenantbeheerder eerst de voorkeurslocatie voor gegevens (PDL) van de gebruiker instellen op de juiste geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="3491d-134">To perform a OneDrive geo move, the tenant administrator must first set the user's Preferred Data Location (PDL) to the appropriate geo location.</span></span> <span data-ttu-id="3491d-135">Wanneer de PDL is ingesteld, wacht u ten minste 24 uur totdat de PDL-update wordt gesynchroniseerd over de geografische locaties voordat u de OneDrive geo-move.</span><span class="sxs-lookup"><span data-stu-id="3491d-135">Once the PDL is set, wait for at least 24 hours for the PDL update to sync across the geo locations before starting the OneDrive geo move.</span></span>

<span data-ttu-id="3491d-136">Wanneer u de geoverplaatsings cmdlets gebruikt, maakt u verbinding met SPO Service op de huidige locatie OneDrive gebruiker, met de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="3491d-136">When using the geo move cmdlets, connect to SPO Service at the user's current OneDrive geo location, using the following syntax:</span></span>

`Connect-SPOService -url https://<tenantName>-admin.sharepoint.com`

<span data-ttu-id="3491d-137">Bijvoorbeeld: Als u OneDrive gebruikers 'Matt@contosoenergy.onmicrosoft.com' wilt verplaatsen, maakt u verbinding met het EUR SharePoint-beheercentrum terwijl de OneDrive van de gebruiker zich op de geografische locatie van EUR bevindt:</span><span class="sxs-lookup"><span data-stu-id="3491d-137">For example: To move OneDrive of user 'Matt@contosoenergy.onmicrosoft.com', connect to EUR SharePoint Admin center as the user's OneDrive is in EUR geo location:</span></span>

`Connect-SPOSservice -url https://contosoenergyeur-admin.sharepoint.com`

![Schermafbeelding van PowerShell-venster met connect-sposervice-cmdlet](../media/move-onedrive-between-geo-locations-image1.png)

## <a name="validating-the-environment"></a><span data-ttu-id="3491d-139">De omgeving valideren</span><span class="sxs-lookup"><span data-stu-id="3491d-139">Validating the environment</span></span>

<span data-ttu-id="3491d-140">Voordat u een geo-OneDrive start, raden we u aan de omgeving te valideren.</span><span class="sxs-lookup"><span data-stu-id="3491d-140">Before you start a OneDrive geo move, we recommend that you validate the environment.</span></span>

<span data-ttu-id="3491d-141">Voer het volgende uit om ervoor te zorgen dat alle geografische locaties compatibel zijn:</span><span class="sxs-lookup"><span data-stu-id="3491d-141">To ensure that all geo locations are compatible, run:</span></span>

`Get-SPOGeoMoveCrossCompatibilityStatus`

<span data-ttu-id="3491d-142">U ziet een lijst met uw geografische locaties en of inhoud kan worden verplaatst, wordt aangeduid als 'Compatibel'.</span><span class="sxs-lookup"><span data-stu-id="3491d-142">You will see a list of your geo locations and whether content can be moved between will be denoted as "Compatible".</span></span> <span data-ttu-id="3491d-143">Als de opdracht 'Niet compatibel' retourneert, kunt u proberen de status op een later tijdstip te valideren.</span><span class="sxs-lookup"><span data-stu-id="3491d-143">If the command returns "Incompatible" please retry validating the status at a later date.</span></span>

<span data-ttu-id="3491d-144">Als een OneDrive bijvoorbeeld een subsite bevat, kan deze niet worden verplaatst.</span><span class="sxs-lookup"><span data-stu-id="3491d-144">If a OneDrive contains a subsite, for example, it cannot be moved.</span></span> <span data-ttu-id="3491d-145">U kunt de cmdlet Start-SPOUserAndContentMove -ValidationOnly gebruiken om te valideren of de OneDrive kan worden verplaatst:</span><span class="sxs-lookup"><span data-stu-id="3491d-145">You can use the Start-SPOUserAndContentMove cmdlet with the -ValidationOnly parameter to validate if the OneDrive is able to be moved:</span></span>

`Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly`

<span data-ttu-id="3491d-146">Dit geeft succes als de OneDrive gereed is om te worden verplaatst of Mislukken als er een wettelijke wacht- of subsite is die de overstap verhindert.</span><span class="sxs-lookup"><span data-stu-id="3491d-146">This will return Success if the OneDrive is ready to be moved or Fail if there is a legal hold or subsite that would prevent the move.</span></span> <span data-ttu-id="3491d-147">Nadat u hebt gevalideerd dat de OneDrive klaar is om te worden verplaatst, kunt u de overstap starten.</span><span class="sxs-lookup"><span data-stu-id="3491d-147">Once you have validated that the OneDrive is ready to move, you can start the move.</span></span>

## <a name="start-a-onedrive-geo-move"></a><span data-ttu-id="3491d-148">Een geo-OneDrive starten</span><span class="sxs-lookup"><span data-stu-id="3491d-148">Start a OneDrive geo move</span></span>

<span data-ttu-id="3491d-149">Als u de move wilt starten, gaat u als volgende te werk:</span><span class="sxs-lookup"><span data-stu-id="3491d-149">To start the move, run:</span></span>  

`Start-SPOUserAndContentMove -UserPrincipalName <UserPrincipalName> -DestinationDataLocation <DestinationDataLocation>`

<span data-ttu-id="3491d-150">Deze parameters gebruiken:</span><span class="sxs-lookup"><span data-stu-id="3491d-150">Using these parameters:</span></span>

-   <span data-ttu-id="3491d-151">_UserPrincipalName:_ UPN van de gebruiker van wie OneDrive wordt verplaatst.</span><span class="sxs-lookup"><span data-stu-id="3491d-151">_UserPrincipalName_ – UPN of the user whose OneDrive is being moved.</span></span>

-   <span data-ttu-id="3491d-152">_DestinationDataLocation:_ Geo-Location waar de OneDrive moet worden verplaatst.</span><span class="sxs-lookup"><span data-stu-id="3491d-152">_DestinationDataLocation_ – Geo-Location where the OneDrive needs to be moved.</span></span> <span data-ttu-id="3491d-153">Dit moet hetzelfde zijn als de gewenste gegevenslocatie van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="3491d-153">This should be same as the user's preferred data location.</span></span>

<span data-ttu-id="3491d-154">Als u bijvoorbeeld de OneDrive van matt@contosoenergy.onmicrosoft.com van EUR naar AUS wilt verplaatsen, gaat u als volgende te werk:</span><span class="sxs-lookup"><span data-stu-id="3491d-154">For example, to move the OneDrive of matt@contosoenergy.onmicrosoft.com from EUR to AUS, run:</span></span>

`Start-SPOUserAndContentMove -UserPrincipalName matt@contosoenergy.onmicrosoft.com -DestinationDataLocation AUS`

![Schermafbeelding van PowerShell-venster met Start-SPOUserAndContentMove cmdlet](../media/move-onedrive-between-geo-locations-image2.png)

<span data-ttu-id="3491d-156">Als u een geografische beweging voor een later tijdstip wilt plannen, gebruikt u een van de volgende parameters:</span><span class="sxs-lookup"><span data-stu-id="3491d-156">To schedule a geo move for a later time, use one of the following parameters:</span></span>

-   <span data-ttu-id="3491d-157">_PreferredMoveBeginDate:_ de move begint waarschijnlijk op deze opgegeven tijd.</span><span class="sxs-lookup"><span data-stu-id="3491d-157">_PreferredMoveBeginDate_ – The move will likely begin at this specified time.</span></span> <span data-ttu-id="3491d-158">Tijd moet worden opgegeven in Coordinated Universal Time (UTC).</span><span class="sxs-lookup"><span data-stu-id="3491d-158">Time must be specified in Coordinated Universal Time (UTC).</span></span>

-   <span data-ttu-id="3491d-159">_PreferredMoveEndDate:_ de move wordt waarschijnlijk voltooid op deze opgegeven tijd, op basis van de beste inspanning.</span><span class="sxs-lookup"><span data-stu-id="3491d-159">_PreferredMoveEndDate_ – The move will likely be completed by this specified time, on a best effort basis.</span></span> <span data-ttu-id="3491d-160">Tijd moet worden opgegeven in Coordinated Universal Time (UTC).</span><span class="sxs-lookup"><span data-stu-id="3491d-160">Time must be specified in Coordinated Universal Time (UTC).</span></span> 

## <a name="cancel-a-onedrive-geo-move"></a><span data-ttu-id="3491d-161">Een geo-OneDrive annuleren</span><span class="sxs-lookup"><span data-stu-id="3491d-161">Cancel a OneDrive geo move</span></span> 

<span data-ttu-id="3491d-162">U kunt de geografische beweging van de OneDrive van een gebruiker stoppen, mits de beweging niet wordt uitgevoerd of voltooid met behulp van de cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3491d-162">You can stop the geo move of a user's OneDrive, provided the move is not in progress or completed by using the cmdlet:</span></span>

`Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>`

<span data-ttu-id="3491d-163">Waarbij _UserPrincipalName_ de UPN is van de gebruiker van wie OneDrive u wilt stoppen.</span><span class="sxs-lookup"><span data-stu-id="3491d-163">Where _UserPrincipalName_ is the UPN of the user whose OneDrive move you want to stop.</span></span>

## <a name="determining-current-status"></a><span data-ttu-id="3491d-164">Huidige status bepalen</span><span class="sxs-lookup"><span data-stu-id="3491d-164">Determining current status</span></span>

<span data-ttu-id="3491d-165">U kunt de status van een OneDrive geo verplaatsen in of uit de geo die u hebt verbonden met de Get-SPOUserAndContentMoveState cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3491d-165">You can check the status of a OneDrive geo move in or out of the geo that you're connected to by using the Get-SPOUserAndContentMoveState cmdlet.</span></span>

<span data-ttu-id="3491d-166">De statussen voor verplaatsen worden in de volgende tabel beschreven.</span><span class="sxs-lookup"><span data-stu-id="3491d-166">The move statuses are described in the following table.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3491d-167"><strong>Status</strong></span><span class="sxs-lookup"><span data-stu-id="3491d-167"><strong>Status</strong></span></span></th>
<th align="left"><span data-ttu-id="3491d-168"><strong>Beschrijving</strong></span><span class="sxs-lookup"><span data-stu-id="3491d-168"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="3491d-169">NotStarted</span><span class="sxs-lookup"><span data-stu-id="3491d-169">NotStarted</span></span></td>
<td align="left"><span data-ttu-id="3491d-170">De move is nog niet gestart.</span><span class="sxs-lookup"><span data-stu-id="3491d-170">The move has not started.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="3491d-171">InProgress (<em>n</em>/4)</span><span class="sxs-lookup"><span data-stu-id="3491d-171">InProgress (<em>n</em>/4)</span></span></td>
<td align="left"><span data-ttu-id="3491d-172">De move wordt uitgevoerd in een van de volgende staten: Validatie (1/4), Back-up (2/4), Herstellen (3/4), Opschoning (4-4).</span><span class="sxs-lookup"><span data-stu-id="3491d-172">The move is in progress in one of the following states: Validation (1/4), Backup (2/4), Restore (3/4), Cleanup (4/4).</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="3491d-173">Succes</span><span class="sxs-lookup"><span data-stu-id="3491d-173">Success</span></span></td>
<td align="left"><span data-ttu-id="3491d-174">De verhuizing is voltooid.</span><span class="sxs-lookup"><span data-stu-id="3491d-174">The move has completed successfully.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="3491d-175">Mislukt</span><span class="sxs-lookup"><span data-stu-id="3491d-175">Failed</span></span></td>
<td align="left"><span data-ttu-id="3491d-176">De beweging is mislukt.</span><span class="sxs-lookup"><span data-stu-id="3491d-176">The move failed.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="3491d-177">Gebruik de parameter UserPrincipalName om de status van de move van een specifieke gebruiker te vinden:</span><span class="sxs-lookup"><span data-stu-id="3491d-177">To find the status of a specific user's move, use the UserPrincipalName parameter:</span></span>

`Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>`

<span data-ttu-id="3491d-178">Gebruik de parameter MoveState met een van de volgende waarden om de status van alle bewegingen in of uit de geografische locatie te vinden die u hebt verbonden: NotStarted, InProgress, Success, Failed, All.</span><span class="sxs-lookup"><span data-stu-id="3491d-178">To find the status of all of the moves in or out of the geo location that you're connected to, use the MoveState parameter with one of the following values: NotStarted, InProgress, Success, Failed, All.</span></span>

`Get-SPOUserAndContentMoveState -MoveState <value>`

<span data-ttu-id="3491d-179">U kunt ook de `-Verbose` parameter toevoegen voor uitgebreidere beschrijvingen van de status verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="3491d-179">You can also add the `-Verbose` parameter for more verbose descriptions of the move state.</span></span>

## <a name="user-experience"></a><span data-ttu-id="3491d-180">Gebruikerservaring</span><span class="sxs-lookup"><span data-stu-id="3491d-180">User Experience</span></span>

<span data-ttu-id="3491d-181">Gebruikers van OneDrive moeten minimale onderbrekingen zien als hun OneDrive naar een andere geografische locatie wordt verplaatst.</span><span class="sxs-lookup"><span data-stu-id="3491d-181">Users of OneDrive should notice minimal disruption if their OneDrive is moved to a different geo location.</span></span> <span data-ttu-id="3491d-182">Afgezien van een korte status alleen-lezen tijdens het verplaatsen, blijven bestaande koppelingen en machtigingen werken zoals verwacht wanneer de verhuizing is voltooid.</span><span class="sxs-lookup"><span data-stu-id="3491d-182">Aside from a brief read-only state during the move, existing links and permissions will continue to work as expected once the move is completed.</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="3491d-183">OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="3491d-183">OneDrive for Business</span></span>

<span data-ttu-id="3491d-184">Terwijl de move wordt uitgevoerd, is de OneDrive van de gebruiker ingesteld op alleen-lezen.</span><span class="sxs-lookup"><span data-stu-id="3491d-184">While the move is in progress the user's OneDrive is set to read-only.</span></span> <span data-ttu-id="3491d-185">Wanneer de overstap is voltooid, wordt de gebruiker doorgestuurd naar zijn of haar OneDrive in de nieuwe geografische locatie wanneer hij of zij naar OneDrive het start- Microsoft 365 app of een webbrowser navigeert.</span><span class="sxs-lookup"><span data-stu-id="3491d-185">Once the move is completed, the user is directed to their OneDrive in the new geo location when they navigate to OneDrive the Microsoft 365 app launcher or a web browser.</span></span>

### <a name="permissions-on-onedrive-content"></a><span data-ttu-id="3491d-186">Machtigingen voor OneDrive inhoud</span><span class="sxs-lookup"><span data-stu-id="3491d-186">Permissions on OneDrive content</span></span>

<span data-ttu-id="3491d-187">Gebruikers met machtigingen voor het OneDrive inhoud hebben nog steeds toegang tot de inhoud tijdens de verhuizing en nadat deze is voltooid.</span><span class="sxs-lookup"><span data-stu-id="3491d-187">Users with permissions to OneDrive content will continue to have access to the content during the move and after it's complete.</span></span>

### <a name="onedrive-sync-client"></a><span data-ttu-id="3491d-188">OneDrive Synchronisatieclient</span><span class="sxs-lookup"><span data-stu-id="3491d-188">OneDrive Sync Client</span></span> 

<span data-ttu-id="3491d-189">De OneDrive-synchronisatieclient detecteert automatisch en schakelt naadloos synchronisatie over naar de nieuwe OneDrive-locatie zodra de OneDrive geoverplaatsing is voltooid.</span><span class="sxs-lookup"><span data-stu-id="3491d-189">The OneDrive sync client will automatically detect and seamlessly transfer syncing to the new OneDrive location once the OneDrive geo move is complete.</span></span> <span data-ttu-id="3491d-190">De gebruiker hoeft zich niet opnieuw aan te melden of een andere actie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="3491d-190">The user does not need to sign-in again or take any other action.</span></span>  <span data-ttu-id="3491d-191">(Versie 17.3.6943.0625 of hoger van de synchronisatieclient vereist.)</span><span class="sxs-lookup"><span data-stu-id="3491d-191">(Version 17.3.6943.0625 or later of the sync client required.)</span></span>

<span data-ttu-id="3491d-192">Als een gebruiker een bestand bij werkt terwijl de OneDrive geo-move wordt uitgevoerd, meldt de synchronisatieclient dat de uploads van bestanden in behandeling zijn terwijl de overstap wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="3491d-192">If a user updates a file while the OneDrive geo move is in progress, the sync client will notify them that file uploads are pending while the move is underway.</span></span>

### <a name="sharing-links"></a><span data-ttu-id="3491d-193">Koppelingen voor delen</span><span class="sxs-lookup"><span data-stu-id="3491d-193">Sharing links</span></span> 

<span data-ttu-id="3491d-194">Wanneer OneDrive geoverplaatsing hebt voltooid, worden de bestaande gedeelde koppelingen voor de bestanden die zijn verplaatst, automatisch omgeleid naar de nieuwe geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="3491d-194">Upon OneDrive geo move completion, the existing shared links for the files that were moved will automatically redirect to the new geo location.</span></span>

### <a name="onenote-experience"></a><span data-ttu-id="3491d-195">OneNote Ervaring</span><span class="sxs-lookup"><span data-stu-id="3491d-195">OneNote Experience</span></span> 

<span data-ttu-id="3491d-196">OneNote win32-client en uwp-app (Universal) worden notitieblokken automatisch gedetecteerd en naadloos gesynchroniseerd naar de nieuwe OneDrive-locatie wanneer OneDrive geo-move is voltooid.</span><span class="sxs-lookup"><span data-stu-id="3491d-196">OneNote win32 client and UWP (Universal) App will automatically detect and seamlessly sync notebooks to the new OneDrive location once OneDrive geo move is complete.</span></span> <span data-ttu-id="3491d-197">De gebruiker hoeft zich niet opnieuw aan te melden of een andere actie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="3491d-197">The user does not need to sign-in again or take any other action.</span></span> <span data-ttu-id="3491d-198">De enige zichtbare indicator voor de gebruiker is dat de synchronisatie van notitieblokken mislukt wanneer OneDrive geo-move wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="3491d-198">The only visible indicator to the user is notebook sync would fail when OneDrive geo move is in progress.</span></span> <span data-ttu-id="3491d-199">Deze ervaring is beschikbaar in de volgende OneNote clientversies:</span><span class="sxs-lookup"><span data-stu-id="3491d-199">This experience is available on the following OneNote client versions:</span></span>

-   <span data-ttu-id="3491d-200">OneNote win32 – Versie 16.0.8326.2096 (en hoger)</span><span class="sxs-lookup"><span data-stu-id="3491d-200">OneNote win32 – Version 16.0.8326.2096 (and later)</span></span>

-   <span data-ttu-id="3491d-201">OneNote UWP – Versie 16.0.8431.1006 (en hoger)</span><span class="sxs-lookup"><span data-stu-id="3491d-201">OneNote UWP – Version 16.0.8431.1006 (and later)</span></span>

-   <span data-ttu-id="3491d-202">OneNote Mobiele app : versie 16.0.8431.1011 (en hoger)</span><span class="sxs-lookup"><span data-stu-id="3491d-202">OneNote Mobile App – Version 16.0.8431.1011 (and later)</span></span>

### <a name="teams-app"></a><span data-ttu-id="3491d-203">Teams app</span><span class="sxs-lookup"><span data-stu-id="3491d-203">Teams app</span></span>

<span data-ttu-id="3491d-204">Wanneer OneDrive geo-move hebt voltooid, hebben gebruikers toegang tot hun OneDrive bestanden in de Teams app.</span><span class="sxs-lookup"><span data-stu-id="3491d-204">Upon OneDrive geo move completion, users will have access to their OneDrive files on the Teams app.</span></span> <span data-ttu-id="3491d-205">Bovendien blijven bestanden die worden gedeeld via Teams chat vanaf hun OneDrive voordat de geo-beweging wordt verplaatst, werken nadat de beweging is voltooid.</span><span class="sxs-lookup"><span data-stu-id="3491d-205">Additionally, files shared via Teams chat from their OneDrive prior to geo move will continue to work after move is complete.</span></span>

### <a name="onedrive-for-business-mobile-app-ios"></a><span data-ttu-id="3491d-206">OneDrive voor Bedrijven Mobiele app (iOS)</span><span class="sxs-lookup"><span data-stu-id="3491d-206">OneDrive for Business Mobile App (iOS)</span></span> 

<span data-ttu-id="3491d-207">Wanneer OneDrive geo-move voltooid is, moet de gebruiker zich aanmelden en zich opnieuw aanmelden in de mobiele iOS-app om te synchroniseren met de nieuwe OneDrive locatie.</span><span class="sxs-lookup"><span data-stu-id="3491d-207">Upon OneDrive geo move completion, the user would need to sign out and sign in again on the iOS Mobile App to sync to the new OneDrive location.</span></span>

### <a name="existing-followed-groups-and-sites"></a><span data-ttu-id="3491d-208">Bestaande gevolgde groepen en sites</span><span class="sxs-lookup"><span data-stu-id="3491d-208">Existing followed groups and sites</span></span>

<span data-ttu-id="3491d-209">Gevolgde sites en groepen worden in de OneDrive van de gebruiker, ongeacht hun geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="3491d-209">Followed sites and groups will show up in the user's OneDrive regardless of their geo location.</span></span> <span data-ttu-id="3491d-210">Sites en groepen die op een andere geografische locatie worden gehost, worden geopend op een apart tabblad.</span><span class="sxs-lookup"><span data-stu-id="3491d-210">Sites and groups hosted in another geo location will open in a separate tab.</span></span>

### <a name="delve-geo-url-updates"></a><span data-ttu-id="3491d-211">Delve Geo-URL-updates</span><span class="sxs-lookup"><span data-stu-id="3491d-211">Delve Geo URL updates</span></span>

<span data-ttu-id="3491d-212">Gebruikers worden alleen naar de Delve geo verzonden die overeenkomt met hun PDL nadat hun OneDrive is verplaatst naar de nieuwe geo.</span><span class="sxs-lookup"><span data-stu-id="3491d-212">Users will be sent to the Delve geo corresponding to their PDL only after their OneDrive has been moved to the new geo.</span></span>
