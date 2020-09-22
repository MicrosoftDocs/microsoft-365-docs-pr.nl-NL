---
title: Negatieve negatieve of onjuiste negatieven in lucht afhandelen in Microsoft Threat Protection
description: Is er iets misgegaan of heeft de verkeerde lucht gedetecteerd in Microsoft Threat Protection? Meer informatie over het indienen van onjuiste of onjuiste negatieven bij Microsoft voor analyse.
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
ms.date: 09/16/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: 84d2a71f715c31560f6376464bf9da25cc8d58b1
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198629"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="163d0-105">In-en uitzoomen op onjuiste positief en negatief onderzoek en antwoord mogelijkheden</span><span class="sxs-lookup"><span data-stu-id="163d0-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="163d0-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="163d0-106">**Applies to:**</span></span>
- <span data-ttu-id="163d0-107">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="163d0-107">Microsoft Threat Protection</span></span>

<span data-ttu-id="163d0-108">Is er [geautomatiseerd onderzoek-en antwoord mogelijkheden](mtp-autoir.md) in Microsoft Threat Protection, of er is iets misgegaan?</span><span class="sxs-lookup"><span data-stu-id="163d0-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="163d0-109">Er zijn stappen die u kunt uitvoeren om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="163d0-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="163d0-110">U kunt:</span><span class="sxs-lookup"><span data-stu-id="163d0-110">You can:</span></span>

