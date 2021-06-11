---
title: Fout-positieven of onwaar negatieven melden na automatisch onderzoek in Microsoft Defender voor Office 365
description: Is er iets gemist of ten onrechte gedetecteerd door AIR in Microsoft Defender voor Office 365? Meer informatie over het indienen van fout-positieven of onwaar negatieven bij Microsoft voor analyse.
keywords: geautomatiseerd, onderzoek, waarschuwing, trigger, actie, herstel, onwaar positief, onwaar negatief
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
ms.prod: m365-security
ms.date: 01/29/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 287bd9cd4dda6ccb152e93908a409e036eab9cc7
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878878"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="37181-105">Fout-positieven/negatieven rapporteren in geautomatiseerde onderzoeks- en antwoordmogelijkheden</span><span class="sxs-lookup"><span data-stu-id="37181-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="37181-106">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="37181-106">**Applies to**</span></span>
- [<span data-ttu-id="37181-107">Abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="37181-107">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="37181-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37181-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="37181-109">Als de mogelijkheden voor automatisch onderzoek en antwoord [(AIR) in](automated-investigation-response-office.md) Office 365 of iets verkeerd zijn gedetecteerd, zijn er stappen die uw team voor beveiligingsbewerkingen kan ondernemen om dit op te lossen.</span><span class="sxs-lookup"><span data-stu-id="37181-109">If [automated investigation and response (AIR) capabilities in Office 365](automated-investigation-response-office.md) missed or wrongly detected something, there are steps your security operations team can take to fix it.</span></span> <span data-ttu-id="37181-110">Dergelijke acties zijn onder andere:</span><span class="sxs-lookup"><span data-stu-id="37181-110">Such actions include:</span></span>

- <span data-ttu-id="37181-111">[Een onwaar positief/negatief melden bij Microsoft;](#report-a-false-positivenegative-to-microsoft-for-analysis)</span><span class="sxs-lookup"><span data-stu-id="37181-111">[Reporting a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="37181-112">[Waarschuwingen aanpassen](#adjust-an-alert-to-prevent-false-positives-from-recurring) (indien nodig); en</span><span class="sxs-lookup"><span data-stu-id="37181-112">[Adjusting alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span>
- <span data-ttu-id="37181-113">[Herstelacties ongedaan maken die zijn genomen.](#undo-a-remediation-action)</span><span class="sxs-lookup"><span data-stu-id="37181-113">[Undoing remediation actions that were taken](#undo-a-remediation-action).</span></span>

<span data-ttu-id="37181-114">Gebruik dit artikel als handleiding.</span><span class="sxs-lookup"><span data-stu-id="37181-114">Use this article as a guide.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="37181-115">Een onwaar positief/negatief melden bij Microsoft voor analyse</span><span class="sxs-lookup"><span data-stu-id="37181-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="37181-116">Als AIR in Microsoft Defender voor Office 365 een e-mailbericht, een e-mailbijlage, een URL in een e-mailbericht of een URL in een Office-bestand heeft gemist, kunt u verdachte [spam, phish, URL's](admin-submission.md)en bestanden indienen bij Microsoft voor Office 365 scannen.</span><span class="sxs-lookup"><span data-stu-id="37181-116">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](admin-submission.md).</span></span>

<span data-ttu-id="37181-117">U kunt ook [een bestand indienen bij Microsoft voor malwareanalyse.](https://www.microsoft.com/wdsi/filesubmission)</span><span class="sxs-lookup"><span data-stu-id="37181-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="37181-118">Een waarschuwing aanpassen om te voorkomen dat fout-positieven terugkeren</span><span class="sxs-lookup"><span data-stu-id="37181-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="37181-119">Als een waarschuwing wordt geactiveerd door legitiem gebruik of als de waarschuwing onjuist is, kunt u waarschuwingen beheren in de [Cloud App Security portal.](/cloud-app-security/managing-alerts)</span><span class="sxs-lookup"><span data-stu-id="37181-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="37181-120">Als uw organisatie naast Office 365 [Microsoft Defender](/windows/security/threat-protection) voor Eindpunt gebruikt en een bestand, IP-adres, URL of domein wordt beschouwd als malware op een apparaat, kunt u een aangepaste indicator maken met de actie Toestaan voor uw [apparaat.](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="37181-120">If your organization is using [Microsoft Defender for Endpoint](/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="37181-121">Een herstelactie ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="37181-121">Undo a remediation action</span></span>

<span data-ttu-id="37181-122">Als er in de meeste gevallen een herstelactie is uitgevoerd op een e-mailbericht, e-mailbijlage of URL en het item eigenlijk geen bedreiging is, kan uw beveiligingsteam de herstelactie ongedaan maken en stappen ondernemen om te voorkomen dat de fout-positieve zich opnieuw voordeed.</span><span class="sxs-lookup"><span data-stu-id="37181-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="37181-123">U kunt Threat [Explorer of het](#undo-an-action-using-threat-explorer) tabblad Acties gebruiken voor een onderzoek [om](#undo-an-action-in-the-action-center) een actie ongedaan te maken.</span><span class="sxs-lookup"><span data-stu-id="37181-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-in-the-action-center) to undo an action.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="37181-124">Zorg ervoor dat u de benodigde machtigingen hebt voordat u de volgende taken uitvoert.</span><span class="sxs-lookup"><span data-stu-id="37181-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="37181-125">Een actie ongedaan maken met Threat Explorer</span><span class="sxs-lookup"><span data-stu-id="37181-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="37181-126">Met Threat Explorer kan uw beveiligingsteam een e-mail vinden die is beïnvloed door een actie en de actie mogelijk ongedaan maken.</span><span class="sxs-lookup"><span data-stu-id="37181-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

<br>

****

|<span data-ttu-id="37181-127">Scenario</span><span class="sxs-lookup"><span data-stu-id="37181-127">Scenario</span></span>|<span data-ttu-id="37181-128">Opties voor ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="37181-128">Undo Options</span></span>|<span data-ttu-id="37181-129">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="37181-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="37181-130">Een e-mailbericht is doorgeleid naar de map Ongewenste e-mail van een gebruiker</span><span class="sxs-lookup"><span data-stu-id="37181-130">An email message was routed to a user's Junk Email folder</span></span>|<ul><li><span data-ttu-id="37181-131">Het bericht verplaatsen naar de map Verwijderde items van de gebruiker</span><span class="sxs-lookup"><span data-stu-id="37181-131">Move the message to the user's Deleted Items folder</span></span></li><li><span data-ttu-id="37181-132">Het bericht naar het Postvak IN van de gebruiker verplaatsen</span><span class="sxs-lookup"><span data-stu-id="37181-132">Move the message to the user's Inbox</span></span></li><li><span data-ttu-id="37181-133">Het bericht verwijderen</span><span class="sxs-lookup"><span data-stu-id="37181-133">Delete the message</span></span></li></ul>|[<span data-ttu-id="37181-134">Schadelijke e-mail zoeken en onderzoeken die is bezorgd in Office 365</span><span class="sxs-lookup"><span data-stu-id="37181-134">Find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)|
|<span data-ttu-id="37181-135">Een e-mailbericht of bestand is in quarantaine geplaatst</span><span class="sxs-lookup"><span data-stu-id="37181-135">An email message or a file was quarantined</span></span>|<ul><li><span data-ttu-id="37181-136">Het e-mailbericht of bestand vrijgeven</span><span class="sxs-lookup"><span data-stu-id="37181-136">Release the email or file</span></span></li><li> <span data-ttu-id="37181-137">Het e-mailbericht of bestand verwijderen</span><span class="sxs-lookup"><span data-stu-id="37181-137">Delete the email or file</span></span></li></ul>|[<span data-ttu-id="37181-138">Berichten in quarantaine beheren als beheerder</span><span class="sxs-lookup"><span data-stu-id="37181-138">Manage quarantined messages as an admin</span></span>](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a><span data-ttu-id="37181-139">Een actie ongedaan maken in het actiecentrum</span><span class="sxs-lookup"><span data-stu-id="37181-139">Undo an action in the Action center</span></span>

<span data-ttu-id="37181-140">In het Actiecentrum kunt u herstelacties zien die zijn ondernomen en de actie mogelijk ongedaan kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="37181-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="37181-141">Ga naar de Microsoft 365 Defender-portal <https://security.microsoft.com> ().</span><span class="sxs-lookup"><span data-stu-id="37181-141">Go to the Microsoft 365 Defender portal (<https://security.microsoft.com>).</span></span>
2. <span data-ttu-id="37181-142">Selecteer actiecentrum in het **navigatiedeelvenster.**</span><span class="sxs-lookup"><span data-stu-id="37181-142">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="37181-143">Selecteer het **tabblad Geschiedenis** om de lijst met voltooide acties te bekijken.</span><span class="sxs-lookup"><span data-stu-id="37181-143">Select the **History** tab to view the list of completed actions.</span></span>
4. <span data-ttu-id="37181-144">Selecteer een item.</span><span class="sxs-lookup"><span data-stu-id="37181-144">Select an item.</span></span> <span data-ttu-id="37181-145">Het deelvenster Flyout wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="37181-145">Its flyout pane opens.</span></span>
5. <span data-ttu-id="37181-146">Selecteer ongedaan maken in het deelvenster Flyout.</span><span class="sxs-lookup"><span data-stu-id="37181-146">In the flyout pane, select **Undo**.</span></span> <span data-ttu-id="37181-147">(Alleen acties die ongedaan kunnen worden gemaakt, hebben een **knop Ongedaan** maken.)</span><span class="sxs-lookup"><span data-stu-id="37181-147">(Only actions that can be undone will have an **Undo** button.)</span></span>

## <a name="see-also"></a><span data-ttu-id="37181-148">Zie ook</span><span class="sxs-lookup"><span data-stu-id="37181-148">See also</span></span>

- [<span data-ttu-id="37181-149">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="37181-149">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="37181-150">Automatische onderzoeken in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="37181-150">Automated investigations in Microsoft Defender for Office 365</span></span>](office-365-air.md)
