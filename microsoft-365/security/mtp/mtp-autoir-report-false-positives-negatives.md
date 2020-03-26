---
title: Omgaan met false positives of false negatives in AIR in Microsoft Threat Protection
description: Is er iets gemist of verkeerd gedetecteerd door AIR in Microsoft Threat Protection? Meer informatie over het indienen van false positives of false negatives bij Microsoft voor analyse.
keywords: geautomatiseerd, onderzoek, alert, trigger, actie, sanering, vals-positief, vals-negatief
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 90651aa258adb9f7fe46f99bcadf1d4d552a5b76
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955659"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="23c19-105">Omgaan met false positives/negatives in geautomatiseerde onderzoeks- en reactiemogelijkheden</span><span class="sxs-lookup"><span data-stu-id="23c19-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="23c19-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="23c19-106">**Applies to:**</span></span>
- <span data-ttu-id="23c19-107">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="23c19-107">Microsoft Threat Protection</span></span>

<span data-ttu-id="23c19-108">Hebben [geautomatiseerde onderzoeks- en reactiemogelijkheden](mtp-autoir.md) in Microsoft Threat Protection iets gemist of verkeerd gedetecteerd?</span><span class="sxs-lookup"><span data-stu-id="23c19-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="23c19-109">Er zijn stappen die u nemen om het te repareren.</span><span class="sxs-lookup"><span data-stu-id="23c19-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="23c19-110">U kunt:</span><span class="sxs-lookup"><span data-stu-id="23c19-110">You can:</span></span>

