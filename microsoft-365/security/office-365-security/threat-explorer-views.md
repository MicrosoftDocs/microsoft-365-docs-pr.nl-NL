---
title: Weergaven in Threat Explorer en realtime detecties
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Meer informatie over het gebruik van Threat Explorer en het realtimedetectierapport voor het onderzoeken en beantwoorden van bedreigingen in Microsoft 365 Defender-portal.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1c79cc717a2dbe345627f99830590c674fa02f09
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929619"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="430b0-103">Weergaven in Threat Explorer en realtime detecties</span><span class="sxs-lookup"><span data-stu-id="430b0-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="430b0-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="430b0-104">**Applies to**</span></span>
- [<span data-ttu-id="430b0-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="430b0-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="430b0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="430b0-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)


![Bedreigingsverkenner](../../media/explorer.png)

<span data-ttu-id="430b0-108">[Threat Explorer](threat-explorer.md) (en het real-time detectierapport) is een krachtig, bijna realtime hulpprogramma waarmee beveiligingsteams bedreigingen kunnen onderzoeken en beantwoorden in de portal Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="430b0-108">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="430b0-109">Explorer (en het realtimedetectierapport) geeft informatie weer over verdachte malware en phish in e-mail en bestanden in Office 365, evenals andere beveiligingsrisico's en risico's voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="430b0-109">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="430b0-110">Als u [Microsoft Defender hebt voor Office 365](defender-for-office-365.md) abonnement 2, hebt u Explorer.</span><span class="sxs-lookup"><span data-stu-id="430b0-110">If you have [Microsoft Defender for Office 365](defender-for-office-365.md) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="430b0-111">Als u Microsoft Defender hebt voor Office 365 abonnement 1, hebt u realtime detecties.</span><span class="sxs-lookup"><span data-stu-id="430b0-111">If you have Microsoft Defender for Office 365 Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="430b0-112">Wanneer u Explorer (of het realtimedetectierapport) voor het eerst opent, worden in de standaardweergave detecties van e-mail malware voor de afgelopen 7 dagen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="430b0-112">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="430b0-113">Dit rapport kan ook Microsoft Defender voor Office 365-detecties, zoals kwaadaardige URL's die zijn gedetecteerd door [Safe Koppelingen,](safe-links.md)en schadelijke bestanden die zijn gedetecteerd door [Safe Bijlagen.](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="430b0-113">This report can also show Microsoft Defender for Office 365 detections, such as malicious URLs detected by [Safe Links](safe-links.md), and malicious files detected by [Safe Attachments](safe-attachments.md).</span></span> <span data-ttu-id="430b0-114">Dit rapport kan worden gewijzigd om gegevens van de afgelopen 30 dagen weer te geven (met een Microsoft Defender voor Office 365 P2-abonnement).</span><span class="sxs-lookup"><span data-stu-id="430b0-114">This report can be modified to show data for the past 30 days (with a Microsoft Defender for Office 365 P2 paid subscription).</span></span> <span data-ttu-id="430b0-115">Proefabonnementen bevatten alleen gegevens over de afgelopen zeven dagen.</span><span class="sxs-lookup"><span data-stu-id="430b0-115">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="430b0-116">Abonnement</span><span class="sxs-lookup"><span data-stu-id="430b0-116">Subscription</span></span>|<span data-ttu-id="430b0-117">Hulpprogramma</span><span class="sxs-lookup"><span data-stu-id="430b0-117">Utility</span></span>|<span data-ttu-id="430b0-118">Dagen van gegevens</span><span class="sxs-lookup"><span data-stu-id="430b0-118">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="430b0-119">Proefversie van Microsoft Defender Office 365 P1</span><span class="sxs-lookup"><span data-stu-id="430b0-119">Microsoft Defender for Office 365 P1 trial</span></span>|<span data-ttu-id="430b0-120">Detecties in realtime</span><span class="sxs-lookup"><span data-stu-id="430b0-120">Real-time detections</span></span>|<span data-ttu-id="430b0-121">7</span><span class="sxs-lookup"><span data-stu-id="430b0-121">7</span></span>|
|<span data-ttu-id="430b0-122">Microsoft Defender voor Office 365 P1 betaald</span><span class="sxs-lookup"><span data-stu-id="430b0-122">Microsoft Defender for Office 365 P1 paid</span></span>|<span data-ttu-id="430b0-123">Detecties in realtime</span><span class="sxs-lookup"><span data-stu-id="430b0-123">Real-time detections</span></span>|<span data-ttu-id="430b0-124">30</span><span class="sxs-lookup"><span data-stu-id="430b0-124">30</span></span>|
|<span data-ttu-id="430b0-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span><span class="sxs-lookup"><span data-stu-id="430b0-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="430b0-126">Bedreigingsverkenner</span><span class="sxs-lookup"><span data-stu-id="430b0-126">Threat Explorer</span></span>|<span data-ttu-id="430b0-127">7</span><span class="sxs-lookup"><span data-stu-id="430b0-127">7</span></span>|
|<span data-ttu-id="430b0-128">Proefversie van Microsoft Defender Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="430b0-128">Microsoft Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="430b0-129">Bedreigingsverkenner</span><span class="sxs-lookup"><span data-stu-id="430b0-129">Threat Explorer</span></span>|<span data-ttu-id="430b0-130">7</span><span class="sxs-lookup"><span data-stu-id="430b0-130">7</span></span>|
|<span data-ttu-id="430b0-131">Microsoft Defender voor Office 365 P2 betaald</span><span class="sxs-lookup"><span data-stu-id="430b0-131">Microsoft Defender for Office 365 P2 paid</span></span>|<span data-ttu-id="430b0-132">Bedreigingsverkenner</span><span class="sxs-lookup"><span data-stu-id="430b0-132">Threat Explorer</span></span>|<span data-ttu-id="430b0-133">30</span><span class="sxs-lookup"><span data-stu-id="430b0-133">30</span></span>|
|

