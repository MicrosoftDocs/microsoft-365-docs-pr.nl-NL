---
title: Onwaar-positieven of fout-negatieven verwerken in AIR in Microsoft 365 Defender
description: Is er iets gemist of ten onrechte gedetecteerd door AIR in Microsoft 365 Defender? Informatie over het indienen van fout-positieven of fout-negatieven bij Microsoft voor analyse.
keywords: geautomatiseerd, onderzoek, waarschuwing, trigger, actie, herstel, fout-positief, fout-negatief
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: dbef240e28258d1ac4000c05538d0ce073a9d910
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930352"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="2c989-105">Fout-positieven/negatieven in geautomatiseerde onderzoeks- en antwoordmogelijkheden verwerken</span><span class="sxs-lookup"><span data-stu-id="2c989-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2c989-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2c989-106">**Applies to:**</span></span>
- <span data-ttu-id="2c989-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c989-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="2c989-108">Hebben [geautomatiseerde onderzoeks- en antwoordmogelijkheden](mtp-autoir.md) in Microsoft 365 Defender iets gemist of ten onrechte gedetecteerd?</span><span class="sxs-lookup"><span data-stu-id="2c989-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft 365 Defender miss or wrongly detect something?</span></span> <span data-ttu-id="2c989-109">U kunt stappen ondernemen om dit op te lossen.</span><span class="sxs-lookup"><span data-stu-id="2c989-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="2c989-110">U kunt:</span><span class="sxs-lookup"><span data-stu-id="2c989-110">You can:</span></span>

