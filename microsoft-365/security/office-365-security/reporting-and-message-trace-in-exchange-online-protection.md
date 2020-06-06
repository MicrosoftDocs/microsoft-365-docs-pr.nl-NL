---
title: Rapportage en berichttracering
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
ms.custom:
- seo-marvel-apr2020
description: In dit artikel vindt u meer informatie over rapporten en hulpprogramma's voor het oplossen van problemen die beschikbaar zijn voor EOP-beheerders (Microsoft Exchange Online Protection).
ms.openlocfilehash: b33d343d9b7f02e32619031d3ecf72ad12f891fd
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588166"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="3b284-103">Rapportage en berichttracering in EOP</span><span class="sxs-lookup"><span data-stu-id="3b284-103">Reporting and message trace in EOP</span></span>

<span data-ttu-id="3b284-104">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken biedt EOP veel verschillende rapporten die u kunnen helpen de algehele status en status van uw organisatie te bepalen.</span><span class="sxs-lookup"><span data-stu-id="3b284-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="3b284-105">Er zijn ook hulpmiddelen om u te helpen specifieke gebeurtenissen op te lossen (zoals een bericht dat niet aan de beoogde ontvangers wordt verzonden) en controlerapporten om te helpen bij nalevingsvereisten.</span><span class="sxs-lookup"><span data-stu-id="3b284-105">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="3b284-106">Gebruiksrapporten</span><span class="sxs-lookup"><span data-stu-id="3b284-106">Usage reports</span></span>

<span data-ttu-id="3b284-107">**Activiteit van Microsoft 365-groepen**: Bekijk informatie over het aantal Microsoft 365-groepen dat is gemaakt en gebruikt.</span><span class="sxs-lookup"><span data-stu-id="3b284-107">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="3b284-108">**E-mailactiviteit**: Bekijk informatie over het aantal verzonden, ontvangen en gelezen berichten in uw hele organisatie en door specifieke gebruikers.</span><span class="sxs-lookup"><span data-stu-id="3b284-108">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="3b284-109">**Gebruik van e-mailapps**: Bekijk informatie over de e-mail-apps die worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="3b284-109">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="3b284-110">Dit omvat het totale aantal verbindingen voor elke app en de versies van Outlook die verbinding maken.</span><span class="sxs-lookup"><span data-stu-id="3b284-110">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="3b284-111">**Postvakgebruik**: Bekijk informatie over gebruikte opslag, quotumverbruik, aantal items en laatste activiteit (verzenden of lezen activiteit) voor postvakken.</span><span class="sxs-lookup"><span data-stu-id="3b284-111">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="3b284-112">Zie de volgende bronnen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="3b284-112">See the following resources for more information:</span></span>

