---
title: Meldings- en berichttracering in Exchange Online Protection
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: Microsoft Exchange Online Protection (EOP) biedt veel verschillende rapporten waarmee u de algehele status en status van uw organisatie bepalen. Er zijn ook hulpmiddelen om u te helpen bij het oplossen van specifieke gebeurtenissen (zoals een bericht dat niet bij de beoogde ontvangers aankomt) en controlerapporten om te helpen voldoen aan de nalevingsvereisten. In de volgende tabel worden de rapporten en hulpmiddelen voor probleemoplossing beschreven die beschikbaar zijn voor EOP-beheerders.
ms.openlocfilehash: 282fd032e73ccb8217801a575f6029dbd9fadc9c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42806295"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a><span data-ttu-id="275bc-105">Meldings- en berichttracering in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="275bc-105">Reporting and message trace in Exchange Online Protection</span></span>

<span data-ttu-id="275bc-106">Microsoft Exchange Online Protection (EOP) biedt veel verschillende rapporten waarmee u de algehele status en status van uw organisatie bepalen.</span><span class="sxs-lookup"><span data-stu-id="275bc-106">Microsoft Exchange Online Protection (EOP) offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="275bc-107">Er zijn ook hulpmiddelen om u te helpen bij het oplossen van specifieke gebeurtenissen (zoals een bericht dat niet bij de beoogde ontvangers aankomt) en controlerapporten om te helpen voldoen aan de nalevingsvereisten.</span><span class="sxs-lookup"><span data-stu-id="275bc-107">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="275bc-108">Gebruiksrapporten</span><span class="sxs-lookup"><span data-stu-id="275bc-108">Usage reports</span></span>

<span data-ttu-id="275bc-109">**Activiteit in Office 365-groepen:** informatie weergeven over het aantal Office 365-groepen dat is gemaakt en gebruikt.</span><span class="sxs-lookup"><span data-stu-id="275bc-109">**Office 365 groups activity**: View information about the number of Office 365 groups that are created and used.</span></span>

<span data-ttu-id="275bc-110">**E-mailactiviteit:** bekijk informatie over het aantal verzonden, ontvangen en gelezen berichten in uw hele organisatie en door specifieke gebruikers.</span><span class="sxs-lookup"><span data-stu-id="275bc-110">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="275bc-111">**Gebruik van e-mailapps:** bekijk informatie over de gebruikte e-mailapps.</span><span class="sxs-lookup"><span data-stu-id="275bc-111">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="275bc-112">Dit omvat het totale aantal verbindingen voor elke app en de versies van Outlook die verbinding maken.</span><span class="sxs-lookup"><span data-stu-id="275bc-112">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="275bc-113">**Postvakgebruik**: Bekijk informatie over gebruikte opslag, quotumverbruik, artikeltelling en laatste activiteit (verzenden of lezen van activiteiten) voor postvakken.</span><span class="sxs-lookup"><span data-stu-id="275bc-113">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="275bc-114">Zie de volgende bronnen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="275bc-114">See the following resources for more information:</span></span>

- [<span data-ttu-id="275bc-115">Office 365-rapporten in het beheercentrum - Office 365-groepen</span><span class="sxs-lookup"><span data-stu-id="275bc-115">Office 365 Reports in the admin center - Office 365 groups</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="275bc-116">Office 365-rapporten in het beheercentrum - e-mailactiviteit</span><span class="sxs-lookup"><span data-stu-id="275bc-116">Office 365 Reports in the Admin Center - Email activity</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/email-activity)