- <span data-ttu-id="163d0-111">[Meld een fout-positief/negatief aan Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="163d0-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="163d0-112">[Pas uw meldingen](#adjust-an-alert-to-prevent-false-positives-from-recurring) aan (indien nodig). en</span><span class="sxs-lookup"><span data-stu-id="163d0-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="163d0-113">[Herstelacties die zijn uitgevoerd op apparaten ongedaan maken](#undo-a-remediation-action-that-was-taken-on-a-device).</span><span class="sxs-lookup"><span data-stu-id="163d0-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="163d0-114">Gebruik dit artikel als leidraad.</span><span class="sxs-lookup"><span data-stu-id="163d0-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="163d0-115">Meld een fout-positief/negatief aan Microsoft voor analyse</span><span class="sxs-lookup"><span data-stu-id="163d0-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="163d0-116">Item gemist of onjuist gedetecteerd</span><span class="sxs-lookup"><span data-stu-id="163d0-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="163d0-117">Service</span><span class="sxs-lookup"><span data-stu-id="163d0-117">Service</span></span>  |<span data-ttu-id="163d0-118">Wat moet u doen?</span><span class="sxs-lookup"><span data-stu-id="163d0-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="163d0-119">-E-mailbericht</span><span class="sxs-lookup"><span data-stu-id="163d0-119">- Email message</span></span> <br/><span data-ttu-id="163d0-120">-E-mailbijlage</span><span class="sxs-lookup"><span data-stu-id="163d0-120">- Email attachment</span></span> <br/><span data-ttu-id="163d0-121">-URL in een e-mailbericht</span><span class="sxs-lookup"><span data-stu-id="163d0-121">- URL in an email message</span></span><br/><span data-ttu-id="163d0-122">-URL in een Office-bestand</span><span class="sxs-lookup"><span data-stu-id="163d0-122">- URL in an Office file</span></span>      |[<span data-ttu-id="163d0-123">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="163d0-123">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="163d0-124">Verdachte spam, phishing, Url's en bestanden naar Microsoft versturen voor de scan</span><span class="sxs-lookup"><span data-stu-id="163d0-124">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="163d0-125">Bestand of app op een apparaat</span><span class="sxs-lookup"><span data-stu-id="163d0-125">File or app on a device</span></span>    |[<span data-ttu-id="163d0-126">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="163d0-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="163d0-127">Een bestand bij Microsoft indienen voor het analyseren van malware</span><span class="sxs-lookup"><span data-stu-id="163d0-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="163d0-128">Een waarschuwing aanpassen om fout-positieven van herhaling te voorkomen</span><span class="sxs-lookup"><span data-stu-id="163d0-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="163d0-129">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="163d0-129">Scenario</span></span> |<span data-ttu-id="163d0-130">Service</span><span class="sxs-lookup"><span data-stu-id="163d0-130">Service</span></span> |<span data-ttu-id="163d0-131">Wat moet u doen?</span><span class="sxs-lookup"><span data-stu-id="163d0-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="163d0-132">-Een waarschuwing wordt geactiveerd door legitiem gebruik</span><span class="sxs-lookup"><span data-stu-id="163d0-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="163d0-133">-Een waarschuwingssignaal klopt niet</span><span class="sxs-lookup"><span data-stu-id="163d0-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="163d0-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="163d0-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="163d0-135">of</span><span class="sxs-lookup"><span data-stu-id="163d0-135">or</span></span> <br/>[<span data-ttu-id="163d0-136">Detectie van Azure Advanced Threat</span><span class="sxs-lookup"><span data-stu-id="163d0-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="163d0-137">Waarschuwingen beheren in de Cloud app Security Portal</span><span class="sxs-lookup"><span data-stu-id="163d0-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="163d0-138">Een bestand, IP-adres, URL of domein wordt behandeld als malware op een apparaat, ook al is het veilig</span><span class="sxs-lookup"><span data-stu-id="163d0-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="163d0-139">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="163d0-139">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="163d0-140">Een aangepaste indicator met een actie toestaan maken</span><span class="sxs-lookup"><span data-stu-id="163d0-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="163d0-141">Een herstelactie ongedaan maken die op een apparaat is uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="163d0-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="163d0-142">Als een herstelbewerking is uitgevoerd op een apparaat (zoals een Windows 10-apparaat) en het item eigenlijk geen bedreiging is, kan uw beveiligingsteam de actie voor herstel ongedaan maken in het [Actiecentrum](mtp-action-center.md).</span><span class="sxs-lookup"><span data-stu-id="163d0-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually not a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="163d0-143">Zorg ervoor dat u de [benodigde machtigingen](mtp-action-center.md#required-permissions-for-action-center-tasks) hebt voordat u de volgende taak probeert uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="163d0-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="163d0-144">Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="163d0-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="163d0-145">Kies in het navigatiedeelvenster de optie **Onderhoudscentrum**.</span><span class="sxs-lookup"><span data-stu-id="163d0-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="163d0-146">Selecteer op het tabblad **geschiedenis** een actie die u ongedaan wilt maken.</span><span class="sxs-lookup"><span data-stu-id="163d0-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="163d0-147">Hiermee wordt een flyout geopend.</span><span class="sxs-lookup"><span data-stu-id="163d0-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="163d0-148">Filters gebruiken om de lijst met resultaten te verfijnen.</span><span class="sxs-lookup"><span data-stu-id="163d0-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="163d0-149">Selecteer in het vervolgmenu voor het geselecteerde item de optie **onderzoek pagina openen**.</span><span class="sxs-lookup"><span data-stu-id="163d0-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="163d0-150">Selecteer in de weergave Details van onderzoek het tabblad **acties** .</span><span class="sxs-lookup"><span data-stu-id="163d0-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="163d0-151">Selecteer een item met de status **voltooid**en zoek een koppeling, zoals **goedgekeurd**, in de kolom **besluiten** .</span><span class="sxs-lookup"><span data-stu-id="163d0-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="163d0-152">Er wordt een flyout geopend met meer informatie over de actie.</span><span class="sxs-lookup"><span data-stu-id="163d0-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="163d0-153">Als u de actie ongedaan wilt maken, selecteert u **herstel verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="163d0-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="see-also"></a><span data-ttu-id="163d0-154">Zie ook</span><span class="sxs-lookup"><span data-stu-id="163d0-154">See also</span></span>

- [<span data-ttu-id="163d0-155">De details en resultaten van een geautomatiseerd onderzoek weergeven</span><span class="sxs-lookup"><span data-stu-id="163d0-155">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="163d0-156">Ervaring opzeggen met een geavanceerde jacht in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="163d0-156">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)
