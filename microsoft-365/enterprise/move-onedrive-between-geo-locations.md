---
title: Een OneDrive-site naar een andere geografische locatie verplaatsen
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
description: Informatie over het verplaatsen van een OneDrive-site naar een andere geografische locatie, waaronder het plannen van site-verplaatsings-en gebruikers vooruitzichten.
ms.openlocfilehash: 59b3fb47fd195967e7af056c7a71fb4e736471d1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688925"
---
# <a name="move-a-onedrive-site-to-a-different-geo-location"></a><span data-ttu-id="271d2-103">Een OneDrive-site naar een andere geografische locatie verplaatsen</span><span class="sxs-lookup"><span data-stu-id="271d2-103">Move a OneDrive site to a different geo location</span></span> 

<span data-ttu-id="271d2-104">Met OneDrive geo Move kunt u de OneDrive van een gebruiker naar een andere geografische locatie verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="271d2-104">With OneDrive geo move, you can move a user's OneDrive to a different geo location.</span></span> <span data-ttu-id="271d2-105">OneDrive geo Move voor OneDrive wordt uitgevoerd door de SharePoint Online-beheerder of de globale beheerder van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="271d2-105">OneDrive geo move is performed by the SharePoint Online administrator or the Microsoft 365 global administrator.</span></span> <span data-ttu-id="271d2-106">Voordat u begint met het verplaatsen van een OneDrive-geografische verplaatsing, moet u de gebruiker op de hoogte stellen van de gebruiker van wie de OneDrive wordt verplaatst en wordt u aangeraden alle bestanden te sluiten gedurende de verhuizing.</span><span class="sxs-lookup"><span data-stu-id="271d2-106">Before you start a OneDrive geo move, be sure to notify the user whose OneDrive is being moved and recommend they close all files for the duration of the move.</span></span> <span data-ttu-id="271d2-107">(Als de gebruiker tijdens de verhuizing een document heeft geopend met de Office-client, moet het document worden opgeslagen op de nieuwe locatie.) U kunt de verhuizing later opnieuw plannen.</span><span class="sxs-lookup"><span data-stu-id="271d2-107">(If the user has a document open using the Office client during the move, then upon move completion the document will need to be saved to the new location.) The move can be scheduled for a future time, if desired.</span></span>

<span data-ttu-id="271d2-108">De OneDrive-service gebruikt Azure Blob Storage om inhoud op te slaan.</span><span class="sxs-lookup"><span data-stu-id="271d2-108">The OneDrive service uses Azure Blob Storage to store content.</span></span> <span data-ttu-id="271d2-109">De blobopslag van de opslagruimte die gekoppeld is aan de OneDrive van de gebruiker wordt verplaatst van de bron naar het doel geografische gebied binnen 40 dagen van de doel-OneDrive die beschikbaar is voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="271d2-109">The Storage blob associated with the user's OneDrive will be moved from the source to destination geo location within 40 days of destination OneDrive being available to the user.</span></span> <span data-ttu-id="271d2-110">De toegang tot de OneDrive van de gebruiker wordt hersteld zodra de beschikbare doel-OneDrive beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="271d2-110">The access to the user's OneDrive will be restored as soon as the destination OneDrive is available.</span></span>

<span data-ttu-id="271d2-111">Tijdens OneDrive geo-verhuizings venster (ongeveer 2-6 uur) wordt de OneDrive van de gebruiker ingesteld op alleen-lezen.</span><span class="sxs-lookup"><span data-stu-id="271d2-111">During OneDrive geo move window (about 2-6 hours) the user's OneDrive is set to read-only.</span></span> <span data-ttu-id="271d2-112">Gebruikers hebben nog steeds toegang tot hun bestanden via de OneDrive-synchronisatieclient of hun OneDrive-site in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="271d2-112">The user can still access their files via the OneDrive sync client or their OneDrive site in SharePoint Online.</span></span> <span data-ttu-id="271d2-113">Nadat OneDrive is verplaatst, wordt de gebruiker automatisch verbonden met hun OneDrive op de doellocatie van de geografische locatie wanneer ze naar OneDrive navigeren in het startprogramma voor apps van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="271d2-113">After OneDrive geo move is complete, the user will be automatically connected to their OneDrive at the destination geo location when they navigate to OneDrive in the Microsoft 365 app launcher.</span></span> <span data-ttu-id="271d2-114">De synchronisatieclient begint automatisch met synchroniseren vanaf de nieuwe locatie.</span><span class="sxs-lookup"><span data-stu-id="271d2-114">The sync client will automatically begin syncing from the new location.</span></span>