- [<span data-ttu-id="3b284-113">Microsoft 365-rapporten in het beheercentrum - Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="3b284-113">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="3b284-114">Microsoft 365-rapporten in het beheercentrum - E-mailactiviteit</span><span class="sxs-lookup"><span data-stu-id="3b284-114">Microsoft 365 Reports in the admin center - Email activity</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [<span data-ttu-id="3b284-115">Microsoft 365-rapporten in het beheercentrum - Gebruik van e-mailapps</span><span class="sxs-lookup"><span data-stu-id="3b284-115">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="3b284-116">Microsoft 365-rapporten in het beheercentrum - Gebruik postvak</span><span class="sxs-lookup"><span data-stu-id="3b284-116">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="3b284-117">Nalevingsrapporten voor beveiligings & in het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="3b284-117">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="3b284-118">Deze verbeterde rapporten bieden een interactieve rapportage-ervaring voor EOP-beheerders, die beknopte informatie bevat, en de mogelijkheid om in te zoomen voor meer details.</span><span class="sxs-lookup"><span data-stu-id="3b284-118">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="3b284-119">**Advanced Threat Protection (ATP)**: Bekijk informatie over veilige koppelingen en veilige bijlagen die deel uitmaken van ATP.</span><span class="sxs-lookup"><span data-stu-id="3b284-119">**Advanced Threat Protection (ATP)**: View information about safe links and safe attachments that are part of ATP.</span></span>

<span data-ttu-id="3b284-120">**EOP:** Bekijk informatie over malwaredetecties, vervalste e-mail, spamdetecties en e-mailstroom van en naar uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3b284-120">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="3b284-121">Rapporten voor geavanceerde bedreigingsbeveiliging van Office 365 weergeven</span><span class="sxs-lookup"><span data-stu-id="3b284-121">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="3b284-122">Aangepaste rapporten met Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="3b284-122">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="3b284-123">Maak programmatisch rapporten die beschikbaar zijn in het beheercentrum met Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="3b284-123">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="3b284-124">Zie [Overzicht van Microsoft Graph](https://docs.microsoft.com/graph/overview) en Werken met Office [365-gebruiksrapporten in Microsoft Graph voor](https://docs.microsoft.com/graph/api/resources/report)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3b284-124">For more information, see [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="3b284-125">Berichttracering</span><span class="sxs-lookup"><span data-stu-id="3b284-125">Message trace</span></span>

<span data-ttu-id="3b284-126">Volgt e-mailberichten terwijl ze via EOP reizen.</span><span class="sxs-lookup"><span data-stu-id="3b284-126">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="3b284-127">U bepalen of een e-mailbericht is ontvangen, geweigerd, uitgesteld of geleverd door de service.</span><span class="sxs-lookup"><span data-stu-id="3b284-127">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="3b284-128">Het toont ook welke acties werden ondernomen op het bericht voordat het zijn definitieve status bereikt.</span><span class="sxs-lookup"><span data-stu-id="3b284-128">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="3b284-129">U deze informatie gebruiken om de vragen van uw gebruiker efficiënt te beantwoorden, problemen met de e-mailstroom op te lossen, beleidswijzigingen te valideren en de noodzaak om contact op te nemen met technische ondersteuning voor hulp te verlichten.</span><span class="sxs-lookup"><span data-stu-id="3b284-129">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="3b284-130">Zie [Berichttracering in het Security & Compliance Center](message-trace-scc.md).</span><span class="sxs-lookup"><span data-stu-id="3b284-130">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="3b284-131">Controlelogboekregistratie</span><span class="sxs-lookup"><span data-stu-id="3b284-131">Audit logging</span></span>

<span data-ttu-id="3b284-132">Houdt specifieke wijzigingen bij die door beheerders in uw organisatie zijn aangebracht.</span><span class="sxs-lookup"><span data-stu-id="3b284-132">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="3b284-133">Met deze rapporten u problemen met configuratieproblemen oplossen of de oorzaak van beveiligings- of nalevingsproblemen vinden.</span><span class="sxs-lookup"><span data-stu-id="3b284-133">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="3b284-134">Zie [Auditing rapporten in EOP](auditing-reports-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="3b284-134">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="3b284-135">Beschikbaarheid en latentie van gegevens over het traceren van berichten</span><span class="sxs-lookup"><span data-stu-id="3b284-135">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="3b284-136">In de volgende tabel wordt beschreven wanneer eop-rapportage- en berichttraceringsgegevens beschikbaar zijn en hoe lang.</span><span class="sxs-lookup"><span data-stu-id="3b284-136">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="3b284-137">**Rapporttype**</span><span class="sxs-lookup"><span data-stu-id="3b284-137">**Report type**</span></span>|<span data-ttu-id="3b284-138">**Gegevens beschikbaar voor (terugkijkperiode)**</span><span class="sxs-lookup"><span data-stu-id="3b284-138">**Data available for (look back period)**</span></span>|<span data-ttu-id="3b284-139">**Latency**</span><span class="sxs-lookup"><span data-stu-id="3b284-139">**Latency**</span></span>|
|<span data-ttu-id="3b284-140">Overzichtsrapporten voor e-mailbeveiliging</span><span class="sxs-lookup"><span data-stu-id="3b284-140">Mail protection summary reports</span></span>|<span data-ttu-id="3b284-141">90 dagen</span><span class="sxs-lookup"><span data-stu-id="3b284-141">90 days</span></span>|<span data-ttu-id="3b284-142">De aggregatie van berichtgegevens is meestal binnen 24-48 uur voltooid.</span><span class="sxs-lookup"><span data-stu-id="3b284-142">Message data aggregation is mostly complete within 24-48 hours.</span></span> <span data-ttu-id="3b284-143">Sommige kleine incrementele geaggregeerde wijzigingen kunnen optreden voor maximaal 5 dagen.</span><span class="sxs-lookup"><span data-stu-id="3b284-143">Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="3b284-144">Gedetailleerde rapporten over e-mailbeveiliging</span><span class="sxs-lookup"><span data-stu-id="3b284-144">Mail protection detail reports</span></span>|<span data-ttu-id="3b284-145">90 dagen</span><span class="sxs-lookup"><span data-stu-id="3b284-145">90 days</span></span>|<span data-ttu-id="3b284-146">Voor detailgegevens die minder dan 7 dagen oud zijn, moeten gegevens binnen 24 uur worden weergegeven, maar mogelijk pas na 48 uur zijn voltooid.</span><span class="sxs-lookup"><span data-stu-id="3b284-146">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours.</span></span> <span data-ttu-id="3b284-147">Sommige kleine incrementele wijzigingen kunnen optreden voor maximaal 5 dagen.</span><span class="sxs-lookup"><span data-stu-id="3b284-147">Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="3b284-148">Als u gedetailleerde rapporten wilt weergeven voor berichten die groter zijn dan 7 dagen oud, kunnen de resultaten enkele uren duren.</span><span class="sxs-lookup"><span data-stu-id="3b284-148">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="3b284-149">Gegevens over berichttracering</span><span class="sxs-lookup"><span data-stu-id="3b284-149">Message trace data</span></span>|<span data-ttu-id="3b284-150">90 dagen</span><span class="sxs-lookup"><span data-stu-id="3b284-150">90 days</span></span>|<span data-ttu-id="3b284-151">Wanneer u een berichttracering uitvoert voor berichten die minder dan 7 dagen oud zijn, moeten de berichten binnen 5-30 minuten worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3b284-151">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="3b284-152">Wanneer u een berichttracering uitvoert voor berichten die groter zijn dan 7 dagen oud, kunnen de resultaten enkele uren duren.</span><span class="sxs-lookup"><span data-stu-id="3b284-152">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="3b284-153">Beschikbaarheid en latentie van gegevens zijn hetzelfde, ongeacht of dit wordt aangevraagd via het beheercentrum of de externe PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b284-153">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>
