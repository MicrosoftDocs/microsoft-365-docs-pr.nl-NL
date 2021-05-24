---
title: Rapportage en berichttracering
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: In dit artikel vindt u informatie over rapporten en hulpprogramma's voor probleemoplossing die beschikbaar zijn Microsoft Exchange Online EOP-beheerders (Protection).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae55ded9d907754161813c9f7bfa7eeb14c558a8
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625027"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="68eb7-103">Rapportage en bericht traceren in EOP</span><span class="sxs-lookup"><span data-stu-id="68eb7-103">Reporting and message trace in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="68eb7-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="68eb7-104">**Applies to**</span></span>
- [<span data-ttu-id="68eb7-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="68eb7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="68eb7-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="68eb7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="68eb7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68eb7-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="68eb7-108">In Microsoft 365 organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken, biedt EOP veel verschillende rapporten die u kunnen helpen bij het bepalen van de algehele status en status van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="68eb7-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="68eb7-109">Er zijn ook hulpprogramma's waarmee u specifieke gebeurtenissen kunt oplossen (zoals een bericht dat niet bij de beoogde geadresseerden binnenkomt) en controlerapporten om te voldoen aan de nalevingsvereisten.</span><span class="sxs-lookup"><span data-stu-id="68eb7-109">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="68eb7-110">Gebruiksrapporten</span><span class="sxs-lookup"><span data-stu-id="68eb7-110">Usage reports</span></span>

<span data-ttu-id="68eb7-111">**Microsoft 365 groepsactiviteiten:** Informatie weergeven over het aantal Microsoft 365 groepen dat wordt gemaakt en gebruikt.</span><span class="sxs-lookup"><span data-stu-id="68eb7-111">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="68eb7-112">**E-mailactiviteit:** Informatie weergeven over het aantal verzonden, ontvangen en gelezen berichten in uw hele organisatie en door specifieke gebruikers.</span><span class="sxs-lookup"><span data-stu-id="68eb7-112">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="68eb7-113">**Gebruik van e-mailapp:** Informatie weergeven over de e-mailapps die worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="68eb7-113">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="68eb7-114">Dit omvat het totale aantal verbindingen voor elke app en de versies van Outlook die verbinding maken.</span><span class="sxs-lookup"><span data-stu-id="68eb7-114">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="68eb7-115">**Postvakgebruik:** Informatie weergeven over gebruikte opslagruimte, quotumverbruik, aantal items en laatste activiteit (verzend- of leesactiviteit) voor postvakken.</span><span class="sxs-lookup"><span data-stu-id="68eb7-115">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="68eb7-116">Zie de volgende bronnen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="68eb7-116">See the following resources for more information:</span></span>

- [<span data-ttu-id="68eb7-117">Microsoft 365 Rapporten in het beheercentrum - Microsoft 365 groepen</span><span class="sxs-lookup"><span data-stu-id="68eb7-117">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](../../admin/activity-reports/office-365-groups.md)

- [<span data-ttu-id="68eb7-118">Microsoft 365 Rapporten in het beheercentrum - E-mailactiviteit</span><span class="sxs-lookup"><span data-stu-id="68eb7-118">Microsoft 365 Reports in the admin center - Email activity</span></span>](../../admin/activity-reports/email-activity.md)

- [<span data-ttu-id="68eb7-119">Microsoft 365 Rapporten in het beheercentrum - Gebruik van e-mailapps</span><span class="sxs-lookup"><span data-stu-id="68eb7-119">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](../../admin/activity-reports/email-apps-usage.md)

- [<span data-ttu-id="68eb7-120">Microsoft 365 Rapporten in het beheercentrum - Postvakgebruik</span><span class="sxs-lookup"><span data-stu-id="68eb7-120">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](../../admin/activity-reports/mailbox-usage.md)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="68eb7-121">Beveiligings- & compliancerapporten in het Microsoft 365 beheercentrum</span><span class="sxs-lookup"><span data-stu-id="68eb7-121">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="68eb7-122">Deze uitgebreide rapporten bieden een interactieve rapportage-ervaring voor EOP-beheerders, met overzichtsgegevens en de mogelijkheid om in te zoomen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="68eb7-122">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="68eb7-123">**Defender voor Office 365:** Informatie weergeven over Safe koppelingen en Safe bijlagen die deel uitmaken van Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="68eb7-123">**Defender for Office 365**: View information about Safe Links and Safe Attachments that are part of Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="68eb7-124">**EOP:** Informatie weergeven over malwaredetecties, vervalste e-mail, spamdetecties en e-mailstroom van en naar uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="68eb7-124">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="68eb7-125">Rapporten weergeven voor Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="68eb7-125">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="68eb7-126">Aangepaste rapporten met Microsoft-Graph</span><span class="sxs-lookup"><span data-stu-id="68eb7-126">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="68eb7-127">Maak programmatisch rapporten die beschikbaar zijn in het beheercentrum met Behulp van Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="68eb7-127">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="68eb7-128">Zie Overzicht van [Microsoft-Graph](/graph/overview) en Werken met Office 365 [gebruiksrapporten in Microsoft Graph.](/graph/api/resources/report)</span><span class="sxs-lookup"><span data-stu-id="68eb7-128">For more information, see [Overview of Microsoft Graph](/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="68eb7-129">Bericht traceren</span><span class="sxs-lookup"><span data-stu-id="68eb7-129">Message trace</span></span>

<span data-ttu-id="68eb7-130">Volgt e-mailberichten terwijl ze via EOP reizen.</span><span class="sxs-lookup"><span data-stu-id="68eb7-130">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="68eb7-131">U kunt bepalen of een e-mailbericht is ontvangen, geweigerd, uitgesteld of bezorgd door de service.</span><span class="sxs-lookup"><span data-stu-id="68eb7-131">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="68eb7-132">Ook wordt weergegeven welke acties zijn uitgevoerd op het bericht voordat het de uiteindelijke status heeft bereikt.</span><span class="sxs-lookup"><span data-stu-id="68eb7-132">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="68eb7-133">U kunt deze informatie gebruiken om de vragen van uw gebruiker efficiënt te beantwoorden, problemen met de e-mailstroom op te lossen, beleidswijzigingen te valideren en om contact op te nemen met de technische ondersteuning voor hulp.</span><span class="sxs-lookup"><span data-stu-id="68eb7-133">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="68eb7-134">Zie [Bericht traceren in het Beveiligings- & compliancecentrum](message-trace-scc.md).</span><span class="sxs-lookup"><span data-stu-id="68eb7-134">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="68eb7-135">Auditregistratie</span><span class="sxs-lookup"><span data-stu-id="68eb7-135">Audit logging</span></span>

<span data-ttu-id="68eb7-136">Houdt specifieke wijzigingen bij die door beheerders in uw organisatie zijn aangebracht.</span><span class="sxs-lookup"><span data-stu-id="68eb7-136">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="68eb7-137">Met deze rapporten kunt u configuratieproblemen oplossen of de oorzaak van beveiligings- of complianceproblemen vinden.</span><span class="sxs-lookup"><span data-stu-id="68eb7-137">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="68eb7-138">Zie [Controlerapporten in Exchange Online.](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)</span><span class="sxs-lookup"><span data-stu-id="68eb7-138">See [Auditing reports in Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="68eb7-139">Beschikbaarheid en latentie van gegevens rapporteren en berichten traceren</span><span class="sxs-lookup"><span data-stu-id="68eb7-139">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="68eb7-140">In de volgende tabel wordt beschreven wanneer EOP-rapportage- en bericht trace-gegevens beschikbaar zijn en hoelang.</span><span class="sxs-lookup"><span data-stu-id="68eb7-140">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

****

|<span data-ttu-id="68eb7-141">Rapporttype</span><span class="sxs-lookup"><span data-stu-id="68eb7-141">Report type</span></span>|<span data-ttu-id="68eb7-142">Beschikbare gegevens voor (terugkijken)</span><span class="sxs-lookup"><span data-stu-id="68eb7-142">Data available for (look back period)</span></span>|<span data-ttu-id="68eb7-143">Latentie</span><span class="sxs-lookup"><span data-stu-id="68eb7-143">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="68eb7-144">Overzichtsrapporten voor e-mailbeveiliging</span><span class="sxs-lookup"><span data-stu-id="68eb7-144">Mail protection summary reports</span></span>|<span data-ttu-id="68eb7-145">90 dagen</span><span class="sxs-lookup"><span data-stu-id="68eb7-145">90 days</span></span>|<span data-ttu-id="68eb7-146">De aggregatie van berichtgegevens is meestal binnen 24-48 uur voltooid.</span><span class="sxs-lookup"><span data-stu-id="68eb7-146">Message data aggregation is mostly complete within 24-48 hours.</span></span> <span data-ttu-id="68eb7-147">Sommige secundaire, geaggregeerde wijzigingen kunnen maximaal 5 dagen duren.</span><span class="sxs-lookup"><span data-stu-id="68eb7-147">Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="68eb7-148">E-mailbeveiligingsdetailrapporten</span><span class="sxs-lookup"><span data-stu-id="68eb7-148">Mail protection detail reports</span></span>|<span data-ttu-id="68eb7-149">90 dagen</span><span class="sxs-lookup"><span data-stu-id="68eb7-149">90 days</span></span>|<span data-ttu-id="68eb7-150">Voor detailgegevens die minder dan 7 dagen oud zijn, moeten gegevens binnen 24 uur worden weergegeven, maar mogelijk pas na 48 uur zijn voltooid.</span><span class="sxs-lookup"><span data-stu-id="68eb7-150">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours.</span></span> <span data-ttu-id="68eb7-151">Sommige kleine incrementele wijzigingen kunnen tot 5 dagen duren.</span><span class="sxs-lookup"><span data-stu-id="68eb7-151">Some minor incremental changes may occur for up to 5 days.</span></span> <p> <span data-ttu-id="68eb7-152">Als u detailrapporten wilt weergeven voor berichten die groter zijn dan 7 dagen oud, kunnen de resultaten enkele uren duren.</span><span class="sxs-lookup"><span data-stu-id="68eb7-152">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="68eb7-153">Gegevens over bericht traceren</span><span class="sxs-lookup"><span data-stu-id="68eb7-153">Message trace data</span></span>|<span data-ttu-id="68eb7-154">90 dagen</span><span class="sxs-lookup"><span data-stu-id="68eb7-154">90 days</span></span>|<span data-ttu-id="68eb7-155">Wanneer u een bericht traceert voor berichten die minder dan 7 dagen oud zijn, moeten de berichten binnen 5-30 minuten worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="68eb7-155">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><p> <span data-ttu-id="68eb7-156">Wanneer u een bericht traceert voor berichten die groter zijn dan 7 dagen oud, kunnen de resultaten enkele uren duren.</span><span class="sxs-lookup"><span data-stu-id="68eb7-156">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="68eb7-157">De beschikbaarheid en latentie van gegevens is hetzelfde, ongeacht of deze zijn aangevraagd via het beheercentrum of externe PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68eb7-157">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>