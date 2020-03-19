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
ms.openlocfilehash: 2f3808f599caa4ed347fc182005397c14b9f51b2
ms.sourcegitcommit: 133bf7936e5ef1a4d06998429d0d01096bda929f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42810458"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="674ec-105">Omgaan met false positives/negatives in geautomatiseerde onderzoeks- en reactiemogelijkheden</span><span class="sxs-lookup"><span data-stu-id="674ec-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="674ec-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="674ec-106">**Applies to:**</span></span>
- <span data-ttu-id="674ec-107">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="674ec-107">Microsoft Threat Protection</span></span>

<span data-ttu-id="674ec-108">Hebben [geautomatiseerde onderzoeks- en reactiemogelijkheden](mtp-autoir.md) in Microsoft Threat Protection iets gemist of verkeerd gedetecteerd?</span><span class="sxs-lookup"><span data-stu-id="674ec-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="674ec-109">Er zijn stappen die u nemen om het te repareren.</span><span class="sxs-lookup"><span data-stu-id="674ec-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="674ec-110">U kunt:</span><span class="sxs-lookup"><span data-stu-id="674ec-110">You can:</span></span>

- <span data-ttu-id="674ec-111">[Een fout-positief/negatief melden aan Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="674ec-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="674ec-112">[Pas uw waarschuwingen aan](#adjust-an-alert-to-prevent-false-positives-from-recurring) (indien nodig); En</span><span class="sxs-lookup"><span data-stu-id="674ec-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="674ec-113">[Herstelacties ongedaan maken die op apparaten zijn uitgevoerd.](#undo-a-remediation-action-that-was-taken-on-a-device)</span><span class="sxs-lookup"><span data-stu-id="674ec-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="674ec-114">Gebruik dit artikel als een gids.</span><span class="sxs-lookup"><span data-stu-id="674ec-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="674ec-115">Een fout-positief/negatief melden aan Microsoft voor analyse</span><span class="sxs-lookup"><span data-stu-id="674ec-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="674ec-116">Object gemist of ten onrechte gedetecteerd</span><span class="sxs-lookup"><span data-stu-id="674ec-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="674ec-117">Service</span><span class="sxs-lookup"><span data-stu-id="674ec-117">Service</span></span>  |<span data-ttu-id="674ec-118">Wat te doen</span><span class="sxs-lookup"><span data-stu-id="674ec-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="674ec-119">- E-mailbericht</span><span class="sxs-lookup"><span data-stu-id="674ec-119">- Email message</span></span> <br/><span data-ttu-id="674ec-120">- E-mailbijlage</span><span class="sxs-lookup"><span data-stu-id="674ec-120">- Email attachment</span></span> <br/><span data-ttu-id="674ec-121">- URL in een e-mailbericht</span><span class="sxs-lookup"><span data-stu-id="674ec-121">- URL in an email message</span></span><br/><span data-ttu-id="674ec-122">- URL in een Office-bestand</span><span class="sxs-lookup"><span data-stu-id="674ec-122">- URL in an Office file</span></span>      |[<span data-ttu-id="674ec-123">Geavanceerde bedreigingsbeveiliging van Office 365</span><span class="sxs-lookup"><span data-stu-id="674ec-123">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="674ec-124">Vermoedelijke spam, phish, URL's en bestanden verzenden naar Microsoft voor het scannen van Office 365</span><span class="sxs-lookup"><span data-stu-id="674ec-124">Submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="674ec-125">Bestand of app op een apparaat</span><span class="sxs-lookup"><span data-stu-id="674ec-125">File or app on a device</span></span>    |[<span data-ttu-id="674ec-126">Geavanceerde bescherming voor geavanceerde bedreigingen van Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="674ec-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="674ec-127">Een bestand indienen bij Microsoft voor malware-analyse</span><span class="sxs-lookup"><span data-stu-id="674ec-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="674ec-128">Een waarschuwing aanpassen om te voorkomen dat fout-positieven terugkeren</span><span class="sxs-lookup"><span data-stu-id="674ec-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="674ec-129">Scenario</span><span class="sxs-lookup"><span data-stu-id="674ec-129">Scenario</span></span> |<span data-ttu-id="674ec-130">Service</span><span class="sxs-lookup"><span data-stu-id="674ec-130">Service</span></span> |<span data-ttu-id="674ec-131">Wat te doen</span><span class="sxs-lookup"><span data-stu-id="674ec-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="674ec-132">- Een waarschuwing wordt geactiveerd door legitiem gebruik</span><span class="sxs-lookup"><span data-stu-id="674ec-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="674ec-133">- Een waarschuwing is onjuist</span><span class="sxs-lookup"><span data-stu-id="674ec-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="674ec-134">Beveiliging van Microsoft Cloud-apps</span><span class="sxs-lookup"><span data-stu-id="674ec-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="674ec-135">of</span><span class="sxs-lookup"><span data-stu-id="674ec-135">or</span></span> <br/>[<span data-ttu-id="674ec-136">Azure Advanced Threat Detection</span><span class="sxs-lookup"><span data-stu-id="674ec-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="674ec-137">Waarschuwingen beheren in de cloudapp-beveiligingsportal</span><span class="sxs-lookup"><span data-stu-id="674ec-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="674ec-138">Een bestand, IP-adres, URL of domein wordt behandeld als malware op een apparaat, ook al is het veilig</span><span class="sxs-lookup"><span data-stu-id="674ec-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="674ec-139">Geavanceerde bescherming voor geavanceerde bedreigingen van Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="674ec-139">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="674ec-140">Een aangepaste indicator maken met de actie 'Toestaan'</span><span class="sxs-lookup"><span data-stu-id="674ec-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="674ec-141">Een herstelactie ongedaan maken die op een apparaat is uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="674ec-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="674ec-142">Als er een herstelactie is uitgevoerd op een apparaat (zoals een Windows 10-apparaat) en het item daadwerkelijk schoon is, kan uw beveiligingsteam de herstelactie in het [actiecentrum](mtp-action-center.md)ongedaan maken.</span><span class="sxs-lookup"><span data-stu-id="674ec-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually clean, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="674ec-143">Zorg ervoor dat u over de [benodigde machtigingen beschikt](mtp-action-center.md#required-permissions-for-action-center-tasks) voordat u probeert de volgende taak uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="674ec-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="674ec-144">Ga [https://security.microsoft.com](https://security.microsoft.com) naar en meld je aan.</span><span class="sxs-lookup"><span data-stu-id="674ec-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="674ec-145">Kies In het navigatiedeelvenster de optie **Actiecentrum**.</span><span class="sxs-lookup"><span data-stu-id="674ec-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="674ec-146">Selecteer op het tabblad **Historie** een actie die u ongedaan wilt maken.</span><span class="sxs-lookup"><span data-stu-id="674ec-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="674ec-147">Dit opent een flyout.</span><span class="sxs-lookup"><span data-stu-id="674ec-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="674ec-148">Gebruik filters om de lijst met resultaten te beperken.</span><span class="sxs-lookup"><span data-stu-id="674ec-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="674ec-149">Selecteer in de flyout voor het geselecteerde item de **optie Onderzoekspagina openen**.</span><span class="sxs-lookup"><span data-stu-id="674ec-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="674ec-150">Selecteer in de weergave Onderzoeksdetails het tabblad **Handelingen.**</span><span class="sxs-lookup"><span data-stu-id="674ec-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="674ec-151">Selecteer een item met de status **Voltooid**en zoek naar een koppeling, zoals **Goedgekeurd,** in de kolom **Besluiten.**</span><span class="sxs-lookup"><span data-stu-id="674ec-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="674ec-152">Dit opent een flyout met meer details over de actie.</span><span class="sxs-lookup"><span data-stu-id="674ec-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="674ec-153">Als u de actie ongedaan wilt maken, selecteert u **Herstel verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="674ec-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="674ec-154">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="674ec-154">Related articles</span></span>

- [<span data-ttu-id="674ec-155">Acties met betrekking tot geautomatiseerd onderzoek en antwoord goedkeuren of afwijzen</span><span class="sxs-lookup"><span data-stu-id="674ec-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)

- [<span data-ttu-id="674ec-156">Meer informatie over het actiecentrum</span><span class="sxs-lookup"><span data-stu-id="674ec-156">Learn more about the Action center</span></span>](mtp-action-center.md)

- [<span data-ttu-id="674ec-157">Proactief op zoek naar bedreigingen met geavanceerde jacht in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="674ec-157">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)
