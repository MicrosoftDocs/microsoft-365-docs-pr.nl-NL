---
title: Onjuiste of onjuiste negatieven rapporteren na geautomatiseerd onderzoek in Microsoft Defender voor Office 365
description: Is er een fout opgetreden bij een gemiste of onjuiste detectie van de lucht in Microsoft Defender voor Office 365? Meer informatie over het indienen van onjuiste of onjuiste negatieven bij Microsoft voor analyse.
keywords: automatisch, onderzoek, waarschuwing, trigger, actie, herstellen, fout positief, negatief negatief
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-defender-office365
ms.topic: conceptual
ms.custom:
- autoir
ms.openlocfilehash: b9f037e3e6d798122b8d3c7ffd3476e34bd5a76b
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48411960"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="cf4ce-105">Onjuiste positief en negatief rapporteren in automatisch onderzoek en antwoord mogelijkheden</span><span class="sxs-lookup"><span data-stu-id="cf4ce-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="cf4ce-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="cf4ce-106">**Applies to:**</span></span>
- <span data-ttu-id="cf4ce-107">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="cf4ce-107">Microsoft Defender for Office 365</span></span>

<span data-ttu-id="cf4ce-108">Is er [geautomatiseerd onderzoek-en antwoord mogelijkheden in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) mis of er is iets misgegaan?</span><span class="sxs-lookup"><span data-stu-id="cf4ce-108">Did [automated investigation and response (AIR) capabilities in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) miss or wrongly detect something?</span></span> <span data-ttu-id="cf4ce-109">Er zijn stappen die u kunt uitvoeren om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="cf4ce-110">U kunt:</span><span class="sxs-lookup"><span data-stu-id="cf4ce-110">You can:</span></span>
- <span data-ttu-id="cf4ce-111">[Meld een fout-positief/negatief aan Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="cf4ce-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="cf4ce-112">[Pas uw meldingen](#adjust-an-alert-to-prevent-false-positives-from-recurring) aan (indien nodig). en</span><span class="sxs-lookup"><span data-stu-id="cf4ce-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="cf4ce-113">[Herstelbewerkingen die zijn uitgevoerd, ongedaan maken](#undo-a-remediation-action).</span><span class="sxs-lookup"><span data-stu-id="cf4ce-113">[Undo remediation actions that were taken](#undo-a-remediation-action).</span></span> 

<span data-ttu-id="cf4ce-114">Gebruik dit artikel als leidraad.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="cf4ce-115">Meld een fout-positief/negatief aan Microsoft voor analyse</span><span class="sxs-lookup"><span data-stu-id="cf4ce-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="cf4ce-116">Als AIR in Microsoft Defender for Office 365 een e-mailbericht, een e-mailbijlage, een URL in een e-mailbericht of een URL in een Office-bestand heeft gemist, kunt u [verdachte spam, phishing, url's en bestanden verzenden naar Microsoft Office 365 scan](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span><span class="sxs-lookup"><span data-stu-id="cf4ce-116">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span></span>

<span data-ttu-id="cf4ce-117">U kunt ook [een bestand bij Microsoft indienen voor de analyse van malware](https://www.microsoft.com/wdsi/filesubmission).</span><span class="sxs-lookup"><span data-stu-id="cf4ce-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="cf4ce-118">Een waarschuwing aanpassen om fout-positieven van herhaling te voorkomen</span><span class="sxs-lookup"><span data-stu-id="cf4ce-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="cf4ce-119">Als een waarschuwing wordt geactiveerd door legitiem gebruik of als de waarschuwing onjuist is, kunt u [waarschuwingen beheren in de portal van de Cloud-app](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span><span class="sxs-lookup"><span data-stu-id="cf4ce-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="cf4ce-120">Als uw organisatie [Microsoft Defender voor eind 365 punt](https://docs.microsoft.com/windows/security/threat-protection) gebruikt, en een bestand, IP-adres, URL of domein wordt behandeld als malware op een apparaat, ook als dit veilig is, kunt u [een aangepaste indicator maken met een actie toestaan voor uw apparaat](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span><span class="sxs-lookup"><span data-stu-id="cf4ce-120">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="cf4ce-121">Een herstelactie ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="cf4ce-121">Undo a remediation action</span></span>

<span data-ttu-id="cf4ce-122">In de meeste gevallen geldt dat als een herstelactie is ondernomen voor een e-mailbericht, e-mailbijlage of URL, en het item eigenlijk geen bedreiging is, kan uw beveiligingsteam de actie ongedaan maken en stappen uitvoeren om te voorkomen dat de fout iets positief is.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="cf4ce-123">U kunt met behulp van de optie [bedreigingen](#undo-an-action-using-threat-explorer) en het [tabblad acties](#undo-an-action-using-the-actions-tab-for-an-investigation) een actie ongedaan maken.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-using-the-actions-tab-for-an-investigation) to undo an action.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="cf4ce-124">Zorg ervoor dat u over de benodigde machtigingen beschikt voordat u probeert de volgende taken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="cf4ce-125">Een actie ongedaan maken met de bedreigings Verkenner</span><span class="sxs-lookup"><span data-stu-id="cf4ce-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="cf4ce-126">Met de bedreigings Verkenner kan uw beveiligingsteam een e-mailbericht vinden dat wordt beïnvloed door een actie en mogelijk de actie ongedaan gemaakt.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

****

|<span data-ttu-id="cf4ce-127">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="cf4ce-127">Scenario</span></span>|<span data-ttu-id="cf4ce-128">Opties voor ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="cf4ce-128">Undo Options</span></span>|<span data-ttu-id="cf4ce-129">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="cf4ce-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="cf4ce-130">Een e-mailbericht is doorgestuurd naar de map Ongewenste E-mail van een gebruiker</span><span class="sxs-lookup"><span data-stu-id="cf4ce-130">An email message was routed to a user's Junk Email folder</span></span>|<span data-ttu-id="cf4ce-131">-Verplaats het bericht naar de map Verwijderde items van de gebruiker</span><span class="sxs-lookup"><span data-stu-id="cf4ce-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="cf4ce-132">-Verplaats het bericht naar het postvak in van de gebruiker</span><span class="sxs-lookup"><span data-stu-id="cf4ce-132">- Move the message to the user's Inbox</span></span> <br/><span data-ttu-id="cf4ce-133">-Verwijder het bericht</span><span class="sxs-lookup"><span data-stu-id="cf4ce-133">- Delete the message</span></span>|[<span data-ttu-id="cf4ce-134">Schadelijke e-mail zoeken en onderzoeken die is bezorgd in Office 365</span><span class="sxs-lookup"><span data-stu-id="cf4ce-134">Find and investigate malicious email that was delivered in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered)|
|<span data-ttu-id="cf4ce-135">Een e-mailbericht of een bestand is in quarantaine geplaatst</span><span class="sxs-lookup"><span data-stu-id="cf4ce-135">An email message or a file was quarantined</span></span>|<span data-ttu-id="cf4ce-136">-De e-mail of het bestand vrijgeven</span><span class="sxs-lookup"><span data-stu-id="cf4ce-136">- Release the email or file</span></span> <br/><span data-ttu-id="cf4ce-137">-De e-mail of het bestand verwijderen</span><span class="sxs-lookup"><span data-stu-id="cf4ce-137">- Delete the email or file</span></span>|[<span data-ttu-id="cf4ce-138">Geplaatste berichten en bestanden in een beheerder in Office 365 beheren</span><span class="sxs-lookup"><span data-stu-id="cf4ce-138">Manage quarantined messages and files as an administrator in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files)|
|

### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a><span data-ttu-id="cf4ce-139">Een bewerking ongedaan maken via het tabblad acties voor een onderzoek</span><span class="sxs-lookup"><span data-stu-id="cf4ce-139">Undo an action using the Actions tab for an investigation</span></span>

<span data-ttu-id="cf4ce-140">In het Actiecentrum ziet u de acties die u kunt uitvoeren om de actie te herstellen.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="cf4ce-141">Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-141">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="cf4ce-142">U gaat nu naar de beveiligings & compliance Center.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-142">This takes you to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="cf4ce-143">Ga naar onderzoek voor **Threat Management**  >  **Investigations**.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-143">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="cf4ce-144">Selecteer in de lijst met onderzoek het pictogram **openen in nieuw venster** naast de id van het item.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-144">In the list of investigations, select the **Open in new window** icon next to an item's ID.</span></span>

4. <span data-ttu-id="cf4ce-145">Selecteer het tabblad **acties** .</span><span class="sxs-lookup"><span data-stu-id="cf4ce-145">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="cf4ce-146">Selecteer een item met de status **voltooid**en zoek een koppeling, zoals **goedgekeurd**, in de kolom **beslissing** .</span><span class="sxs-lookup"><span data-stu-id="cf4ce-146">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decision** column.</span></span> <span data-ttu-id="cf4ce-147">Er wordt een flyout geopend met meer informatie over de actie.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-147">This opens a flyout with more details about the action.</span></span>

6. <span data-ttu-id="cf4ce-148">Als u de actie ongedaan wilt maken, selecteert u **herstel verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="cf4ce-148">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="cf4ce-149">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="cf4ce-149">Related articles</span></span>

[<span data-ttu-id="cf4ce-150">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="cf4ce-150">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[<span data-ttu-id="cf4ce-151">AIR in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="cf4ce-151">AIR in Microsoft Defender for Office 365</span></span>](office-365-air.md)