- <span data-ttu-id="2c989-111">[Een fout-positief/negatief melden bij Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="2c989-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="2c989-112">[Pas uw waarschuwingen](#adjust-an-alert-to-prevent-false-positives-from-recurring) aan (indien nodig); en</span><span class="sxs-lookup"><span data-stu-id="2c989-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="2c989-113">[Herstelacties ongedaan maken die zijn gemaakt op apparaten.](#undo-a-remediation-action-that-was-taken-on-a-device)</span><span class="sxs-lookup"><span data-stu-id="2c989-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="2c989-114">Gebruik dit artikel als richtlijn.</span><span class="sxs-lookup"><span data-stu-id="2c989-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="2c989-115">Een fout-positief/negatief rapporteren bij Microsoft voor analyse</span><span class="sxs-lookup"><span data-stu-id="2c989-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="2c989-116">Item gemist of ten onrechte gedetecteerd</span><span class="sxs-lookup"><span data-stu-id="2c989-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="2c989-117">Service</span><span class="sxs-lookup"><span data-stu-id="2c989-117">Service</span></span>  |<span data-ttu-id="2c989-118">Wat moet u doen?</span><span class="sxs-lookup"><span data-stu-id="2c989-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="2c989-119">- E-mailbericht</span><span class="sxs-lookup"><span data-stu-id="2c989-119">- Email message</span></span> <br/><span data-ttu-id="2c989-120">- E-mailbijlage</span><span class="sxs-lookup"><span data-stu-id="2c989-120">- Email attachment</span></span> <br/><span data-ttu-id="2c989-121">- URL in een e-mailbericht</span><span class="sxs-lookup"><span data-stu-id="2c989-121">- URL in an email message</span></span><br/><span data-ttu-id="2c989-122">- URL in een Office-bestand</span><span class="sxs-lookup"><span data-stu-id="2c989-122">- URL in an Office file</span></span>      |[<span data-ttu-id="2c989-123">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2c989-123">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="2c989-124">Verdachte spam, phish, URL's en bestanden indienen bij Microsoft voor scannen</span><span class="sxs-lookup"><span data-stu-id="2c989-124">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="2c989-125">Bestand of app op een apparaat</span><span class="sxs-lookup"><span data-stu-id="2c989-125">File or app on a device</span></span>    |[<span data-ttu-id="2c989-126">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2c989-126">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="2c989-127">Een bestand bij Microsoft indienen voor malwareanalyse</span><span class="sxs-lookup"><span data-stu-id="2c989-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="2c989-128">Een waarschuwing aanpassen om te voorkomen dat fout-positieven terugkeren</span><span class="sxs-lookup"><span data-stu-id="2c989-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="2c989-129">Scenario</span><span class="sxs-lookup"><span data-stu-id="2c989-129">Scenario</span></span> |<span data-ttu-id="2c989-130">Service</span><span class="sxs-lookup"><span data-stu-id="2c989-130">Service</span></span> |<span data-ttu-id="2c989-131">Wat moet u doen?</span><span class="sxs-lookup"><span data-stu-id="2c989-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="2c989-132">- Een waarschuwing wordt geactiveerd door legitiem gebruik</span><span class="sxs-lookup"><span data-stu-id="2c989-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="2c989-133">- Een waarschuwing klopt niet</span><span class="sxs-lookup"><span data-stu-id="2c989-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="2c989-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2c989-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="2c989-135">of</span><span class="sxs-lookup"><span data-stu-id="2c989-135">or</span></span> <br/>[<span data-ttu-id="2c989-136">Azure Advanced Threat Detection</span><span class="sxs-lookup"><span data-stu-id="2c989-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="2c989-137">Waarschuwingen beheren in de cloud-app-beveiligingsportal</span><span class="sxs-lookup"><span data-stu-id="2c989-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="2c989-138">Een bestand, IP-adres, URL of domein wordt op een apparaat beschouwd als malware, ook al is het veilig</span><span class="sxs-lookup"><span data-stu-id="2c989-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="2c989-139">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2c989-139">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="2c989-140">Een aangepaste indicator maken met de actie Toestaan</span><span class="sxs-lookup"><span data-stu-id="2c989-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="2c989-141">Een herstelactie ongedaan maken die is ondernomen op een apparaat</span><span class="sxs-lookup"><span data-stu-id="2c989-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="2c989-142">Als er een herstelactie is ondernomen op een apparaat (zoals een Windows 10-apparaat) en het item in feite geen bedreiging is, kan uw team voor beveiligingsbewerkingen de herstelactie ongedaan maken in het [Actiecentrum.](mtp-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="2c989-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually not a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2c989-143">Zorg ervoor dat u de [benodigde machtigingen hebt voordat](mtp-action-center.md#required-permissions-for-action-center-tasks) u de volgende taak probeert uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="2c989-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="2c989-144">Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="2c989-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="2c989-145">Kies Actiecentrum in het **navigatiedeelvenster.**</span><span class="sxs-lookup"><span data-stu-id="2c989-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="2c989-146">Selecteer op **het** tabblad Geschiedenis een actie die u ongedaan wilt maken.</span><span class="sxs-lookup"><span data-stu-id="2c989-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="2c989-147">Er wordt een flyout geopend.</span><span class="sxs-lookup"><span data-stu-id="2c989-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="2c989-148">Gebruik filters om de lijst met resultaten te beperken.</span><span class="sxs-lookup"><span data-stu-id="2c989-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="2c989-149">Selecteer Onderzoek openen in de flyout voor **het** geselecteerde item.</span><span class="sxs-lookup"><span data-stu-id="2c989-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="2c989-150">Selecteer in de detailweergave voor onderzoek het **tabblad** Acties.</span><span class="sxs-lookup"><span data-stu-id="2c989-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="2c989-151">Selecteer een item met de status Voltooid en zoek naar een koppeling, zoals **Goedgekeurd,** in **de** kolom Beslissingen.</span><span class="sxs-lookup"><span data-stu-id="2c989-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="2c989-152">Hiermee opent u een flyout met meer details over de actie.</span><span class="sxs-lookup"><span data-stu-id="2c989-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="2c989-153">Als u de actie ongedaan wilt maken, **selecteert u Herstelactie verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="2c989-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c989-154">Zie ook</span><span class="sxs-lookup"><span data-stu-id="2c989-154">See also</span></span>

- [<span data-ttu-id="2c989-155">De details en resultaten van een geautomatiseerd onderzoek weergeven</span><span class="sxs-lookup"><span data-stu-id="2c989-155">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="2c989-156">Proactief zoeken naar bedreigingen met geavanceerd zoeken in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c989-156">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
