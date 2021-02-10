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
description: In dit artikel vindt u informatie over rapporten en hulpprogramma's voor probleemoplossing die beschikbaar zijn voor beheerders van Microsoft Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 86c9eb0ee050c4c1a40ef7f29ea3d01dc202be9a
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166673"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="a1f68-103">Rapportage en bericht traceren in EOP</span><span class="sxs-lookup"><span data-stu-id="a1f68-103">Reporting and message trace in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a1f68-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="a1f68-104">**Applies to**</span></span>
- [<span data-ttu-id="a1f68-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a1f68-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="a1f68-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="a1f68-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="a1f68-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1f68-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="a1f68-108">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken biedt EOP veel verschillende rapporten die u kunnen helpen de algehele status en status van uw organisatie te bepalen.</span><span class="sxs-lookup"><span data-stu-id="a1f68-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="a1f68-109">Er zijn ook hulpprogramma's om u te helpen bij het oplossen van specifieke gebeurtenissen (zoals een bericht dat niet is aangekomen bij de beoogde geadresseerden) en het controleren van rapporten om u te helpen voldoen aan de nalevingsvereisten.</span><span class="sxs-lookup"><span data-stu-id="a1f68-109">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="a1f68-110">Gebruiksrapporten</span><span class="sxs-lookup"><span data-stu-id="a1f68-110">Usage reports</span></span>

<span data-ttu-id="a1f68-111">**Activiteit in Microsoft 365-groepen:** informatie weergeven over het aantal Microsoft 365-groepen dat wordt gemaakt en gebruikt.</span><span class="sxs-lookup"><span data-stu-id="a1f68-111">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="a1f68-112">**E-mailactiviteit:** bekijk informatie over het aantal verzonden, ontvangen en gelezen berichten in de hele organisatie en door specifieke gebruikers.</span><span class="sxs-lookup"><span data-stu-id="a1f68-112">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="a1f68-113">**Gebruik van e-mailapps:** bekijk informatie over de e-mailapps die worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="a1f68-113">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="a1f68-114">Dit omvat het totale aantal verbindingen voor elke app en de versies van Outlook die verbinding maken.</span><span class="sxs-lookup"><span data-stu-id="a1f68-114">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="a1f68-115">**Postvakgebruik:** informatie weergeven over gebruikte opslag, quotumgebruik, aantal items en laatste activiteit (verzenden of lezen) voor postvakken.</span><span class="sxs-lookup"><span data-stu-id="a1f68-115">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="a1f68-116">Zie de volgende bronnen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="a1f68-116">See the following resources for more information:</span></span>

- [<span data-ttu-id="a1f68-117">Microsoft 365-rapporten in het beheercentrum - Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="a1f68-117">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="a1f68-118">Microsoft 365-rapporten in het beheercentrum - E-mailactiviteit</span><span class="sxs-lookup"><span data-stu-id="a1f68-118">Microsoft 365 Reports in the admin center - Email activity</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [<span data-ttu-id="a1f68-119">Microsoft 365-rapporten in het beheercentrum - Gebruik van e-mailapps</span><span class="sxs-lookup"><span data-stu-id="a1f68-119">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="a1f68-120">Microsoft 365-rapporten in het beheercentrum - Postvakgebruik</span><span class="sxs-lookup"><span data-stu-id="a1f68-120">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="a1f68-121">Beveiligingsrapporten & compliancerapporten in het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="a1f68-121">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="a1f68-122">Deze verbeterde rapporten bieden een interactieve rapportage-ervaring voor EOP-beheerders, met overzichtsinformatie en de mogelijkheid om in te zoomen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a1f68-122">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="a1f68-123">**Defender voor Office 365:** informatie weergeven over veilige koppelingen en veilige bijlagen die deel uitmaken van Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="a1f68-123">**Defender for Office 365**: View information about Safe Links and Safe Attachments that are part of Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="a1f68-124">**EOP:** informatie weergeven over malwaredetectie, vervalste e-mail, spamdetecties en e-mailstromen van en naar uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a1f68-124">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="a1f68-125">Rapporten voor Defender voor Office 365 weergeven</span><span class="sxs-lookup"><span data-stu-id="a1f68-125">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="a1f68-126">Aangepaste rapporten met Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="a1f68-126">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="a1f68-127">Via programmatisch rapporten maken die beschikbaar zijn in het beheercentrum met Behulp van Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="a1f68-127">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="a1f68-128">Zie Overview [of Microsoft Graph](https://docs.microsoft.com/graph/overview) and Working with Office 365 usage reports in Microsoft Graph (Overzicht van Microsoft Graph en werken met Office [365-gebruiksrapporten in Microsoft Graph) voor meer informatie.](https://docs.microsoft.com/graph/api/resources/report)</span><span class="sxs-lookup"><span data-stu-id="a1f68-128">For more information, see [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="a1f68-129">Bericht traceren</span><span class="sxs-lookup"><span data-stu-id="a1f68-129">Message trace</span></span>

<span data-ttu-id="a1f68-130">Volgt e-mailberichten terwijl ze door EOP reizen.</span><span class="sxs-lookup"><span data-stu-id="a1f68-130">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="a1f68-131">U kunt bepalen of een e-mailbericht is ontvangen, geweigerd, uitgesteld of bezorgd door de service.</span><span class="sxs-lookup"><span data-stu-id="a1f68-131">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="a1f68-132">U ziet ook welke acties er zijn uitgevoerd op het bericht voordat het de uiteindelijke status heeft bereikt.</span><span class="sxs-lookup"><span data-stu-id="a1f68-132">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="a1f68-133">U kunt deze informatie gebruiken om efficiënt antwoord te geven op vragen van gebruikers, problemen met de e-mailstroom op te lossen, beleidswijzigingen te valideren en de noodzaak om contact op te nemen met de technische ondersteuning voor hulp.</span><span class="sxs-lookup"><span data-stu-id="a1f68-133">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="a1f68-134">Zie [Bericht traceren in het beveiligings- & Compliancecentrum.](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="a1f68-134">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="a1f68-135">Auditlogregistratie</span><span class="sxs-lookup"><span data-stu-id="a1f68-135">Audit logging</span></span>

<span data-ttu-id="a1f68-136">Houdt specifieke wijzigingen bij die zijn aangebracht door beheerders in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a1f68-136">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="a1f68-137">Deze rapporten kunnen u helpen configuratieproblemen op te lossen of de oorzaak van beveiligings- of nalevingsproblemen te vinden.</span><span class="sxs-lookup"><span data-stu-id="a1f68-137">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="a1f68-138">Zie [Controlerapporten in EOP.](auditing-reports-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="a1f68-138">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="a1f68-139">Beschikbaarheid en latentie van rapportage- en bericht traceren van gegevens</span><span class="sxs-lookup"><span data-stu-id="a1f68-139">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="a1f68-140">In de volgende tabel wordt beschreven wanneer gegevens over EOP-rapporten en bericht traceren beschikbaar zijn en hoelang.</span><span class="sxs-lookup"><span data-stu-id="a1f68-140">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

****

|<span data-ttu-id="a1f68-141">Rapporttype</span><span class="sxs-lookup"><span data-stu-id="a1f68-141">Report type</span></span>|<span data-ttu-id="a1f68-142">Gegevens beschikbaar voor (terugkijken termijn)</span><span class="sxs-lookup"><span data-stu-id="a1f68-142">Data available for (look back period)</span></span>|<span data-ttu-id="a1f68-143">Latentie</span><span class="sxs-lookup"><span data-stu-id="a1f68-143">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="a1f68-144">Overzichtsrapporten voor E-mailbeveiliging</span><span class="sxs-lookup"><span data-stu-id="a1f68-144">Mail protection summary reports</span></span>|<span data-ttu-id="a1f68-145">90 dagen</span><span class="sxs-lookup"><span data-stu-id="a1f68-145">90 days</span></span>|<span data-ttu-id="a1f68-146">De aggregatie van berichtgegevens wordt meestal binnen 24-48 uur voltooid.</span><span class="sxs-lookup"><span data-stu-id="a1f68-146">Message data aggregation is mostly complete within 24-48 hours.</span></span> <span data-ttu-id="a1f68-147">Enkele kleine, incrementele samengevoegde wijzigingen kunnen maximaal 5 dagen duren.</span><span class="sxs-lookup"><span data-stu-id="a1f68-147">Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="a1f68-148">Detailrapporten over E-mailbeveiliging</span><span class="sxs-lookup"><span data-stu-id="a1f68-148">Mail protection detail reports</span></span>|<span data-ttu-id="a1f68-149">90 dagen</span><span class="sxs-lookup"><span data-stu-id="a1f68-149">90 days</span></span>|<span data-ttu-id="a1f68-150">Voor detailgegevens die minder dan zeven dagen oud zijn, worden gegevens binnen 24 uur weergegeven, maar zijn ze mogelijk pas na 48 uur voltooid.</span><span class="sxs-lookup"><span data-stu-id="a1f68-150">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours.</span></span> <span data-ttu-id="a1f68-151">Enkele kleine incrementele wijzigingen kunnen maximaal 5 dagen duren.</span><span class="sxs-lookup"><span data-stu-id="a1f68-151">Some minor incremental changes may occur for up to 5 days.</span></span> <p> <span data-ttu-id="a1f68-152">Als u detailrapporten wilt weergeven voor berichten die meer dan zeven dagen oud zijn, kunnen de resultaten enkele uren in duren.</span><span class="sxs-lookup"><span data-stu-id="a1f68-152">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="a1f68-153">Gegevens voor bericht traceren</span><span class="sxs-lookup"><span data-stu-id="a1f68-153">Message trace data</span></span>|<span data-ttu-id="a1f68-154">90 dagen</span><span class="sxs-lookup"><span data-stu-id="a1f68-154">90 days</span></span>|<span data-ttu-id="a1f68-155">Wanneer u een bericht traceren voor berichten die minder dan zeven dagen oud zijn, worden de berichten binnen 5-30 minuten weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a1f68-155">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><p> <span data-ttu-id="a1f68-156">Wanneer u een bericht traceren voor berichten die groter zijn dan zeven dagen oud, kan het enkele uren duren.</span><span class="sxs-lookup"><span data-stu-id="a1f68-156">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="a1f68-157">De beschikbaarheid en latentie van gegevens is hetzelfde, ongeacht of dit is aangevraagd via het beheercentrum of externe PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a1f68-157">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>
