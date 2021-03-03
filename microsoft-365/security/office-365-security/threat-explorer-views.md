---
title: Weergaven in Bedreigingsverkenner en realtime detecties
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
description: Meer informatie over het gebruik van Bedreigingsverkenner en het rapport detecties in realtime om bedreigingen te onderzoeken en te beantwoorden in het beveiligings- & compliancecentrum.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b00b78432a34ec982208586f2fe19c1588354293
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406478"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="d4c10-103">Weergaven in Bedreigingsverkenner en realtime detecties</span><span class="sxs-lookup"><span data-stu-id="d4c10-103">Views in Threat Explorer and real-time detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d4c10-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="d4c10-104">**Applies to**</span></span>
- [<span data-ttu-id="d4c10-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="d4c10-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="d4c10-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d4c10-106">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)


![Bedreigingsverkenner](../../media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="d4c10-108">[Bedreigingsverkenner](threat-explorer.md) (en het rapport realtime detecties) is een krachtig, bijna realtime hulpmiddel waarmee teams met beveiligingsbewerkingen bedreigingen kunnen onderzoeken en reageren op bedreigingen in het beveiligings- & compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="d4c10-108">[Threat Explorer](threat-explorer.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security & Compliance Center.</span></span> <span data-ttu-id="d4c10-109">Explorer (en het rapport realtime detecties) geeft informatie weer over verdachte malware en phish in e-mail en bestanden in Office 365, evenals andere beveiligingsrisico's en risico's voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d4c10-109">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span>

- <span data-ttu-id="d4c10-110">Als u [Microsoft Defender voor Office 365-abonnement](office-365-atp.md) 2 hebt, hebt u Explorer.</span><span class="sxs-lookup"><span data-stu-id="d4c10-110">If you have [Microsoft Defender for Office 365](office-365-atp.md) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="d4c10-111">Als u Microsoft Defender voor Office 365-abonnement 1 hebt, hebt u detecties in realtime.</span><span class="sxs-lookup"><span data-stu-id="d4c10-111">If you have Microsoft Defender for Office 365 Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="d4c10-112">Wanneer u Explorer (of het rapport realtime detecties) voor het eerst opent, ziet u in de standaardweergave malwaredetecties voor e-mail van de afgelopen zeven dagen.</span><span class="sxs-lookup"><span data-stu-id="d4c10-112">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="d4c10-113">Dit rapport kan ook Microsoft Defender voor Office 365-detecties tonen, zoals schadelijke URL's gedetecteerd door veilige koppelingen [en](atp-safe-links.md)schadelijke bestanden gedetecteerd door [veilige bijlagen.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="d4c10-113">This report can also show Microsoft Defender for Office 365 detections, such as malicious URLs detected by [Safe Links](atp-safe-links.md), and malicious files detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="d4c10-114">Dit rapport kan worden gewijzigd om gegevens voor de afgelopen 30 dagen weer te geven (met een betaald abonnement op Microsoft Defender voor Office 365 P2).</span><span class="sxs-lookup"><span data-stu-id="d4c10-114">This report can be modified to show data for the past 30 days (with a Microsoft Defender for Office 365 P2 paid subscription).</span></span> <span data-ttu-id="d4c10-115">Proefabonnementen bevatten alleen gegevens van de afgelopen zeven dagen.</span><span class="sxs-lookup"><span data-stu-id="d4c10-115">Trial subscriptions will include data for the past seven days only.</span></span>

****

|<span data-ttu-id="d4c10-116">Abonnement</span><span class="sxs-lookup"><span data-stu-id="d4c10-116">Subscription</span></span>|<span data-ttu-id="d4c10-117">Hulpprogramma</span><span class="sxs-lookup"><span data-stu-id="d4c10-117">Utility</span></span>|<span data-ttu-id="d4c10-118">Dagen van gegevens</span><span class="sxs-lookup"><span data-stu-id="d4c10-118">Days of Data</span></span>|
|---|---|---|
|<span data-ttu-id="d4c10-119">Proefversie van Microsoft Defender voor Office 365 P1</span><span class="sxs-lookup"><span data-stu-id="d4c10-119">Microsoft Defender for Office 365 P1 trial</span></span>|<span data-ttu-id="d4c10-120">Detecties in realtime</span><span class="sxs-lookup"><span data-stu-id="d4c10-120">Real-time detections</span></span>|<span data-ttu-id="d4c10-121">7</span><span class="sxs-lookup"><span data-stu-id="d4c10-121">7</span></span>|
|<span data-ttu-id="d4c10-122">Betaalde Microsoft Defender voor Office 365 P1</span><span class="sxs-lookup"><span data-stu-id="d4c10-122">Microsoft Defender for Office 365 P1 paid</span></span>|<span data-ttu-id="d4c10-123">Detecties in realtime</span><span class="sxs-lookup"><span data-stu-id="d4c10-123">Real-time detections</span></span>|<span data-ttu-id="d4c10-124">30</span><span class="sxs-lookup"><span data-stu-id="d4c10-124">30</span></span>|
|<span data-ttu-id="d4c10-125">Betaalde testversie van Defender voor Office 365 P1 met Microsoft Defender voor Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="d4c10-125">Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="d4c10-126">Bedreigingsverkenner</span><span class="sxs-lookup"><span data-stu-id="d4c10-126">Threat Explorer</span></span>|<span data-ttu-id="d4c10-127">7</span><span class="sxs-lookup"><span data-stu-id="d4c10-127">7</span></span>|
|<span data-ttu-id="d4c10-128">Proefversie van Microsoft Defender voor Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="d4c10-128">Microsoft Defender for Office 365 P2 trial</span></span>|<span data-ttu-id="d4c10-129">Bedreigingsverkenner</span><span class="sxs-lookup"><span data-stu-id="d4c10-129">Threat Explorer</span></span>|<span data-ttu-id="d4c10-130">7</span><span class="sxs-lookup"><span data-stu-id="d4c10-130">7</span></span>|
|<span data-ttu-id="d4c10-131">Betaalde Microsoft Defender voor Office 365 P2</span><span class="sxs-lookup"><span data-stu-id="d4c10-131">Microsoft Defender for Office 365 P2 paid</span></span>|<span data-ttu-id="d4c10-132">Bedreigingsverkenner</span><span class="sxs-lookup"><span data-stu-id="d4c10-132">Threat Explorer</span></span>|<span data-ttu-id="d4c10-133">30</span><span class="sxs-lookup"><span data-stu-id="d4c10-133">30</span></span>|
|

> [!NOTE]
> <span data-ttu-id="d4c10-134">De bewaar- en zoeklimiet voor proeften tenants wordt binnenkort uitgebreid van 7 naar 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="d4c10-134">We will soon be extending the Explorer (and Real-time detections) data retention and search limit for trial tenants from 7 to 30 days.</span></span> <span data-ttu-id="d4c10-135">Deze wijziging wordt bijgehouden als onderdeel van roadmap-item 70544 en is momenteel in een fase van implementatie.</span><span class="sxs-lookup"><span data-stu-id="d4c10-135">This change is being tracked as part of roadmap item no. 70544, and is currently in a roll-out phase.</span></span>

<span data-ttu-id="d4c10-136">Gebruik **het** menu Beeld om te wijzigen welke informatie wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="d4c10-136">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="d4c10-137">Met knopinfo kunt u bepalen welke weergave u wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d4c10-137">Tooltips help you determine which view to use.</span></span>

![Menu Beeld van Bedreigingsverkenner](../../media/ThreatExplorerViewMenu.png)

<span data-ttu-id="d4c10-139">Nadat u een weergave hebt geselecteerd, kunt u filters toepassen en query's instellen voor verdere analyse.</span><span class="sxs-lookup"><span data-stu-id="d4c10-139">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="d4c10-140">De volgende secties bieden een kort overzicht van de verschillende weergaven die beschikbaar zijn in Verkenner (of realtime detecties).</span><span class="sxs-lookup"><span data-stu-id="d4c10-140">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>

## <a name="email--malware"></a><span data-ttu-id="d4c10-141">E-> Malware</span><span class="sxs-lookup"><span data-stu-id="d4c10-141">Email > Malware</span></span>

<span data-ttu-id="d4c10-142">Als u dit rapport wilt bekijken, kiest u In Verkenner (of realtime detecties) De optie **E-mailmalware** \>  \> **weergeven.**</span><span class="sxs-lookup"><span data-stu-id="d4c10-142">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Malware**.</span></span> <span data-ttu-id="d4c10-143">Deze weergave toont informatie over e-mailberichten die zijn geïdentificeerd als malware.</span><span class="sxs-lookup"><span data-stu-id="d4c10-143">This view shows information about email messages that were identified as containing malware.</span></span>

![Gegevens weergeven over e-mail die is geïdentificeerd als malware](../../media/ExplorerEmailMalwareMenu.png)

<span data-ttu-id="d4c10-145">Klik **op Afzender** om de lijst met weergaveopties te openen.</span><span class="sxs-lookup"><span data-stu-id="d4c10-145">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="d4c10-146">Gebruik deze lijst om gegevens weer te geven op afzender, geadresseerden, domein van afzender, onderwerp, detectietechnologie, beveiligingsstatus en meer.</span><span class="sxs-lookup"><span data-stu-id="d4c10-146">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span>

<span data-ttu-id="d4c10-147">Als u bijvoorbeeld wilt zien welke acties zijn ondernomen bij gedetecteerde e-mailberichten, kiest u **Beveiligingsstatus** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="d4c10-147">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="d4c10-148">Selecteer een optie en klik vervolgens op de knop Vernieuwen om dat filter toe te passen op het rapport.</span><span class="sxs-lookup"><span data-stu-id="d4c10-148">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![Opties voor Status van bedreigingsbeveiliging voor Bedreigingsverkenner](../../media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="d4c10-150">Bekijk onder de grafiek meer details over specifieke berichten.</span><span class="sxs-lookup"><span data-stu-id="d4c10-150">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="d4c10-151">Wanneer u een item in de lijst selecteert, wordt er een uitvliegend deelvenster geopend, waar u meer informatie kunt vinden over het geselecteerde item.</span><span class="sxs-lookup"><span data-stu-id="d4c10-151">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Bedreigingsverkenner met geopende flyout](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="d4c10-153">E-> Phish</span><span class="sxs-lookup"><span data-stu-id="d4c10-153">Email > Phish</span></span>

<span data-ttu-id="d4c10-154">Als u dit rapport wilt bekijken, kiest u  In Verkenner (of realtime detecties) \> **E-mail** \> **phish weergeven.**</span><span class="sxs-lookup"><span data-stu-id="d4c10-154">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Phish**.</span></span> <span data-ttu-id="d4c10-155">In deze weergave ziet u e-mailberichten die zijn geïdentificeerd als phishing-pogingen.</span><span class="sxs-lookup"><span data-stu-id="d4c10-155">This view shows email messages identified as phishing attempts.</span></span>

![Gegevens weergeven over e-mailberichten die zijn geïdentificeerd als phishingpogingen](../../media/ThreatExplorerEmailPhish.png)

<span data-ttu-id="d4c10-157">Klik **op Afzender** om de lijst met weergaveopties te openen.</span><span class="sxs-lookup"><span data-stu-id="d4c10-157">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="d4c10-158">Gebruik deze lijst om gegevens weer te geven per afzender, geadresseerden, afzenderdomein, AFZENDER-IP, URL-domein, klik op gemaakt en meer.</span><span class="sxs-lookup"><span data-stu-id="d4c10-158">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span>

<span data-ttu-id="d4c10-159">Als u bijvoorbeeld wilt zien welke acties zijn ondernomen wanneer personen op URL's klikken die zijn aangemerkt als phishing-pogingen, kiest u Klik op naam **in** de lijst, selecteert u een of meer opties en klikt u vervolgens op de knop Vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="d4c10-159">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![Klik op opties voor de opties voor het phish-rapport](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="d4c10-161">Onder de grafiek vindt u meer informatie over specifieke berichten, klikken op URL's, URL's en e-mail origin.</span><span class="sxs-lookup"><span data-stu-id="d4c10-161">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span>

![URL's gedetecteerd als phish in e-mailberichten](../../media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="d4c10-163">Wanneer u een item in de lijst selecteert, zoals een URL die is gedetecteerd, wordt een fly-outvenster geopend, waarin u meer informatie vindt over het geselecteerde item.</span><span class="sxs-lookup"><span data-stu-id="d4c10-163">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span>

![Details over een gedetecteerde URL](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a><span data-ttu-id="d4c10-165">E> mail inzendingen</span><span class="sxs-lookup"><span data-stu-id="d4c10-165">Email > Submissions</span></span>

<span data-ttu-id="d4c10-166">Als u dit rapport wilt bekijken, kiest u in Verkenner (of realtime detecties) **E-mailinzending** \>  \> **weergeven.**</span><span class="sxs-lookup"><span data-stu-id="d4c10-166">To view this report, in Explorer (or real-time detections), choose **View** \> **Email** \> **Submissions**.</span></span> <span data-ttu-id="d4c10-167">In deze weergave ziet u e-mail die gebruikers hebben gerapporteerd als ongewenste e-mail, geen ongewenste e-mail of phishing-e-mail.</span><span class="sxs-lookup"><span data-stu-id="d4c10-167">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>

![E-mailberichten gerapporteerd door gebruikers](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

<span data-ttu-id="d4c10-169">Klik **op Afzender** om de lijst met weergaveopties te openen.</span><span class="sxs-lookup"><span data-stu-id="d4c10-169">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="d4c10-170">Gebruik deze lijst om informatie weer te geven per afzender, geadresseerde, rapporttype (de mening van de gebruiker dat het e-mailbericht ongewenst is, geen ongewenste e-mail of phish), en meer.</span><span class="sxs-lookup"><span data-stu-id="d4c10-170">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span>

<span data-ttu-id="d4c10-171">Als u bijvoorbeeld informatie wilt weergeven over e-mailberichten die zijn gerapporteerd als phishing-pogingen, klikt u op Rapporttype afzender, selecteert u  Phish en klikt u vervolgens op \> de knop Vernieuwen. </span><span class="sxs-lookup"><span data-stu-id="d4c10-171">For example, to view information about email messages that were reported as phishing attempts, click **Sender** \> **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![Phish selected for Report Type filter](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="d4c10-173">Onder de grafiek kunt u meer details bekijken over specifieke e-mailberichten, zoals de onderwerpregel, het IP-adres van de afzender, de gebruiker die het bericht heeft gerapporteerd als ongewenste e-mail, geen ongewenste e-mail of phish, en meer.</span><span class="sxs-lookup"><span data-stu-id="d4c10-173">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span>

![Berichten die zijn gerapporteerd als phishing-pogingen](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="d4c10-175">Selecteer een item in de lijst om aanvullende details weer te geven.</span><span class="sxs-lookup"><span data-stu-id="d4c10-175">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="d4c10-176">E-> e-mail verzenden</span><span class="sxs-lookup"><span data-stu-id="d4c10-176">Email > All email</span></span>

<span data-ttu-id="d4c10-177">Als u dit rapport wilt bekijken, kiest u in Verkenner **E-mail** \>  \> **weergeven alle e-mail.**</span><span class="sxs-lookup"><span data-stu-id="d4c10-177">To view this report, in Explorer, choose **View** \> **Email** \> **All mail**.</span></span> <span data-ttu-id="d4c10-178">In deze weergaven ziet u een overzicht van alle e-mailactiviteiten, waaronder e-mail die is geïdentificeerd als schadelijk vanwege phishing of malware, en alle niet-schadelijke e-mail (normale e-mail, spam en bulkmail).</span><span class="sxs-lookup"><span data-stu-id="d4c10-178">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span>

> [!NOTE]
> <span data-ttu-id="d4c10-179">Als u een foutbericht krijgt met de tekst Te veel gegevens om weer te **geven,** voegt u een filter toe en beperkt u zo nodig het datumbereik dat u bekijkt.</span><span class="sxs-lookup"><span data-stu-id="d4c10-179">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span>

<span data-ttu-id="d4c10-180">Als u een filter wilt toepassen, kiest **u Afzender,** selecteert u een item in de lijst en klikt u op de knop Vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="d4c10-180">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="d4c10-181">In ons voorbeeld hebben we **Detectietechnologie als** filter gebruikt (er zijn verschillende opties beschikbaar).</span><span class="sxs-lookup"><span data-stu-id="d4c10-181">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="d4c10-182">Gegevens weergeven per afzender, het domein van de afzender, geadresseerden, onderwerp, bestandsnaam van bijlage, malwarefamilie, beveiligingsstatus (acties die zijn ondernomen door de functies en beleidsregels voor bedreigingsbeveiliging in Office 365), detectietechnologie (hoe de malware is gedetecteerd) en meer.</span><span class="sxs-lookup"><span data-stu-id="d4c10-182">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span>

![Gegevens over gedetecteerde e-mail weergeven met detectietechnologie](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

<span data-ttu-id="d4c10-184">Bekijk onder de grafiek meer details over specifieke e-mailberichten, zoals onderwerpregel, geadresseerde, afzender, status, en dergelijke.</span><span class="sxs-lookup"><span data-stu-id="d4c10-184">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span>

## <a name="content--malware"></a><span data-ttu-id="d4c10-185">Inhoud > Malware</span><span class="sxs-lookup"><span data-stu-id="d4c10-185">Content > Malware</span></span>

<span data-ttu-id="d4c10-186">Als u dit rapport wilt bekijken, kiest u In Verkenner (of realtime detecties) **Inhoudsmalware** \>  \> **weergeven.**</span><span class="sxs-lookup"><span data-stu-id="d4c10-186">To view this report, in Explorer (or real-time detections), choose **View** \> **Content** \> **Malware**.</span></span> <span data-ttu-id="d4c10-187">In deze weergave ziet u bestanden die zijn geïdentificeerd als schadelijk door Microsoft Defender voor [Office 365 in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams.](atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="d4c10-187">This view shows files that were identified as malicious by [Microsoft Defender for Office 365 in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="d4c10-188">Bekijk informatie via malwarefamilie, detectietechnologie (hoe de malware is gedetecteerd) en werkbelasting (OneDrive, SharePoint of Teams).</span><span class="sxs-lookup"><span data-stu-id="d4c10-188">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span>

![Gegevens over gedetecteerde malware weergeven](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

<span data-ttu-id="d4c10-190">Bekijk onder de grafiek meer details over specifieke bestanden, zoals de bestandsnaam van de bijlage, de werkbelasting, de bestandsgrootte, wie het bestand het laatst heeft gewijzigd en meer.</span><span class="sxs-lookup"><span data-stu-id="d4c10-190">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span>

## <a name="click-to-filter-capabilities"></a><span data-ttu-id="d4c10-191">Klik-en-filtermogelijkheden</span><span class="sxs-lookup"><span data-stu-id="d4c10-191">Click-to-filter capabilities</span></span>

<span data-ttu-id="d4c10-192">Met Explorer (en realtime detecties) kunt u met één klik een filter toepassen.</span><span class="sxs-lookup"><span data-stu-id="d4c10-192">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="d4c10-193">Als u op een item in de legenda klikt, wordt dat item een filter voor het rapport.</span><span class="sxs-lookup"><span data-stu-id="d4c10-193">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="d4c10-194">Stel dat we naar de weergave Malware in Verkenner kijken:</span><span class="sxs-lookup"><span data-stu-id="d4c10-194">For example, suppose we are looking at the Malware view in Explorer:</span></span>

![Ga naar \> BedreigingsbeheerVerkenner](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="d4c10-196">Als u **op ATP-detonatie** in deze grafiek klikt, ziet dit er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="d4c10-196">Clicking **ATP Detonation** in this chart results in a view like this:</span></span>

![Verkenner gefilterd om alleen Defender voor office 365-detonatieresultaten weer te geven](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

<span data-ttu-id="d4c10-198">In deze weergave kijken we nu naar gegevens over bestanden die zijn gedetoneerd met [veilige bijlagen.](atp-safe-attachments.md)</span><span class="sxs-lookup"><span data-stu-id="d4c10-198">In this view, we are now looking at data for files that were detonated by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="d4c10-199">Onder de grafiek ziet u details over specifieke e-mailberichten met bijlagen die door veilige bijlagen zijn gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="d4c10-199">Below the chart, we can see details about specific email messages that had attachments that were detected by Safe Attachments.</span></span>

![Specifieke details over e-mailberichten met gedetecteerde bijlagen](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

<span data-ttu-id="d4c10-201">Als u een of meer items selecteert, wordt het **menu** Acties geactiveerd. Het menu biedt verschillende keuzemogelijkheden waaruit u kunt kiezen voor de geselecteerde items.</span><span class="sxs-lookup"><span data-stu-id="d4c10-201">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span>

![Als u een item selecteert, wordt het menu Acties geactiveerd](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

<span data-ttu-id="d4c10-203">De mogelijkheid om te filteren met één klik en naar specifieke details te gaan, kan u veel tijd besparen bij het onderzoeken van bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="d4c10-203">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="d4c10-204">Query's en filters</span><span class="sxs-lookup"><span data-stu-id="d4c10-204">Queries and filters</span></span>

<span data-ttu-id="d4c10-205">Explorer (evenals het rapport realtime detecties) beschikt over verschillende krachtige filters en querymogelijkheden waarmee u in detail kunt inzoomen, zoals topgebruikers, de belangrijkste malwarefamilies, detectietechnologie en meer.</span><span class="sxs-lookup"><span data-stu-id="d4c10-205">Explorer (as well as the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="d4c10-206">Elk type rapport biedt verschillende manieren om gegevens weer te geven en te verkennen.</span><span class="sxs-lookup"><span data-stu-id="d4c10-206">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4c10-207">Gebruik geen jokertekens, zoals een sterretje of vraagteken, in de querybalk voor Verkenner (of realtime detecties).</span><span class="sxs-lookup"><span data-stu-id="d4c10-207">Do not use wildcard characters, such as an asterisk or a question mark, in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="d4c10-208">Wanneer u in  het veld Onderwerp zoekt naar e-mailberichten, zal Explorer (of realtime detecties) gedeeltelijke overeenkomende resultaten uitvoeren en resultaten opleveren die vergelijkbaar zijn met een zoekopdracht met een jokerteken.</span><span class="sxs-lookup"><span data-stu-id="d4c10-208">When you search on the **Subject field** for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
