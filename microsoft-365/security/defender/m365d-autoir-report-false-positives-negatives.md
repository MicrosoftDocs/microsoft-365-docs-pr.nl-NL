---
title: Onwaar positieven of onwaar negatieven verwerken in AIR in Microsoft 365 Defender
description: Is er iets gemist of ten onrechte gedetecteerd door AIR in Microsoft 365 Defender? Meer informatie over het indienen van fout-positieven of onwaar negatieven bij Microsoft voor analyse.
keywords: geautomatiseerd, onderzoek, waarschuwing, herstel, onwaar positief, onwaar negatief
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 8658b08f0d3948d6d23486ec885486e8bbfdf273
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056623"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="e8361-105">False positives/negatives verwerken in geautomatiseerde onderzoeks- en antwoordmogelijkheden</span><span class="sxs-lookup"><span data-stu-id="e8361-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e8361-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e8361-106">**Applies to:**</span></span>
- <span data-ttu-id="e8361-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e8361-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="e8361-108">Onwaar positieven/negatieven kunnen af en toe optreden met een bedreigingsbeveiligingsoplossing.</span><span class="sxs-lookup"><span data-stu-id="e8361-108">False positives/negatives can occasionally occur with any threat protection solution.</span></span> <span data-ttu-id="e8361-109">Als [geautomatiseerde onderzoeks- en antwoordmogelijkheden](m365d-autoir.md) in Microsoft 365 Defender iets hebben gemist of ten onrechte zijn gedetecteerd, zijn er stappen die uw beveiligingsteam kan uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="e8361-109">If [automated investigation and response capabilities](m365d-autoir.md) in Microsoft 365 Defender missed or wrongly detected something, there are steps your security operations team can take:</span></span>

