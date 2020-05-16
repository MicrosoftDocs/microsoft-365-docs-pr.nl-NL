---
title: Valse positieven of valse negatieven melden in automatisch onderzoek en reactie van Office 365
description: Is er iets gemist of verkeerd gedetecteerd door Office 365 Advanced Threat Protection? Meer informatie over het indienen van false positives of false negatives bij Microsoft voor analyse.
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
ms.date: 05/15/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 2dd67af62a400f3e217f146e6d0ee213d74ad99a
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262408"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="f858a-105">Valse positieven/negatieven melden in geautomatiseerde onderzoeks- en reactiemogelijkheden</span><span class="sxs-lookup"><span data-stu-id="f858a-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="f858a-106">**Geldt voor:**</span><span class="sxs-lookup"><span data-stu-id="f858a-106">**Applies to:**</span></span>
- <span data-ttu-id="f858a-107">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f858a-107">Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="f858a-108">Heeft [automatische air-mogelijkheden (investigation and response) in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) iets gemist of verkeerd gedetecteerd?</span><span class="sxs-lookup"><span data-stu-id="f858a-108">Did [automated investigation and response (AIR) capabilities in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) miss or wrongly detect something?</span></span> <span data-ttu-id="f858a-109">Er zijn stappen die u nemen om het te repareren.</span><span class="sxs-lookup"><span data-stu-id="f858a-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="f858a-110">U kunt:</span><span class="sxs-lookup"><span data-stu-id="f858a-110">You can:</span></span>
- <span data-ttu-id="f858a-111">[Een fout-positief/negatief melden aan Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="f858a-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="f858a-112">[Pas uw waarschuwingen aan](#adjust-an-alert-to-prevent-false-positives-from-recurring) (indien nodig); En</span><span class="sxs-lookup"><span data-stu-id="f858a-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="f858a-113">[Herstelacties ongedaan maken die op apparaten zijn uitgevoerd.](#undo-a-remediation-action)</span><span class="sxs-lookup"><span data-stu-id="f858a-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action).</span></span> 

<span data-ttu-id="f858a-114">Gebruik dit artikel als een gids.</span><span class="sxs-lookup"><span data-stu-id="f858a-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="f858a-115">Een fout-positief/negatief melden aan Microsoft voor analyse</span><span class="sxs-lookup"><span data-stu-id="f858a-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="f858a-116">Als Office 365 AIR een e-mailbericht, een e-mailbijlage, een URL in een e-mailbericht of een URL in een Office-bestand heeft gemist, u [verdachte spam, phish, URL's en bestanden indienen bij Microsoft voor het scannen van Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)</span><span class="sxs-lookup"><span data-stu-id="f858a-116">If Office 365 AIR missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span></span>

<span data-ttu-id="f858a-117">U ook [een bestand indienen bij Microsoft voor malwareanalyse.](https://www.microsoft.com/wdsi/filesubmission)</span><span class="sxs-lookup"><span data-stu-id="f858a-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="f858a-118">Een waarschuwing aanpassen om te voorkomen dat fout-positieven terugkeren</span><span class="sxs-lookup"><span data-stu-id="f858a-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="f858a-119">Als een waarschuwing wordt geactiveerd door legitiem gebruik of als de waarschuwing onjuist is, u [waarschuwingen beheren in de Cloud App Security-portal.](https://docs.microsoft.com/cloud-app-security/managing-alerts)</span><span class="sxs-lookup"><span data-stu-id="f858a-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="f858a-120">Als uw organisatie [microsoft defender advanced threat protection](https://docs.microsoft.com/windows/security/threat-protection) gebruikt naast Office 365 en een bestand, IP-adres, URL of domein wordt behandeld als malware op een apparaat, ook al is het veilig, u een aangepaste indicator maken met een actie ['Toestaan' voor uw apparaat.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="f858a-120">If your organization is using [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="f858a-121">Een herstelactie ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="f858a-121">Undo a remediation action</span></span>

<span data-ttu-id="f858a-122">In de meeste gevallen, als een herstelactie is uitgevoerd op een e-mailbericht, e-mailbijlage of URL, en het item is eigenlijk geen bedreiging, kan uw security operations team ongedaan maken van de herstelactie en stappen ondernemen om te voorkomen dat de false positive van terugkerende.</span><span class="sxs-lookup"><span data-stu-id="f858a-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="f858a-123">U [Threat Explorer](#undo-an-action-using-threat-explorer) of het tabblad Handelingen gebruiken [voor een onderzoek](#undo-an-action-using-the-actions-tab-for-an-investigation) om een actie ongedaan te maken.</span><span class="sxs-lookup"><span data-stu-id="f858a-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-using-the-actions-tab-for-an-investigation) to undo an action.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="f858a-124">Zorg ervoor dat u over de benodigde machtigingen beschikt voordat u probeert de volgende taken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="f858a-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="f858a-125">Een actie ongedaan maken met Threat Explorer</span><span class="sxs-lookup"><span data-stu-id="f858a-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="f858a-126">Met Threat Explorer kan uw beveiligingsteam een e-mail vinden die is beïnvloed door een actie en de actie mogelijk ongedaan maken.</span><span class="sxs-lookup"><span data-stu-id="f858a-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="f858a-127">Scenario</span><span class="sxs-lookup"><span data-stu-id="f858a-127">Scenario</span></span>  |<span data-ttu-id="f858a-128">Opties ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="f858a-128">Undo Options</span></span>  |<span data-ttu-id="f858a-129">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="f858a-129">Learn more</span></span> |
|---------|---------|---------|
|<span data-ttu-id="f858a-130">Er is een e-mailbericht doorgestuurd naar de map Ongewenste e-mail van een gebruiker</span><span class="sxs-lookup"><span data-stu-id="f858a-130">An email message was routed to a user's Junk Email folder</span></span>     |<span data-ttu-id="f858a-131">- Het bericht verplaatsen naar de map Verwijderde items van de gebruiker</span><span class="sxs-lookup"><span data-stu-id="f858a-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="f858a-132">- Het bericht verplaatsen naar het Postvak IN van de gebruiker</span><span class="sxs-lookup"><span data-stu-id="f858a-132">- Move the message to the user's Inbox</span></span> <br/><span data-ttu-id="f858a-133">- Het bericht verwijderen</span><span class="sxs-lookup"><span data-stu-id="f858a-133">- Delete the message</span></span>          |[<span data-ttu-id="f858a-134">Schadelijke e-mail zoeken en onderzoeken die is geleverd in Office 365</span><span class="sxs-lookup"><span data-stu-id="f858a-134">Find and investigate malicious email that was delivered in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered) |
|<span data-ttu-id="f858a-135">Een e-mailbericht of een bestand is in quarantaine geplaatst</span><span class="sxs-lookup"><span data-stu-id="f858a-135">An email message or a file was quarantined</span></span>     |<span data-ttu-id="f858a-136">- Laat de e-mail of het bestand vrij</span><span class="sxs-lookup"><span data-stu-id="f858a-136">- Release the email or file</span></span> <br/><span data-ttu-id="f858a-137">- Verwijder de e-mail of het bestand</span><span class="sxs-lookup"><span data-stu-id="f858a-137">- Delete the email or file</span></span>         |[<span data-ttu-id="f858a-138">In quarantaine geplaatste berichten en bestanden beheren als beheerder in Office 365</span><span class="sxs-lookup"><span data-stu-id="f858a-138">Manage quarantined messages and files as an administrator in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files) |


### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a><span data-ttu-id="f858a-139">Een actie ongedaan maken met het tabblad Acties voor een onderzoek</span><span class="sxs-lookup"><span data-stu-id="f858a-139">Undo an action using the Actions tab for an investigation</span></span>

<span data-ttu-id="f858a-140">In het actiecentrum u herstelacties zien die zijn uitgevoerd en mogelijk de actie ongedaan maken.</span><span class="sxs-lookup"><span data-stu-id="f858a-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="f858a-141">Ga naar [https://protection.office.com](https://protection.office.com) en meld je aan.</span><span class="sxs-lookup"><span data-stu-id="f858a-141">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="f858a-142">Dit brengt u naar het Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="f858a-142">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="f858a-143">Ga naar **Threat Management**  >  **Investigations**.</span><span class="sxs-lookup"><span data-stu-id="f858a-143">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="f858a-144">Selecteer in de lijst met onderzoeken het pictogram **Openen in nieuw venster** naast de id van een item.</span><span class="sxs-lookup"><span data-stu-id="f858a-144">In the list of investigations, select the **Open in new window** icon next to an item's ID.</span></span>

4. <span data-ttu-id="f858a-145">Selecteer het tabblad **Handelingen.**</span><span class="sxs-lookup"><span data-stu-id="f858a-145">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="f858a-146">Selecteer een item met de status **Voltooid**en zoek naar een koppeling, zoals **Goedgekeurd,** in de kolom **Besluit.**</span><span class="sxs-lookup"><span data-stu-id="f858a-146">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decision** column.</span></span> <span data-ttu-id="f858a-147">Dit opent een flyout met meer details over de actie.</span><span class="sxs-lookup"><span data-stu-id="f858a-147">This opens a flyout with more details about the action.</span></span>

6. <span data-ttu-id="f858a-148">Als u de actie ongedaan wilt maken, selecteert u **Herstel verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="f858a-148">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f858a-149">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="f858a-149">Related articles</span></span>

[<span data-ttu-id="f858a-150">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f858a-150">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[<span data-ttu-id="f858a-151">Aan de slag met Automated Investigation and Response (AIR) in Office 365</span><span class="sxs-lookup"><span data-stu-id="f858a-151">Get started using Automated investigation and response (AIR) in Office 365</span></span>](office-365-air.md)