<span data-ttu-id="271d2-115">Voor de procedures in dit artikel is de [Microsoft SharePoint Online PowerShell-module](https://www.microsoft.com/download/details.aspx?id=35588)vereist.</span><span class="sxs-lookup"><span data-stu-id="271d2-115">The procedures in this article require the [Microsoft SharePoint Online PowerShell Module](https://www.microsoft.com/download/details.aspx?id=35588).</span></span>

## <a name="communicating-to-your-users"></a><span data-ttu-id="271d2-116">Communiceren met uw gebruikers</span><span class="sxs-lookup"><span data-stu-id="271d2-116">Communicating to your users</span></span>

<span data-ttu-id="271d2-117">Als u OneDrive-sites tussen geo-locaties verplaatst, is het belangrijk om te communiceren met uw gebruikers wat u kunt verwachten.</span><span class="sxs-lookup"><span data-stu-id="271d2-117">When moving OneDrive sites between geo locations, it's important to communicate to your users what to expect.</span></span> <span data-ttu-id="271d2-118">Dit kan de gebruikers verwarring en oproepen naar uw helpdesk verminderen.</span><span class="sxs-lookup"><span data-stu-id="271d2-118">This can help reduce user confusion and calls to your help desk.</span></span> <span data-ttu-id="271d2-119">E-mail uw gebruikers voorafgaand aan de verhuizing en laat ze de volgende informatie weten:</span><span class="sxs-lookup"><span data-stu-id="271d2-119">Email your users before the move and let them know the following information:</span></span>

- <span data-ttu-id="271d2-120">Wanneer de verplaatsing naar verwachting begint en hoe lang deze duurt</span><span class="sxs-lookup"><span data-stu-id="271d2-120">When the move is expected to start and how long it is expected to take</span></span>
- <span data-ttu-id="271d2-121">De geografische locatie waarnaar de OneDrive wordt verplaatst, en de URL voor toegang tot de nieuwe locatie</span><span class="sxs-lookup"><span data-stu-id="271d2-121">What geo location their OneDrive is moving to, and the URL to access the new location</span></span>
- <span data-ttu-id="271d2-122">De persoon moet hun bestanden sluiten en geen wijzigingen aanbrengen tijdens de verhuizing.</span><span class="sxs-lookup"><span data-stu-id="271d2-122">They should close their files and not make edits during the move.</span></span>
- <span data-ttu-id="271d2-123">Het is niet mogelijk om bestanden te bewerken en te delen.</span><span class="sxs-lookup"><span data-stu-id="271d2-123">File permissions and sharing will not change as a result of the move.</span></span>
- <span data-ttu-id="271d2-124">Wat kunt u verwachten van de [gebruikerservaring in een omgeving met meerdere geografische omgevingen](multi-geo-user-experience.md) ?</span><span class="sxs-lookup"><span data-stu-id="271d2-124">What to expect from the [user experience in a multi-geo environment](multi-geo-user-experience.md)</span></span>

<span data-ttu-id="271d2-125">Zorg ervoor dat u uw gebruikers een e-mailbericht stuurt wanneer de overstap is voltooid, zodat ze verder kunnen werken in OneDrive.</span><span class="sxs-lookup"><span data-stu-id="271d2-125">Be sure to send your users an email when the move has successfully completed informing them that they can resume working in OneDrive.</span></span>

## <a name="scheduling-onedrive-site-moves"></a><span data-ttu-id="271d2-126">OneDrive-site plannen</span><span class="sxs-lookup"><span data-stu-id="271d2-126">Scheduling OneDrive site moves</span></span>

<span data-ttu-id="271d2-127">U kunt instellen dat de OneDrive-site vooraf wordt bewogen (verderop in dit artikel wordt beschreven).</span><span class="sxs-lookup"><span data-stu-id="271d2-127">You can schedule OneDrive site moves in advance (described later in this article).</span></span> <span data-ttu-id="271d2-128">We raden u aan te beginnen met een klein aantal gebruikers om uw werkstromen en communicatie strategieën te valideren.</span><span class="sxs-lookup"><span data-stu-id="271d2-128">We recommend that you start with a small number of users to validate your workflows and communication strategies.</span></span> <span data-ttu-id="271d2-129">Wanneer u vertrouwd bent met het proces, kunt u het volgende plannen:</span><span class="sxs-lookup"><span data-stu-id="271d2-129">Once you are comfortable with the process, you can schedule moves as follows:</span></span>

- <span data-ttu-id="271d2-130">U kunt maximaal 4.000 verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="271d2-130">You can schedule up to 4,000 moves at a time.</span></span>
- <span data-ttu-id="271d2-131">Zoals de verhuizing begint, kunt u meer plannen, met een maximum van 4.000 in behandeling in de wachtrij en op een bepaald moment.</span><span class="sxs-lookup"><span data-stu-id="271d2-131">As the moves begin, you can schedule more, with a maximum of 4,000 pending moves in the queue and any given time.</span></span>
- <span data-ttu-id="271d2-132">De maximumgrootte van een OneDrive die kan worden verplaatst, is 1 terabyte (1 TB).</span><span class="sxs-lookup"><span data-stu-id="271d2-132">The maximum size of a OneDrive that can be moved is 1 terabyte (1 TB).</span></span>

## <a name="moving-a-onedrive-site"></a><span data-ttu-id="271d2-133">Een OneDrive-site verplaatsen</span><span class="sxs-lookup"><span data-stu-id="271d2-133">Moving a OneDrive site</span></span>

<span data-ttu-id="271d2-134">Voor het uitvoeren van een OneDrive-geografische verplaatsing moet de tenantbeheerder eerst de voorkeurs gegevenslocatie (PDL) van de gebruiker instellen op de gewenste geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="271d2-134">To perform a OneDrive geo move, the tenant administrator must first set the user's Preferred Data Location (PDL) to the appropriate geo location.</span></span> <span data-ttu-id="271d2-135">Wanneer de PDL is ingesteld, wacht u minimaal 24 uur voordat de PDL-update via de geo-locaties is gesynchroniseerd voordat u de geografische verhuizing van OneDrive start.</span><span class="sxs-lookup"><span data-stu-id="271d2-135">Once the PDL is set, wait for at least 24 hours for the PDL update to sync across the geo locations before starting the OneDrive geo move.</span></span>

<span data-ttu-id="271d2-136">Wanneer u de geo Move-cmdlets gebruikt, kunt u de volgende syntaxis gebruiken om verbinding te maken met de SPO-service op de huidige OneDrive-geografische locatie van de gebruiker:</span><span class="sxs-lookup"><span data-stu-id="271d2-136">When using the geo move cmdlets, connect to SPO Service at the user's current OneDrive geo location, using the following syntax:</span></span>

`Connect-SPOService -url https://<tenantName>-admin.sharepoint.com`

<span data-ttu-id="271d2-137">Als u bijvoorbeeld OneDrive van User ' Matt@contosoenergy.onmicrosoft.com ' wilt verplaatsen, maakt u verbinding met het SharePoint-Beheercentrum als de OneDrive van de gebruiker wordt gebruikt in plaats van de geografische locatie van de gebruiker:</span><span class="sxs-lookup"><span data-stu-id="271d2-137">For example: To move OneDrive of user 'Matt@contosoenergy.onmicrosoft.com', connect to EUR SharePoint Admin center as the user's OneDrive is in EUR geo location:</span></span>

`Connect-SPOSservice -url https://contosoenergyeur-admin.sharepoint.com`

![Schermafbeelding van het PowerShell-venster met de cmdlet Connect-sposervice](../media/move-onedrive-between-geo-locations-image1.png)

## <a name="validating-the-environment"></a><span data-ttu-id="271d2-139">De omgeving valideren</span><span class="sxs-lookup"><span data-stu-id="271d2-139">Validating the environment</span></span>

<span data-ttu-id="271d2-140">U wordt aangeraden om de omgeving te valideren voordat u een OneDrive-geografische verhuizing start.</span><span class="sxs-lookup"><span data-stu-id="271d2-140">Before you start a OneDrive geo move, we recommend that you validate the environment.</span></span>

<span data-ttu-id="271d2-141">Voer de volgende opdracht uit om ervoor te zorgen dat alle geo-locaties compatibel zijn:</span><span class="sxs-lookup"><span data-stu-id="271d2-141">To ensure that all geo locations are compatible, run:</span></span>

`Get-SPOGeoMoveCrossCompatibilityStatus`

<span data-ttu-id="271d2-142">U ziet een lijst met uw geografische locaties en u kunt de inhoud van de geografische locaties verplaatsten, ongeacht of deze wordt aangeduid als compatibel.</span><span class="sxs-lookup"><span data-stu-id="271d2-142">You will see a list of your geo locations and whether content can be moved between will be denoted as "Compatible".</span></span> <span data-ttu-id="271d2-143">Als met de opdracht ' niet-compatibel ' is geretourneerd, probeert u de status op een later tijdstip te valideren.</span><span class="sxs-lookup"><span data-stu-id="271d2-143">If the command returns "Incompatible" please retry validating the status at a later date.</span></span>

<span data-ttu-id="271d2-144">Als een OneDrive een subsite bevat, kunt u deze bijvoorbeeld niet verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="271d2-144">If a OneDrive contains a subsite, for example, it cannot be moved.</span></span> <span data-ttu-id="271d2-145">U kunt de cmdlet start-SPOUserAndContentMove gebruiken met de parameter-ValidationOnly om te controleren of de OneDrive kan worden verplaatst:</span><span class="sxs-lookup"><span data-stu-id="271d2-145">You can use the Start-SPOUserAndContentMove cmdlet with the -ValidationOnly parameter to validate if the OneDrive is able to be moved:</span></span>

`Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly`

<span data-ttu-id="271d2-146">Hierdoor wordt het resultaat weergegeven als de OneDrive klaar is om te worden verplaatst of als er een fout is opgetreden als de verhuizing niet kan worden verplaatst.</span><span class="sxs-lookup"><span data-stu-id="271d2-146">This will return Success if the OneDrive is ready to be moved or Fail if there is a legal hold or subsite that would prevent the move.</span></span> <span data-ttu-id="271d2-147">Nadat u hebt gecontroleerd of de OneDrive klaar is om te worden verplaatst, kunt u beginnen met verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="271d2-147">Once you have validated that the OneDrive is ready to move, you can start the move.</span></span>

## <a name="start-a-onedrive-geo-move"></a><span data-ttu-id="271d2-148">Een geografische verhuizing van OneDrive starten</span><span class="sxs-lookup"><span data-stu-id="271d2-148">Start a OneDrive geo move</span></span>

<span data-ttu-id="271d2-149">Voer de volgende opdracht uit om de verhuizing te starten:</span><span class="sxs-lookup"><span data-stu-id="271d2-149">To start the move, run:</span></span>  

`Start-SPOUserAndContentMove -UserPrincipalName <UserPrincipalName> -DestinationDataLocation <DestinationDataLocation>`

<span data-ttu-id="271d2-150">Met deze parameters:</span><span class="sxs-lookup"><span data-stu-id="271d2-150">Using these parameters:</span></span>

-   <span data-ttu-id="271d2-151">_UserPrincipalName_ : UPN van de gebruiker van wie OneDrive wordt verplaatst.</span><span class="sxs-lookup"><span data-stu-id="271d2-151">_UserPrincipalName_ – UPN of the user whose OneDrive is being moved.</span></span>

-   <span data-ttu-id="271d2-152">_DestinationDataLocation_ – geografische locatie waar de OneDrive moet worden verplaatst.</span><span class="sxs-lookup"><span data-stu-id="271d2-152">_DestinationDataLocation_ – Geo-Location where the OneDrive needs to be moved.</span></span> <span data-ttu-id="271d2-153">Dit moet gelijk zijn aan de voorkeur van de gebruikerslocatie van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="271d2-153">This should be same as the user's preferred data location.</span></span>

<span data-ttu-id="271d2-154">Als u bijvoorbeeld de OneDrive van matt@contosoenergy.onmicrosoft.com van EUR naar AUS wilt verplaatsen, voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="271d2-154">For example, to move the OneDrive of matt@contosoenergy.onmicrosoft.com from EUR to AUS, run:</span></span>

`Start-SPOUserAndContentMove -UserPrincipalName matt@contosoenergy.onmicrosoft.com -DestinationDataLocation AUS`

![Schermafbeelding van het PowerShell-venster met de cmdlet start-SPOUserAndContentMove](../media/move-onedrive-between-geo-locations-image2.png)

<span data-ttu-id="271d2-156">Gebruik een van de volgende parameters als u een geo-overstap voor een later tijdstip wilt plannen:</span><span class="sxs-lookup"><span data-stu-id="271d2-156">To schedule a geo move for a later time, use one of the following parameters:</span></span>

-   <span data-ttu-id="271d2-157">_PreferredMoveBeginDate_ : de verhuizing gaat waarschijnlijk op deze specifieke tijd.</span><span class="sxs-lookup"><span data-stu-id="271d2-157">_PreferredMoveBeginDate_ – The move will likely begin at this specified time.</span></span> <span data-ttu-id="271d2-158">De tijd moet zijn opgegeven in Coordinated Universal Time (UTC).</span><span class="sxs-lookup"><span data-stu-id="271d2-158">Time must be specified in Coordinated Universal Time (UTC).</span></span>

-   <span data-ttu-id="271d2-159">_PreferredMoveEndDate_ : de verhuizing wordt waarschijnlijk op basis van de opgegeven tijd voltooid.</span><span class="sxs-lookup"><span data-stu-id="271d2-159">_PreferredMoveEndDate_ – The move will likely be completed by this specified time, on a best effort basis.</span></span> <span data-ttu-id="271d2-160">De tijd moet zijn opgegeven in Coordinated Universal Time (UTC).</span><span class="sxs-lookup"><span data-stu-id="271d2-160">Time must be specified in Coordinated Universal Time (UTC).</span></span> 

## <a name="cancel-a-onedrive-geo-move"></a><span data-ttu-id="271d2-161">Een geo-verhuizing van OneDrive opzeggen</span><span class="sxs-lookup"><span data-stu-id="271d2-161">Cancel a OneDrive geo move</span></span> 

<span data-ttu-id="271d2-162">U kunt de geografische verplaatsing van een OneDrive van een gebruiker stoppen, mits de overstap niet wordt uitgevoerd of voltooid met behulp van de cmdlet:</span><span class="sxs-lookup"><span data-stu-id="271d2-162">You can stop the geo move of a user's OneDrive, provided the move is not in progress or completed by using the cmdlet:</span></span>

`Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>`

<span data-ttu-id="271d2-163">Waarbij _userPrincipalName_ de UPN is van de gebruiker van wie u de OneDrive-verplaatsing wilt stoppen.</span><span class="sxs-lookup"><span data-stu-id="271d2-163">Where _UserPrincipalName_ is the UPN of the user whose OneDrive move you want to stop.</span></span>

## <a name="determining-current-status"></a><span data-ttu-id="271d2-164">De huidige status bepalen</span><span class="sxs-lookup"><span data-stu-id="271d2-164">Determining current status</span></span>

<span data-ttu-id="271d2-165">Met de cmdlet Get-SPOUserAndContentMoveState kunt u de status van een OneDrive-geografische plaats in-of uitzetten.</span><span class="sxs-lookup"><span data-stu-id="271d2-165">You can check the status of a OneDrive geo move in or out of the geo that you're connected to by using the Get-SPOUserAndContentMoveState cmdlet.</span></span>

<span data-ttu-id="271d2-166">De verplaatsings status wordt beschreven in de volgende tabel.</span><span class="sxs-lookup"><span data-stu-id="271d2-166">The move statuses are described in the following table.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="271d2-167"><strong>Status</strong></span><span class="sxs-lookup"><span data-stu-id="271d2-167"><strong>Status</strong></span></span></th>
<th align="left"><span data-ttu-id="271d2-168"><strong>Beschrijving</strong></span><span class="sxs-lookup"><span data-stu-id="271d2-168"><strong>Description</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="271d2-169">NotStarted</span><span class="sxs-lookup"><span data-stu-id="271d2-169">NotStarted</span></span></td>
<td align="left"><span data-ttu-id="271d2-170">De verhuizing is niet gestart.</span><span class="sxs-lookup"><span data-stu-id="271d2-170">The move has not started.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="271d2-171">Invoortgang (<em>n</em>/4)</span><span class="sxs-lookup"><span data-stu-id="271d2-171">InProgress (<em>n</em>/4)</span></span></td>
<td align="left"><span data-ttu-id="271d2-172">De verplaatsing wordt uitgevoerd in een van de volgende staten: validering (1/4), back-up (2/4), herstellen (3/4), opruimen (4/4).</span><span class="sxs-lookup"><span data-stu-id="271d2-172">The move is in progress in one of the following states: Validation (1/4), Backup (2/4), Restore (3/4), Cleanup (4/4).</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="271d2-173">Bevestiging</span><span class="sxs-lookup"><span data-stu-id="271d2-173">Success</span></span></td>
<td align="left"><span data-ttu-id="271d2-174">De verhuizing is voltooid.</span><span class="sxs-lookup"><span data-stu-id="271d2-174">The move has completed successfully.</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="271d2-175">Mislukt</span><span class="sxs-lookup"><span data-stu-id="271d2-175">Failed</span></span></td>
<td align="left"><span data-ttu-id="271d2-176">Verplaatsen mislukt.</span><span class="sxs-lookup"><span data-stu-id="271d2-176">The move failed.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="271d2-177">Als u de status van de verhuizing van een bepaalde gebruiker wilt achterhalen, gebruikt u de parameter UserPrincipalName:</span><span class="sxs-lookup"><span data-stu-id="271d2-177">To find the status of a specific user's move, use the UserPrincipalName parameter:</span></span>

`Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>`

<span data-ttu-id="271d2-178">Gebruik de parameter MoveState met een van de volgende waarden als u wilt weten hoe u de status van alle in-en uitnodigingen van de geografische locatie waarmee u bent verbonden wilt achterhalen.</span><span class="sxs-lookup"><span data-stu-id="271d2-178">To find the status of all of the moves in or out of the geo location that you're connected to, use the MoveState parameter with one of the following values: NotStarted, InProgress, Success, Failed, All.</span></span>

`Get-SPOUserAndContentMoveState -MoveState <value>`

<span data-ttu-id="271d2-179">U kunt ook de `-Verbose` parameter toevoegen voor uitgebreide beschrijvingen van de verplaatsings status.</span><span class="sxs-lookup"><span data-stu-id="271d2-179">You can also add the `-Verbose` parameter for more verbose descriptions of the move state.</span></span>

## <a name="user-experience"></a><span data-ttu-id="271d2-180">Gebruikerservaring</span><span class="sxs-lookup"><span data-stu-id="271d2-180">User Experience</span></span>

<span data-ttu-id="271d2-181">Gebruikers van OneDrive moeten minimaal verstoren als hun OneDrive naar een andere geografische locatie wordt verplaatst.</span><span class="sxs-lookup"><span data-stu-id="271d2-181">Users of OneDrive should notice minimal disruption if their OneDrive is moved to a different geo location.</span></span> <span data-ttu-id="271d2-182">Als u tijdens de verhuizing een kortere alleen-lezen status wilt hebben, blijven bestaande koppelingen en machtigingen op de verwachte manier werken als de verplaatsing is voltooid.</span><span class="sxs-lookup"><span data-stu-id="271d2-182">Aside from a brief read-only state during the move, existing links and permissions will continue to work as expected once the move is completed.</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="271d2-183">OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="271d2-183">OneDrive for Business</span></span>

<span data-ttu-id="271d2-184">Terwijl de overstap wordt uitgevoerd, wordt de OneDrive van de gebruiker ingesteld op alleen-lezen.</span><span class="sxs-lookup"><span data-stu-id="271d2-184">While the move is in progress the user's OneDrive is set to read-only.</span></span> <span data-ttu-id="271d2-185">Wanneer de overstap is voltooid, wordt de gebruiker doorgestuurd naar zijn of haar OneDrive op de nieuwe geo-locatie wanneer ze naar OneDrive navigeren in het startprogramma voor Microsoft 365-apps of een webbrowser.</span><span class="sxs-lookup"><span data-stu-id="271d2-185">Once the move is completed, the user is directed to their OneDrive in the new geo location when they navigate to OneDrive the Microsoft 365 app launcher or a web browser.</span></span>

### <a name="permissions-on-onedrive-content"></a><span data-ttu-id="271d2-186">Machtigingen voor OneDrive-inhoud</span><span class="sxs-lookup"><span data-stu-id="271d2-186">Permissions on OneDrive content</span></span>

<span data-ttu-id="271d2-187">Gebruikers met machtigingen voor OneDrive-inhoud blijven toegang tot de inhoud tijdens de verhuizing en nadat deze is voltooid.</span><span class="sxs-lookup"><span data-stu-id="271d2-187">Users with permissions to OneDrive content will continue to have access to the content during the move and after it's complete.</span></span>

### <a name="onedrive-sync-client"></a><span data-ttu-id="271d2-188">OneDrive-Synchronisatieclient</span><span class="sxs-lookup"><span data-stu-id="271d2-188">OneDrive Sync Client</span></span> 

<span data-ttu-id="271d2-189">Met de synchronisatieclient van OneDrive wordt automatisch het synchroniseren van synchronisatie naar de nieuwe OneDrive-locatie herkend en naadloos overgebracht nadat de geo-verplaatsing van OneDrive is voltooid.</span><span class="sxs-lookup"><span data-stu-id="271d2-189">The OneDrive sync client will automatically detect and seamlessly transfer syncing to the new OneDrive location once the OneDrive geo move is complete.</span></span> <span data-ttu-id="271d2-190">De gebruiker hoeft zich niet opnieuw aan te melden of een andere actie te ondernemen.</span><span class="sxs-lookup"><span data-stu-id="271d2-190">The user does not need to sign-in again or take any other action.</span></span>  <span data-ttu-id="271d2-191">(Versie 17.3.6943.0625 of hoger van de synchronisatieclient vereist.)</span><span class="sxs-lookup"><span data-stu-id="271d2-191">(Version 17.3.6943.0625 or later of the sync client required.)</span></span>

<span data-ttu-id="271d2-192">Als een gebruiker een bestand bijwerkt terwijl de geo-verhuizing van OneDrive wordt uitgevoerd, wordt door de synchronisatieclient aangegeven dat het uploaden van bestanden in behandeling is terwijl de verhuizing plaatsvindt.</span><span class="sxs-lookup"><span data-stu-id="271d2-192">If a user updates a file while the OneDrive geo move is in progress, the sync client will notify them that file uploads are pending while the move is underway.</span></span>

### <a name="sharing-links"></a><span data-ttu-id="271d2-193">Koppelingen voordelen</span><span class="sxs-lookup"><span data-stu-id="271d2-193">Sharing links</span></span> 

<span data-ttu-id="271d2-194">Na voltooiing van OneDrive geo-verhuizing worden de bestaande gedeelde koppelingen voor de bestanden die zijn verplaatst automatisch omgeleid naar de nieuwe geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="271d2-194">Upon OneDrive geo move completion, the existing shared links for the files that were moved will automatically redirect to the new geo location.</span></span>

### <a name="onenote-experience"></a><span data-ttu-id="271d2-195">OneNote-ervaring</span><span class="sxs-lookup"><span data-stu-id="271d2-195">OneNote Experience</span></span> 

<span data-ttu-id="271d2-196">Met de apps van OneNote Win32 client en UWP (Universal) wordt automatisch notitieblokken automatisch opgespoord en naadloos gesynchroniseerd met de nieuwe OneDrive-locatie nadat OneDrive geo Move is voltooid.</span><span class="sxs-lookup"><span data-stu-id="271d2-196">OneNote win32 client and UWP (Universal) App will automatically detect and seamlessly sync notebooks to the new OneDrive location once OneDrive geo move is complete.</span></span> <span data-ttu-id="271d2-197">De gebruiker hoeft zich niet opnieuw aan te melden of een andere actie te ondernemen.</span><span class="sxs-lookup"><span data-stu-id="271d2-197">The user does not need to sign-in again or take any other action.</span></span> <span data-ttu-id="271d2-198">De enige zichtbare indicator voor de gebruiker is het synchroniseren van notitieblokken mislukt wanneer OneDrive geo-verplaatsing wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="271d2-198">The only visible indicator to the user is notebook sync would fail when OneDrive geo move is in progress.</span></span> <span data-ttu-id="271d2-199">Deze ervaring is beschikbaar in de volgende versies van OneNote-clients:</span><span class="sxs-lookup"><span data-stu-id="271d2-199">This experience is available on the following OneNote client versions:</span></span>

-   <span data-ttu-id="271d2-200">OneNote Win32-versie 16.0.8326.2096 (en later)</span><span class="sxs-lookup"><span data-stu-id="271d2-200">OneNote win32 – Version 16.0.8326.2096 (and later)</span></span>

-   <span data-ttu-id="271d2-201">OneNote UWP: versie 16.0.8431.1006 (en later)</span><span class="sxs-lookup"><span data-stu-id="271d2-201">OneNote UWP – Version 16.0.8431.1006 (and later)</span></span>

-   <span data-ttu-id="271d2-202">App OneNote Mobile: versie 16.0.8431.1011 (en later)</span><span class="sxs-lookup"><span data-stu-id="271d2-202">OneNote Mobile App – Version 16.0.8431.1011 (and later)</span></span>

### <a name="teams-app"></a><span data-ttu-id="271d2-203">Teams-app</span><span class="sxs-lookup"><span data-stu-id="271d2-203">Teams app</span></span>

<span data-ttu-id="271d2-204">Na voltooiing van OneDrive geo-verhuizing hebben gebruikers toegang tot hun OneDrive-bestanden in de app teams.</span><span class="sxs-lookup"><span data-stu-id="271d2-204">Upon OneDrive geo move completion, users will have access to their OneDrive files on the Teams app.</span></span> <span data-ttu-id="271d2-205">Bestanden die worden gedeeld via teams-chat vanuit hun OneDrive voordat u geo-overstap gaat, blijven ook werken na voltooiing van de verhuizing.</span><span class="sxs-lookup"><span data-stu-id="271d2-205">Additionally, files shared via Teams chat from their OneDrive prior to geo move will continue to work after move is complete.</span></span>

### <a name="onedrive-for-business-mobile-app-ios"></a><span data-ttu-id="271d2-206">Mobiele app van OneDrive voor bedrijven (iOS)</span><span class="sxs-lookup"><span data-stu-id="271d2-206">OneDrive for Business Mobile App (iOS)</span></span> 

<span data-ttu-id="271d2-207">Na voltooiing van OneDrive geo-verhuizing moet de gebruiker zich afmelden en opnieuw aanmelden op de mobiele iOS-app om te synchroniseren met de nieuwe OneDrive-locatie.</span><span class="sxs-lookup"><span data-stu-id="271d2-207">Upon OneDrive geo move completion, the user would need to sign out and sign in again on the iOS Mobile App to sync to the new OneDrive location.</span></span>

### <a name="existing-followed-groups-and-sites"></a><span data-ttu-id="271d2-208">Bestaande gevolgde groepen en sites</span><span class="sxs-lookup"><span data-stu-id="271d2-208">Existing followed groups and sites</span></span>

<span data-ttu-id="271d2-209">Gevolgde sites en groepen worden weergegeven in het OneDrive van de gebruiker, ongeacht de geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="271d2-209">Followed sites and groups will show up in the user's OneDrive regardless of their geo location.</span></span> <span data-ttu-id="271d2-210">Sites en groepen die worden gehost op een andere geografische locatie, worden geopend op een apart tabblad.</span><span class="sxs-lookup"><span data-stu-id="271d2-210">Sites and groups hosted in another geo location will open in a separate tab.</span></span>

### <a name="delve-geo-url-updates"></a><span data-ttu-id="271d2-211">Geo-URL'S bijwerken in Delve</span><span class="sxs-lookup"><span data-stu-id="271d2-211">Delve Geo URL updates</span></span>

<span data-ttu-id="271d2-212">Gebruikers worden alleen naar de Delve-geo verzonden die overeenkomen met hun PDL, wanneer hun OneDrive naar de nieuwe geo is verplaatst.</span><span class="sxs-lookup"><span data-stu-id="271d2-212">Users will be sent to the Delve geo corresponding to their PDL only after their OneDrive has been moved to the new geo.</span></span>