- <span data-ttu-id="e8361-110">[Een onwaar positief/negatief melden bij Microsoft;](#report-a-false-positivenegative-to-microsoft-for-analysis)</span><span class="sxs-lookup"><span data-stu-id="e8361-110">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="e8361-111">[Pas uw waarschuwingen (indien](#adjust-an-alert-to-prevent-false-positives-from-recurring) nodig) aan; en</span><span class="sxs-lookup"><span data-stu-id="e8361-111">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="e8361-112">[Herstelacties ongedaan maken die zijn genomen op apparaten.](#undo-a-remediation-action-that-was-taken-on-a-device)</span><span class="sxs-lookup"><span data-stu-id="e8361-112">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="e8361-113">In de volgende secties wordt beschreven hoe u deze taken uitvoert.</span><span class="sxs-lookup"><span data-stu-id="e8361-113">The following sections describe how to perform these tasks.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="e8361-114">Een onwaar positief/negatief melden bij Microsoft voor analyse</span><span class="sxs-lookup"><span data-stu-id="e8361-114">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="e8361-115">Item gemist of ten onrechte gedetecteerd</span><span class="sxs-lookup"><span data-stu-id="e8361-115">Item missed or wrongly detected</span></span> |<span data-ttu-id="e8361-116">Service</span><span class="sxs-lookup"><span data-stu-id="e8361-116">Service</span></span>  |<span data-ttu-id="e8361-117">Wat moet u doen?</span><span class="sxs-lookup"><span data-stu-id="e8361-117">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="e8361-118">- E-mailbericht</span><span class="sxs-lookup"><span data-stu-id="e8361-118">- Email message</span></span> <br/><span data-ttu-id="e8361-119">- E-mailbijlage</span><span class="sxs-lookup"><span data-stu-id="e8361-119">- Email attachment</span></span> <br/><span data-ttu-id="e8361-120">- URL in een e-mailbericht</span><span class="sxs-lookup"><span data-stu-id="e8361-120">- URL in an email message</span></span><br/><span data-ttu-id="e8361-121">- URL in een Office-bestand</span><span class="sxs-lookup"><span data-stu-id="e8361-121">- URL in an Office file</span></span>      |[<span data-ttu-id="e8361-122">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="e8361-122">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/defender-365-security/defender-for-office-365)        |[<span data-ttu-id="e8361-123">Verdachte spam, phish, URL's en bestanden indienen bij Microsoft voor scannen</span><span class="sxs-lookup"><span data-stu-id="e8361-123">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](../defender-365-security/admin-submission.md)         |
|<span data-ttu-id="e8361-124">Bestand of app op een apparaat</span><span class="sxs-lookup"><span data-stu-id="e8361-124">File or app on a device</span></span>    |[<span data-ttu-id="e8361-125">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="e8361-125">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)         |[<span data-ttu-id="e8361-126">Een bestand indienen bij Microsoft voor malwareanalyse</span><span class="sxs-lookup"><span data-stu-id="e8361-126">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="e8361-127">Een waarschuwing aanpassen om te voorkomen dat fout-positieven terugkeren</span><span class="sxs-lookup"><span data-stu-id="e8361-127">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="e8361-128">Scenario</span><span class="sxs-lookup"><span data-stu-id="e8361-128">Scenario</span></span> |<span data-ttu-id="e8361-129">Service</span><span class="sxs-lookup"><span data-stu-id="e8361-129">Service</span></span> |<span data-ttu-id="e8361-130">Wat moet u doen?</span><span class="sxs-lookup"><span data-stu-id="e8361-130">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="e8361-131">- Een waarschuwing wordt geactiveerd door legitiem gebruik</span><span class="sxs-lookup"><span data-stu-id="e8361-131">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="e8361-132">- Een waarschuwing is onjuist</span><span class="sxs-lookup"><span data-stu-id="e8361-132">- An alert is inaccurate</span></span>    |[<span data-ttu-id="e8361-133">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="e8361-133">Microsoft Cloud App Security</span></span>](/cloud-app-security)<br/> <span data-ttu-id="e8361-134">of</span><span class="sxs-lookup"><span data-stu-id="e8361-134">or</span></span> <br/>[<span data-ttu-id="e8361-135">Azure Advanced Threat Detection</span><span class="sxs-lookup"><span data-stu-id="e8361-135">Azure Advanced Threat Detection</span></span>](/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="e8361-136">Waarschuwingen beheren in de cloud-app-beveiligingsportal</span><span class="sxs-lookup"><span data-stu-id="e8361-136">Manage alerts in the Cloud App Security portal</span></span>](/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="e8361-137">Een bestand, IP-adres, URL of domein wordt behandeld als malware op een apparaat, ook al is het veilig</span><span class="sxs-lookup"><span data-stu-id="e8361-137">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="e8361-138">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="e8361-138">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection) |[<span data-ttu-id="e8361-139">Een aangepaste indicator maken met de actie Toestaan</span><span class="sxs-lookup"><span data-stu-id="e8361-139">Create a custom indicator with an "Allow" action</span></span>](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="e8361-140">Een herstelactie ongedaan maken die is ondernomen op een apparaat</span><span class="sxs-lookup"><span data-stu-id="e8361-140">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="e8361-141">Als er een herstelactie is uitgevoerd op een entiteit (zoals een apparaat of een e-mailbericht) en de betreffende entiteit geen bedreiging is, kan uw beveiligingsteam de herstelactie ongedaan maken in het [Actiecentrum.](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="e8361-141">If a remediation action was taken on an entity (such as a device or an email message) and the affected entity is not actually a threat, your security operations team can undo the remediation action in the [Action center](m365d-action-center.md).</span></span>

1. <span data-ttu-id="e8361-142">Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="e8361-142">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="e8361-143">Kies actiecentrum in het **navigatiedeelvenster.**</span><span class="sxs-lookup"><span data-stu-id="e8361-143">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="e8361-144">Selecteer op **het** tabblad Geschiedenis een actie die u ongedaan wilt maken.</span><span class="sxs-lookup"><span data-stu-id="e8361-144">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="e8361-145">Het deelvenster Flyout wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="e8361-145">Its flyout pane opens.</span></span>
4. <span data-ttu-id="e8361-146">Selecteer ongedaan maken in het deelvenster Flyout.</span><span class="sxs-lookup"><span data-stu-id="e8361-146">In the flyout pane, select **Undo**.</span></span>

> [!TIP]
> <span data-ttu-id="e8361-147">Zie [Voltooide acties ongedaan maken.](m365d-autoir-actions.md#undo-completed-actions)</span><span class="sxs-lookup"><span data-stu-id="e8361-147">See [Undo completed actions](m365d-autoir-actions.md#undo-completed-actions).</span></span>

## <a name="see-also"></a><span data-ttu-id="e8361-148">Zie ook</span><span class="sxs-lookup"><span data-stu-id="e8361-148">See also</span></span>

- [<span data-ttu-id="e8361-149">De details en resultaten van een geautomatiseerd onderzoek weergeven</span><span class="sxs-lookup"><span data-stu-id="e8361-149">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="e8361-150">Proactief op bedreigingen zoeken met geavanceerde jacht in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e8361-150">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e8361-151">False positives/negatives in Microsoft Defender for Endpoint adresseert</span><span class="sxs-lookup"><span data-stu-id="e8361-151">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/defender-endpoint-false-positives-negatives)