- [<span data-ttu-id="275bc-117">Office 365-rapporten in het beheercentrum - gebruik van e-mailapps</span><span class="sxs-lookup"><span data-stu-id="275bc-117">Office 365 Reports in the Admin Center - Email apps usage</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="275bc-118">Office 365-rapporten in het beheercentrum - Postvakgebruik</span><span class="sxs-lookup"><span data-stu-id="275bc-118">Office 365 Reports in the Admin Center - Mailbox usage</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="275bc-119">Beveiligingsrapporten & naleving in het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="275bc-119">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="275bc-120">Deze verbeterde rapporten bieden een interactieve rapportage-ervaring voor EOP-beheerders, waaronder beknopte informatie, en de mogelijkheid om in te zoomen voor meer details.</span><span class="sxs-lookup"><span data-stu-id="275bc-120">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="275bc-121">**Advanced Threat Protection (ATP)**: Bekijk informatie over veilige koppelingen en veilige bijlagen die deel uitmaken van ATP.</span><span class="sxs-lookup"><span data-stu-id="275bc-121">**Advanced Threat Protection (ATP)**: View information about safe links and safe attachments that are part of ATP.</span></span>

<span data-ttu-id="275bc-122">**EOP:** Bekijk informatie over malwaredetecties, vervalste e-mail, spamdetecties en e-mailstroom van en naar uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="275bc-122">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="275bc-123">Rapporten weergeven voor geavanceerde bedreigingsbeveiliging van Office 365</span><span class="sxs-lookup"><span data-stu-id="275bc-123">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="275bc-124">Aangepaste rapporten met Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="275bc-124">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="275bc-125">Maak programmatisch rapporten die beschikbaar zijn in het Microsoft 365-beheercentrum met Behulp van Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="275bc-125">Programmatically create reports that are available in the Microsoft 365 admin center by using Microsoft Graph.</span></span> <span data-ttu-id="275bc-126">Bekijk de subonderwerpen [van Werken met Office 365-gebruiksrapporten in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span><span class="sxs-lookup"><span data-stu-id="275bc-126">See the subtopics of [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="275bc-127">Aangepaste rapporten met Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="275bc-127">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="275bc-128">Programmatisch rapporten maken.</span><span class="sxs-lookup"><span data-stu-id="275bc-128">Programmatically create reports.</span></span> <span data-ttu-id="275bc-129">Zie [Overzicht van Microsoft Graph](https://docs.microsoft.com/graph/overview).</span><span class="sxs-lookup"><span data-stu-id="275bc-129">See [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>

## <a name="message-trace"></a><span data-ttu-id="275bc-130">Berichttracering</span><span class="sxs-lookup"><span data-stu-id="275bc-130">Message trace</span></span>

<span data-ttu-id="275bc-131">Volgt e-mailberichten terwijl ze door EOP reizen.</span><span class="sxs-lookup"><span data-stu-id="275bc-131">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="275bc-132">U bepalen of een e-mailbericht is ontvangen, afgewezen, uitgesteld of door de service is bezorgd.</span><span class="sxs-lookup"><span data-stu-id="275bc-132">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="275bc-133">Het laat ook zien welke acties zijn ondernomen op het bericht voordat het zijn definitieve status bereikte.</span><span class="sxs-lookup"><span data-stu-id="275bc-133">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="275bc-134">U deze informatie gebruiken om de vragen van uw gebruiker efficiënt te beantwoorden, problemen met de mailstroom op te lossen, beleidswijzigingen te valideren en de noodzaak om contact op te nemen met technische ondersteuning voor hulp te verlichten.</span><span class="sxs-lookup"><span data-stu-id="275bc-134">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="275bc-135">Zie [Een e-mailbericht traceren](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)</span><span class="sxs-lookup"><span data-stu-id="275bc-135">See [Trace an email message](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)</span></span>

## <a name="audit-logging"></a><span data-ttu-id="275bc-136">Controlelogboekregistratie</span><span class="sxs-lookup"><span data-stu-id="275bc-136">Audit logging</span></span>

<span data-ttu-id="275bc-137">Houdt specifieke wijzigingen bij die door beheerders in uw organisatie zijn aangebracht.</span><span class="sxs-lookup"><span data-stu-id="275bc-137">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="275bc-138">Met deze rapporten u configuratieproblemen oplossen of de oorzaak van beveiligings- of nalevingsgerelateerde problemen vinden.</span><span class="sxs-lookup"><span data-stu-id="275bc-138">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="275bc-139">Zie [Controlerapporten in EOP](auditing-reports-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="275bc-139">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="275bc-140">Beschikbaarheid en latentie van gegevens voor rapportage en berichttraceer</span><span class="sxs-lookup"><span data-stu-id="275bc-140">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="275bc-141">In de volgende tabel wordt beschreven wanneer eop-rapportage- en berichttraceringsgegevens beschikbaar zijn en voor hoe lang.</span><span class="sxs-lookup"><span data-stu-id="275bc-141">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="275bc-142">**Rapporttype**</span><span class="sxs-lookup"><span data-stu-id="275bc-142">**Report type**</span></span>|<span data-ttu-id="275bc-143">**Beschikbare gegevens voor (terugblikperiode)**</span><span class="sxs-lookup"><span data-stu-id="275bc-143">**Data available for (look back period)**</span></span>|<span data-ttu-id="275bc-144">**Latency**</span><span class="sxs-lookup"><span data-stu-id="275bc-144">**Latency**</span></span>|
|<span data-ttu-id="275bc-145">Overzichtsrapporten voor e-mailbeveiliging</span><span class="sxs-lookup"><span data-stu-id="275bc-145">Mail protection summary reports</span></span>|<span data-ttu-id="275bc-146">90 dagen</span><span class="sxs-lookup"><span data-stu-id="275bc-146">90 days</span></span>|<span data-ttu-id="275bc-147">De aggregatie van berichtgegevens is meestal binnen 24-48 uur voltooid.</span><span class="sxs-lookup"><span data-stu-id="275bc-147">Message data aggregation is mostly complete within 24-48 hours.</span></span> <span data-ttu-id="275bc-148">Enkele kleine incrementele geaggregeerde wijzigingen kunnen maximaal 5 dagen voorkomen.</span><span class="sxs-lookup"><span data-stu-id="275bc-148">Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="275bc-149">Detailrapporten voor e-mailbeveiliging</span><span class="sxs-lookup"><span data-stu-id="275bc-149">Mail protection detail reports</span></span>|<span data-ttu-id="275bc-150">90 dagen</span><span class="sxs-lookup"><span data-stu-id="275bc-150">90 days</span></span>|<span data-ttu-id="275bc-151">Voor detailgegevens die minder dan 7 dagen oud zijn, moeten gegevens binnen 24 uur worden weergegeven, maar mogelijk pas na 48 uur volledig zijn.</span><span class="sxs-lookup"><span data-stu-id="275bc-151">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours.</span></span> <span data-ttu-id="275bc-152">Enkele kleine incrementele wijzigingen kunnen maximaal 5 dagen voorkomen.</span><span class="sxs-lookup"><span data-stu-id="275bc-152">Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="275bc-153">Als u detailrapporten wilt weergeven voor berichten die meer dan 7 dagen oud zijn, kunnen de resultaten enkele uren duren.</span><span class="sxs-lookup"><span data-stu-id="275bc-153">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="275bc-154">Gegevens over berichttracering</span><span class="sxs-lookup"><span data-stu-id="275bc-154">Message trace data</span></span>|<span data-ttu-id="275bc-155">90 dagen</span><span class="sxs-lookup"><span data-stu-id="275bc-155">90 days</span></span>|<span data-ttu-id="275bc-156">Wanneer u een berichttracering uitvoert voor berichten die minder dan 7 dagen oud zijn, moeten de berichten binnen 5-30 minuten worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="275bc-156">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="275bc-157">Wanneer u een berichttracering uitvoert voor berichten die meer dan 7 dagen oud zijn, kunnen de resultaten enkele uren duren.</span><span class="sxs-lookup"><span data-stu-id="275bc-157">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|

> [!NOTE]
> <span data-ttu-id="275bc-158">Beschikbaarheid en latentie van gegevens is hetzelfde, ongeacht of deze worden aangevraagd via het Microsoft 365-beheercentrum of externe PowerShell.</span><span class="sxs-lookup"><span data-stu-id="275bc-158">Data availability and latency is the same whether requested via the Microsoft 365 admin center or remote PowerShell.</span></span>
