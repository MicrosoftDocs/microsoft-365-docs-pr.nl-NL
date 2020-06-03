---
title: Valse positieven of false negatives melden in geautomatiseerd onderzoek en reactie van Office 365
description: Is er iets gemist of ten onrechte gedetecteerd door Office 365 Advanced Threat Protection? Meer informatie over het indienen van false positives of false negatives bij Microsoft voor analyse.
keywords: geautomatiseerd, onderzoek, alert, trigger, actie, sanering, vals positief, vals negatief
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 05/15/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 837232550ca392a364b9842f64a1c3f0d790a502
ms.sourcegitcommit: 33be6075fcc89d4c0a48fa7e59f3b3ebc605d9f3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/03/2020
ms.locfileid: "44520156"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="f0b99-105">Valse positieven/negatieven rapporteren in geautomatiseerde onderzoeks- en reactiemogelijkheden</span><span class="sxs-lookup"><span data-stu-id="f0b99-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="f0b99-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f0b99-106">**Applies to:**</span></span>
- <span data-ttu-id="f0b99-107">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f0b99-107">Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="f0b99-108">Hebben [geautomatiseerde mogelijkheden voor onderzoek en respons (AIR) in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) iets gemist of ten onrechte gedetecteerd?</span><span class="sxs-lookup"><span data-stu-id="f0b99-108">Did [automated investigation and response (AIR) capabilities in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) miss or wrongly detect something?</span></span> <span data-ttu-id="f0b99-109">Er zijn stappen die u nemen om het te repareren.</span><span class="sxs-lookup"><span data-stu-id="f0b99-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="f0b99-110">U kunt:</span><span class="sxs-lookup"><span data-stu-id="f0b99-110">You can:</span></span>
- <span data-ttu-id="f0b99-111">[Een false positive/negatief melden aan Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="f0b99-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="f0b99-112">[Pas uw waarschuwingen](#adjust-an-alert-to-prevent-false-positives-from-recurring) aan (indien nodig); En</span><span class="sxs-lookup"><span data-stu-id="f0b99-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="f0b99-113">[Herstelacties ongedaan maken die zijn uitgevoerd](#undo-a-remediation-action).</span><span class="sxs-lookup"><span data-stu-id="f0b99-113">[Undo remediation actions that were taken](#undo-a-remediation-action).</span></span> 

<span data-ttu-id="f0b99-114">Gebruik dit artikel als een gids.</span><span class="sxs-lookup"><span data-stu-id="f0b99-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="f0b99-115">Een false positive/negatief melden aan Microsoft voor analyse</span><span class="sxs-lookup"><span data-stu-id="f0b99-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="f0b99-116">Als Office 365 AIR een e-mailbericht, een e-mailbijlage, een URL in een e-mailbericht of een URL in een Office-bestand heeft gemist, u [vermoedelijke spam, phish, URL's en bestanden verzenden naar Microsoft voor office 365-scanning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span><span class="sxs-lookup"><span data-stu-id="f0b99-116">If Office 365 AIR missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span></span>

<span data-ttu-id="f0b99-117">U ook [een bestand indienen bij Microsoft voor malware-analyse.](https://www.microsoft.com/wdsi/filesubmission)</span><span class="sxs-lookup"><span data-stu-id="f0b99-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="f0b99-118">Een waarschuwing aanpassen om te voorkomen dat false positives zich herhalen</span><span class="sxs-lookup"><span data-stu-id="f0b99-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="f0b99-119">Als een waarschuwing wordt geactiveerd door legitiem gebruik of als de waarschuwing onjuist is, u [waarschuwingen beheren in de Cloud App Security-portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span><span class="sxs-lookup"><span data-stu-id="f0b99-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="f0b99-120">Als uw organisatie naast Office 365 [ook Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) gebruikt en een bestand, IP-adres, URL of domein wordt behandeld als malware op een apparaat, ook al is het veilig, u een aangepaste indicator maken met een actie ['Toestaan' voor uw apparaat.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="f0b99-120">If your organization is using [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="f0b99-121">Een herstelactie ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="f0b99-121">Undo a remediation action</span></span>

<span data-ttu-id="f0b99-122">In de meeste gevallen kan uw beveiligingsteam de herstelactie ongedaan maken als er een herstelactie is ondernomen op een e-mailbericht, e-mailbijlage of URL en het item eigenlijk geen bedreiging vormt, dan kan uw beveiligingsteam de herstelactie ongedaan maken en stappen ondernemen om te voorkomen dat het fout-positieve zich opnieuw voordoet.</span><span class="sxs-lookup"><span data-stu-id="f0b99-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="f0b99-123">U [Threat Explorer](#undo-an-action-using-threat-explorer) of het tabblad Acties gebruiken [voor een onderzoek](#undo-an-action-using-the-actions-tab-for-an-investigation) om een actie ongedaan te maken.</span><span class="sxs-lookup"><span data-stu-id="f0b99-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-using-the-actions-tab-for-an-investigation) to undo an action.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="f0b99-124">Zorg ervoor dat u over de benodigde machtigingen beschikt voordat u de volgende taken probeert uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="f0b99-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="f0b99-125">Een actie ongedaan maken met Threat Explorer</span><span class="sxs-lookup"><span data-stu-id="f0b99-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="f0b99-126">Met Threat Explorer kan uw beveiligingsteam een e-mail vinden die door een actie is beïnvloed en de actie mogelijk ongedaan maken.</span><span class="sxs-lookup"><span data-stu-id="f0b99-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="f0b99-127">Scenario</span><span class="sxs-lookup"><span data-stu-id="f0b99-127">Scenario</span></span>  |<span data-ttu-id="f0b99-128">Ongedaan maken Opties</span><span class="sxs-lookup"><span data-stu-id="f0b99-128">Undo Options</span></span>  |<span data-ttu-id="f0b99-129">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="f0b99-129">Learn more</span></span> |
|---------|---------|---------|
|<span data-ttu-id="f0b99-130">Een e-mailbericht is doorgestuurd naar de map Ongewenste e-mail van een gebruiker</span><span class="sxs-lookup"><span data-stu-id="f0b99-130">An email message was routed to a user's Junk Email folder</span></span>     |<span data-ttu-id="f0b99-131">- Het bericht verplaatsen naar de map Verwijderde items van de gebruiker</span><span class="sxs-lookup"><span data-stu-id="f0b99-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="f0b99-132">- Het bericht verplaatsen naar het Postvak IN van de gebruiker</span><span class="sxs-lookup"><span data-stu-id="f0b99-132">- Move the message to the user's Inbox</span></span> <br/><span data-ttu-id="f0b99-133">- Het bericht verwijderen</span><span class="sxs-lookup"><span data-stu-id="f0b99-133">- Delete the message</span></span>          |[<span data-ttu-id="f0b99-134">Schadelijke e-mail zoeken en onderzoeken die is geleverd in Office 365</span><span class="sxs-lookup"><span data-stu-id="f0b99-134">Find and investigate malicious email that was delivered in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered) |
|<span data-ttu-id="f0b99-135">Een e-mailbericht of een bestand is in quarantaine geplaatst</span><span class="sxs-lookup"><span data-stu-id="f0b99-135">An email message or a file was quarantined</span></span>     |<span data-ttu-id="f0b99-136">- De e-mail of het bestand vrijgeven</span><span class="sxs-lookup"><span data-stu-id="f0b99-136">- Release the email or file</span></span> <br/><span data-ttu-id="f0b99-137">- De e-mail of het bestand verwijderen</span><span class="sxs-lookup"><span data-stu-id="f0b99-137">- Delete the email or file</span></span>         |[<span data-ttu-id="f0b99-138">Berichten en bestanden in quarantaine beheren als beheerder in Office 365</span><span class="sxs-lookup"><span data-stu-id="f0b99-138">Manage quarantined messages and files as an administrator in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files) |


### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a><span data-ttu-id="f0b99-139">Een actie ongedaan maken met het tabblad Handelingen voor een onderzoek</span><span class="sxs-lookup"><span data-stu-id="f0b99-139">Undo an action using the Actions tab for an investigation</span></span>

<span data-ttu-id="f0b99-140">In het Centrum van Het Actie u herstelacties zien die zijn uitgevoerd en de actie mogelijk ongedaan maken.</span><span class="sxs-lookup"><span data-stu-id="f0b99-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="f0b99-141">Ga naar [https://protection.office.com](https://protection.office.com) en meld je aan.</span><span class="sxs-lookup"><span data-stu-id="f0b99-141">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="f0b99-142">Dit brengt u naar het Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="f0b99-142">This takes you to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="f0b99-143">Ga naar **Threat management**  >  **Investigations**.</span><span class="sxs-lookup"><span data-stu-id="f0b99-143">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="f0b99-144">Selecteer in de lijst met onderzoeken het pictogram **Openen in een nieuw venster** naast de id van een item.</span><span class="sxs-lookup"><span data-stu-id="f0b99-144">In the list of investigations, select the **Open in new window** icon next to an item's ID.</span></span>

4. <span data-ttu-id="f0b99-145">Selecteer het tabblad **Handelingen.**</span><span class="sxs-lookup"><span data-stu-id="f0b99-145">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="f0b99-146">Selecteer een item met de status **Voltooid**en zoek naar een koppeling, zoals **Goedgekeurd,** in de kolom **Besluit.**</span><span class="sxs-lookup"><span data-stu-id="f0b99-146">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decision** column.</span></span> <span data-ttu-id="f0b99-147">Dit opent een flyout met meer details over de actie.</span><span class="sxs-lookup"><span data-stu-id="f0b99-147">This opens a flyout with more details about the action.</span></span>

6. <span data-ttu-id="f0b99-148">Als u de actie ongedaan wilt maken, selecteert u **Herstel verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="f0b99-148">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f0b99-149">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="f0b99-149">Related articles</span></span>

[<span data-ttu-id="f0b99-150">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f0b99-150">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[<span data-ttu-id="f0b99-151">Aan de slag met Geautomatiseerd onderzoek en antwoord (AIR) in Office 365</span><span class="sxs-lookup"><span data-stu-id="f0b99-151">Get started using Automated investigation and response (AIR) in Office 365</span></span>](office-365-air.md)