> [!NOTE]
> <span data-ttu-id="430b0-134">Binnenkort wordt de bewaar- en zoeklimiet voor proeften tenants uitgebreid van 7 naar 30 dagen voor het bewaren en zoeken van gegevens in Explorer (en realtimedetecties).</span><span class="sxs-lookup"><span data-stu-id="430b0-134">We will soon be extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 to 30 days.</span></span> <span data-ttu-id="430b0-135">Deze wijziging wordt bijgehouden als onderdeel van routekaartitem 70544 en is momenteel in een uitrolfase.</span><span class="sxs-lookup"><span data-stu-id="430b0-135">This change is being tracked as part of roadmap item no. 70544, and is currently in a roll-out phase.</span></span>

<span data-ttu-id="430b0-136">Gebruik **het** menu Beeld om te wijzigen welke gegevens worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="430b0-136">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="430b0-137">Met knopinfo kunt u bepalen welke weergave u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="430b0-137">Tooltips help you determine which view to use.</span></span>

![Menu Bedreigingsverkennerweergave](../../media/all-email.png)

<span data-ttu-id="430b0-139">Nadat u een weergave hebt geselecteerd, kunt u filters toepassen en query's instellen om verdere analyse uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="430b0-139">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="430b0-140">In de volgende secties ziet u een kort overzicht van de verschillende weergaven die beschikbaar zijn in Explorer (of realtime detecties).</span><span class="sxs-lookup"><span data-stu-id="430b0-140">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="430b0-141">E-mail > Malware</span><span class="sxs-lookup"><span data-stu-id="430b0-141">Email > Malware</span></span>

<span data-ttu-id="430b0-142">Als u dit rapport wilt bekijken, kiest u in Explorer (of realtime detecties) **de optie E-mail malware** \>  \> **weergeven.**</span><span class="sxs-lookup"><span data-stu-id="430b0-142">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Malware**.</span></span> <span data-ttu-id="430b0-143">In deze weergave ziet u informatie over e-mailberichten die zijn geïdentificeerd als malware.</span><span class="sxs-lookup"><span data-stu-id="430b0-143">This view shows information about email messages that were identified as containing malware.</span></span>

![Gegevens weergeven over e-mail die is geïdentificeerd als malware](../../media/detection-technology.png)