- <span data-ttu-id="23c19-111">[Een fout-positief/negatief melden aan Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="23c19-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="23c19-112">[Pas uw waarschuwingen aan](#adjust-an-alert-to-prevent-false-positives-from-recurring) (indien nodig); En</span><span class="sxs-lookup"><span data-stu-id="23c19-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="23c19-113">[Herstelacties ongedaan maken die op apparaten zijn uitgevoerd.](#undo-a-remediation-action-that-was-taken-on-a-device)</span><span class="sxs-lookup"><span data-stu-id="23c19-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="23c19-114">Gebruik dit artikel als een gids.</span><span class="sxs-lookup"><span data-stu-id="23c19-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="23c19-115">Een fout-positief/negatief melden aan Microsoft voor analyse</span><span class="sxs-lookup"><span data-stu-id="23c19-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="23c19-116">Object gemist of ten onrechte gedetecteerd</span><span class="sxs-lookup"><span data-stu-id="23c19-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="23c19-117">Service</span><span class="sxs-lookup"><span data-stu-id="23c19-117">Service</span></span>  |<span data-ttu-id="23c19-118">Wat te doen</span><span class="sxs-lookup"><span data-stu-id="23c19-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="23c19-119">- E-mailbericht</span><span class="sxs-lookup"><span data-stu-id="23c19-119">- Email message</span></span> <br/><span data-ttu-id="23c19-120">- E-mailbijlage</span><span class="sxs-lookup"><span data-stu-id="23c19-120">- Email attachment</span></span> <br/><span data-ttu-id="23c19-121">- URL in een e-mailbericht</span><span class="sxs-lookup"><span data-stu-id="23c19-121">- URL in an email message</span></span><br/><span data-ttu-id="23c19-122">- URL in een Office-bestand</span><span class="sxs-lookup"><span data-stu-id="23c19-122">- URL in an Office file</span></span>      |[<span data-ttu-id="23c19-123">Geavanceerde bedreigingsbeveiliging van Office 365</span><span class="sxs-lookup"><span data-stu-id="23c19-123">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="23c19-124">Vermoedelijke spam, phish, URL's en bestanden verzenden naar Microsoft voor het scannen van Office 365</span><span class="sxs-lookup"><span data-stu-id="23c19-124">Submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="23c19-125">Bestand of app op een apparaat</span><span class="sxs-lookup"><span data-stu-id="23c19-125">File or app on a device</span></span>    |[<span data-ttu-id="23c19-126">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="23c19-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="23c19-127">Een bestand indienen bij Microsoft voor malware-analyse</span><span class="sxs-lookup"><span data-stu-id="23c19-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="23c19-128">Een waarschuwing aanpassen om te voorkomen dat fout-positieven terugkeren</span><span class="sxs-lookup"><span data-stu-id="23c19-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="23c19-129">Scenario</span><span class="sxs-lookup"><span data-stu-id="23c19-129">Scenario</span></span> |<span data-ttu-id="23c19-130">Service</span><span class="sxs-lookup"><span data-stu-id="23c19-130">Service</span></span> |<span data-ttu-id="23c19-131">Wat te doen</span><span class="sxs-lookup"><span data-stu-id="23c19-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="23c19-132">- Een waarschuwing wordt geactiveerd door legitiem gebruik</span><span class="sxs-lookup"><span data-stu-id="23c19-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="23c19-133">- Een waarschuwing is onjuist</span><span class="sxs-lookup"><span data-stu-id="23c19-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="23c19-134">Beveiliging van Microsoft Cloud-apps</span><span class="sxs-lookup"><span data-stu-id="23c19-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="23c19-135">of</span><span class="sxs-lookup"><span data-stu-id="23c19-135">or</span></span> <br/>[<span data-ttu-id="23c19-136">Azure Advanced Threat Detection</span><span class="sxs-lookup"><span data-stu-id="23c19-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="23c19-137">Waarschuwingen beheren in de cloudapp-beveiligingsportal</span><span class="sxs-lookup"><span data-stu-id="23c19-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="23c19-138">Een bestand, IP-adres, URL of domein wordt behandeld als malware op een apparaat, ook al is het veilig</span><span class="sxs-lookup"><span data-stu-id="23c19-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="23c19-139">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="23c19-139">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="23c19-140">Een aangepaste indicator maken met de actie 'Toestaan'</span><span class="sxs-lookup"><span data-stu-id="23c19-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="23c19-141">Een herstelactie ongedaan maken die op een apparaat is uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="23c19-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="23c19-142">Als er een herstelactie is uitgevoerd op een apparaat (zoals een Windows 10-apparaat) en het item is eigenlijk geen bedreiging, kan uw beveiligingsteam de herstelactie in het [Actiecentrum](mtp-action-center.md)ongedaan maken.</span><span class="sxs-lookup"><span data-stu-id="23c19-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually not a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="23c19-143">Zorg ervoor dat u over de [benodigde machtigingen beschikt](mtp-action-center.md#required-permissions-for-action-center-tasks) voordat u probeert de volgende taak uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="23c19-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="23c19-144">Ga [https://security.microsoft.com](https://security.microsoft.com) naar en meld je aan.</span><span class="sxs-lookup"><span data-stu-id="23c19-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="23c19-145">Kies In het navigatiedeelvenster de optie **Actiecentrum**.</span><span class="sxs-lookup"><span data-stu-id="23c19-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="23c19-146">Selecteer op het tabblad **Historie** een actie die u ongedaan wilt maken.</span><span class="sxs-lookup"><span data-stu-id="23c19-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="23c19-147">Dit opent een flyout.</span><span class="sxs-lookup"><span data-stu-id="23c19-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="23c19-148">Gebruik filters om de lijst met resultaten te beperken.</span><span class="sxs-lookup"><span data-stu-id="23c19-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="23c19-149">Selecteer in de flyout voor het geselecteerde item de **optie Onderzoekspagina openen**.</span><span class="sxs-lookup"><span data-stu-id="23c19-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="23c19-150">Selecteer in de weergave Onderzoeksdetails het tabblad **Handelingen.**</span><span class="sxs-lookup"><span data-stu-id="23c19-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="23c19-151">Selecteer een item met de status **Voltooid**en zoek naar een koppeling, zoals **Goedgekeurd,** in de kolom **Besluiten.**</span><span class="sxs-lookup"><span data-stu-id="23c19-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="23c19-152">Dit opent een flyout met meer details over de actie.</span><span class="sxs-lookup"><span data-stu-id="23c19-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="23c19-153">Als u de actie ongedaan wilt maken, selecteert u **Herstel verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="23c19-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="23c19-154">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="23c19-154">Related articles</span></span>

- [<span data-ttu-id="23c19-155">Acties met betrekking tot geautomatiseerd onderzoek en antwoord goedkeuren of afwijzen</span><span class="sxs-lookup"><span data-stu-id="23c19-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)

- [<span data-ttu-id="23c19-156">Meer informatie over het actiecentrum</span><span class="sxs-lookup"><span data-stu-id="23c19-156">Learn more about the Action center</span></span>](mtp-action-center.md)

- [<span data-ttu-id="23c19-157">Proactief op zoek naar bedreigingen met geavanceerde jacht in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="23c19-157">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)