<span data-ttu-id="430b0-145">Klik **op Afzender** om uw lijst met weergaveopties te openen.</span><span class="sxs-lookup"><span data-stu-id="430b0-145">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="430b0-146">Gebruik deze lijst om gegevens weer te geven op afzender, geadresseerden, afzenderdomein, onderwerp, detectietechnologie, beveiligingsstatus en meer.</span><span class="sxs-lookup"><span data-stu-id="430b0-146">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="430b0-147">Als u bijvoorbeeld wilt zien welke acties zijn ondernomen voor gedetecteerde e-mailberichten, kiest u **Beveiligingsstatus** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="430b0-147">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="430b0-148">Selecteer een optie en klik vervolgens op de knop Vernieuwen om dat filter toe te passen op uw rapport.</span><span class="sxs-lookup"><span data-stu-id="430b0-148">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![Opties voor status van bedreigingsbeveiliging voor Threat Explorer](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="430b0-150">Bekijk onder de grafiek meer informatie over specifieke berichten.</span><span class="sxs-lookup"><span data-stu-id="430b0-150">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="430b0-151">Wanneer u een item in de lijst selecteert, wordt er een fly-outvenster geopend, waar u meer informatie kunt vinden over het item dat u hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="430b0-151">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Threat Explorer met flyout geopend](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="430b0-153">E-mail > Phish</span><span class="sxs-lookup"><span data-stu-id="430b0-153">Email > Phish</span></span>

<span data-ttu-id="430b0-154">Als u dit rapport wilt bekijken, kiest u in Explorer (of realtime detecties) **de** optie \> **E-mail** \> **phish weergeven.**</span><span class="sxs-lookup"><span data-stu-id="430b0-154">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Phish**.</span></span> <span data-ttu-id="430b0-155">In deze weergave ziet u e-mailberichten die zijn geïdentificeerd als phishingpogingen.</span><span class="sxs-lookup"><span data-stu-id="430b0-155">This view shows email messages identified as phishing attempts.</span></span>

![Gegevens weergeven over e-mail die is geïdentificeerd als phishingpogingen](../../media/phish.png)

<span data-ttu-id="430b0-157">Klik **op Afzender** om uw lijst met weergaveopties te openen.</span><span class="sxs-lookup"><span data-stu-id="430b0-157">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="430b0-158">Gebruik deze lijst om gegevens te bekijken op afzender, geadresseerden, afzenderdomein, AFZENDER-IP, URL-domein, klik op vonnis en meer.</span><span class="sxs-lookup"><span data-stu-id="430b0-158">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="430b0-159">Als u bijvoorbeeld wilt zien welke acties zijn ondernomen wanneer personen op URL's klikten die zijn geïdentificeerd als phishingpogingen, kiest u Op vonnis **klikken** in de lijst, selecteert u een of meer opties en klikt u vervolgens op de knop Vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="430b0-159">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![Klik op opties voor vonnissen voor het Phish-rapport](../../media/click-verdict.png)

<span data-ttu-id="430b0-161">Bekijk onder de grafiek meer informatie over specifieke berichten, URL-klikken, URL's en e-mail origin.</span><span class="sxs-lookup"><span data-stu-id="430b0-161">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![URL's gedetecteerd als phish in e-mailberichten](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="430b0-163">Wanneer u een item in de lijst selecteert, zoals een URL die is gedetecteerd, wordt een uitvliegend deelvenster geopend, waar u meer informatie kunt vinden over het item dat u hebt geselecteerd.</span><span class="sxs-lookup"><span data-stu-id="430b0-163">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Details over een gedetecteerde URL](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="430b0-165">E-> Inzendingen</span><span class="sxs-lookup"><span data-stu-id="430b0-165">Email > Submissions</span></span>

<span data-ttu-id="430b0-166">Als u dit rapport wilt bekijken, kiest u in Explorer (of realtime detecties) **de** optie \>  \> **E-mailverzending weergeven.**</span><span class="sxs-lookup"><span data-stu-id="430b0-166">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Submissions**.</span></span> <span data-ttu-id="430b0-167">In deze weergave ziet u e-mail die gebruikers hebben gerapporteerd als ongewenste e-mail, geen ongewenste e-mail of phishing-e-mail.</span><span class="sxs-lookup"><span data-stu-id="430b0-167">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![E-mailberichten gerapporteerd door gebruikers](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="430b0-169">Klik **op Afzender** om uw lijst met weergaveopties te openen.</span><span class="sxs-lookup"><span data-stu-id="430b0-169">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="430b0-170">Gebruik deze lijst om gegevens weer te geven op afzender, geadresseerden, rapporttype (de gebruiker heeft vastgesteld dat de e-mail ongewenste e-mail was, geen ongewenste e-mail of phish) en meer.</span><span class="sxs-lookup"><span data-stu-id="430b0-170">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="430b0-171">Als u bijvoorbeeld informatie wilt weergeven over e-mailberichten die zijn gerapporteerd als phishingpogingen, klikt u op **Afzenderrapporttype,** selecteert u Phish en klikt u \> vervolgens op de knop Vernieuwen. </span><span class="sxs-lookup"><span data-stu-id="430b0-171">For example, to view information about email messages that were reported as phishing attempts, click **Sender** \> **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![Phish geselecteerd voor rapporttypefilter](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="430b0-173">Bekijk onder de grafiek meer informatie over specifieke e-mailberichten, zoals onderwerpregel, HET IP-adres van de afzender, de gebruiker die het bericht heeft gerapporteerd als ongewenste e-mail, geen ongewenste e-mail of phish, en meer.</span><span class="sxs-lookup"><span data-stu-id="430b0-173">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![Berichten die zijn gerapporteerd als phishingpogingen](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="430b0-175">Selecteer een item in de lijst om extra details weer te geven.</span><span class="sxs-lookup"><span data-stu-id="430b0-175">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="430b0-176">E-> Alle e-mail</span><span class="sxs-lookup"><span data-stu-id="430b0-176">Email > All email</span></span>

<span data-ttu-id="430b0-177">Als u dit rapport wilt bekijken, kiest u in Verkenner **De optie** \> **E-mail** \> **weergeven alle e-mail.**</span><span class="sxs-lookup"><span data-stu-id="430b0-177">To view this report, in Explorer, choose **View** \> **Email** \> **All mail**.</span></span> <span data-ttu-id="430b0-178">In deze weergaven ziet u een overzicht van e-mailactiviteit, inclusief e-mail die als schadelijk is geïdentificeerd vanwege phishing of malware, evenals alle niet-schadelijke e-mail (normale e-mail, spam en bulkmail).</span><span class="sxs-lookup"><span data-stu-id="430b0-178">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="430b0-179">Als u een foutmelding krijgt met te veel gegevens om weer te **geven,** voegt u een filter toe en beperkt u zo nodig het datumbereik dat u bekijkt.</span><span class="sxs-lookup"><span data-stu-id="430b0-179">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="430b0-180">Als u een filter wilt toepassen, kiest u **Afzender,** selecteert u een item in de lijst en klikt u vervolgens op de knop Vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="430b0-180">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="430b0-181">In ons voorbeeld hebben we **detectietechnologie gebruikt** als filter (er zijn verschillende opties beschikbaar).</span><span class="sxs-lookup"><span data-stu-id="430b0-181">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="430b0-182">Gegevens weergeven per afzender, het domein van de afzender, geadresseerden, onderwerp, bestandsnaam van bijlage, malwarefamilie, beveiligingsstatus (acties die zijn ondernomen door de functies en beleidsregels voor bedreigingsbeveiliging in Office 365), detectietechnologie (hoe de malware is gedetecteerd) en meer.</span><span class="sxs-lookup"><span data-stu-id="430b0-182">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![Gegevens over gedetecteerde e-mail weergeven met detectietechnologie](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="430b0-184">Bekijk onder de grafiek meer informatie over specifieke e-mailberichten, zoals onderwerpregel, geadresseerde, afzender, status, en dergelijke.</span><span class="sxs-lookup"><span data-stu-id="430b0-184">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="430b0-185">Inhoud > Malware</span><span class="sxs-lookup"><span data-stu-id="430b0-185">Content > Malware</span></span>

<span data-ttu-id="430b0-186">Als u dit rapport wilt bekijken, kiest u in Explorer (of realtime detecties) de optie  \> **Inhoudsmalware** \> **weergeven.**</span><span class="sxs-lookup"><span data-stu-id="430b0-186">To view this report, in Explorer (or real-time detections), choose **View** \> **Content** \> **Malware**.</span></span> <span data-ttu-id="430b0-187">In deze weergave ziet u bestanden die door Microsoft Defender zijn geïdentificeerd als schadelijk voor Office 365 [in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.](mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="430b0-187">This view shows files that were identified as malicious by [Microsoft Defender for Office 365 in SharePoint Online, OneDrive for Business, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="430b0-188">Informatie weergeven via malwarefamilie, detectietechnologie (hoe de malware is gedetecteerd) en werkbelasting (OneDrive, SharePoint of Teams).</span><span class="sxs-lookup"><span data-stu-id="430b0-188">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![Gegevens over gedetecteerde malware weergeven](../../media/malware-family.png)

<span data-ttu-id="430b0-190">Bekijk onder de grafiek meer informatie over specifieke bestanden, zoals bestandsnaam van bijlagen, werkbelasting, bestandsgrootte, wie het bestand het laatst heeft gewijzigd en meer.</span><span class="sxs-lookup"><span data-stu-id="430b0-190">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="430b0-191">Klik-en-filtermogelijkheden</span><span class="sxs-lookup"><span data-stu-id="430b0-191">Click-to-filter capabilities</span></span>

<span data-ttu-id="430b0-192">Met Explorer (en realtimedetecties) kunt u met één klik een filter toepassen.</span><span class="sxs-lookup"><span data-stu-id="430b0-192">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="430b0-193">Klik op een item in de legenda en dat item wordt een filter voor het rapport.</span><span class="sxs-lookup"><span data-stu-id="430b0-193">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="430b0-194">Stel dat we kijken naar de weergave Malware in Explorer:</span><span class="sxs-lookup"><span data-stu-id="430b0-194">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![Ga naar Threat Management \> Explorer](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="430b0-196">Als u in **deze grafiek op ATP-detonatie** klikt, ziet u de volgende weergave:</span><span class="sxs-lookup"><span data-stu-id="430b0-196">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![Explorer gefilterd om alleen Defender weer te geven Office 365 detonatieresultaten](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="430b0-198">In deze weergave bekijken we nu gegevens voor bestanden die zijn ontploft door Safe [Bijlagen.](safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="430b0-198">In this view, we are now looking at data for files that were detonated by [Safe Attachments](safe-attachments.md).</span></span> <span data-ttu-id="430b0-199">Onder de grafiek ziet u details over specifieke e-mailberichten met bijlagen die zijn gedetecteerd door Safe Bijlagen.</span><span class="sxs-lookup"><span data-stu-id="430b0-199">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![Specifieke details over e-mailberichten met gedetecteerde bijlagen](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="430b0-201">Als u een of meer items selecteert, wordt het **menu** Acties geactiveerd, waarin verschillende opties worden weergegeven waaruit u kunt kiezen voor het geselecteerde item(en).</span><span class="sxs-lookup"><span data-stu-id="430b0-201">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![Als u een item selecteert, wordt het menu Acties geactiveerd](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="430b0-203">De mogelijkheid om in een klik te filteren en naar specifieke details te navigeren, kan u veel tijd besparen bij het onderzoeken van bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="430b0-203">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="430b0-204">Query's en filters</span><span class="sxs-lookup"><span data-stu-id="430b0-204">Queries and filters</span></span>

<span data-ttu-id="430b0-205">Explorer (evenals het realtimedetectierapport) beschikt over verschillende krachtige filters en query's waarmee u kunt inzoomen op details, zoals de meest gerichte gebruikers, de beste malwarefamilies, detectietechnologie en meer.</span><span class="sxs-lookup"><span data-stu-id="430b0-205">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="430b0-206">Elk type rapport biedt verschillende manieren om gegevens weer te geven en te verkennen.</span><span class="sxs-lookup"><span data-stu-id="430b0-206">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="430b0-207">Gebruik geen jokertekens, zoals een sterretje of een vraagteken, in de querybalk voor Explorer (of realtime detecties).</span><span class="sxs-lookup"><span data-stu-id="430b0-207">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="430b0-208">Wanneer u in het veld **Onderwerp** zoekt naar e-mailberichten, worden in Verkenner (of realtimedetecties) gedeeltelijke overeenkomsten en resultaten weergegeven die lijken op een jokertekenzoekactie.</span><span class="sxs-lookup"><span data-stu-id="430b0-208">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
