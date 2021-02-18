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
ms.openlocfilehash: 783c7ea0aca47c805daf66592b401a98f739d071
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288077"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="90ff4-103">Rapportage en bericht traceren in EOP</span><span class="sxs-lookup"><span data-stu-id="90ff4-103">Reporting and message trace in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="90ff4-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="90ff4-104">**Applies to**</span></span>
- [<span data-ttu-id="90ff4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="90ff4-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="90ff4-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="90ff4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="90ff4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="90ff4-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="90ff4-108">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken biedt EOP veel verschillende rapporten die u kunnen helpen de algehele status en status van uw organisatie te bepalen.</span><span class="sxs-lookup"><span data-stu-id="90ff4-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="90ff4-109">Er zijn ook hulpprogramma's om u te helpen bij het oplossen van specifieke gebeurtenissen (zoals een bericht dat niet is aangekomen bij de beoogde geadresseerden) en het controleren van rapporten om u te helpen voldoen aan de nalevingsvereisten.</span><span class="sxs-lookup"><span data-stu-id="90ff4-109">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="90ff4-110">Gebruiksrapporten</span><span class="sxs-lookup"><span data-stu-id="90ff4-110">Usage reports</span></span>

<span data-ttu-id="90ff4-111">**Activiteit in Microsoft 365-groepen:** informatie weergeven over het aantal Microsoft 365-groepen dat wordt gemaakt en gebruikt.</span><span class="sxs-lookup"><span data-stu-id="90ff4-111">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="90ff4-112">**E-mailactiviteit:** informatie weergeven over het aantal verzonden, ontvangen en gelezen berichten in de hele organisatie en door specifieke gebruikers.</span><span class="sxs-lookup"><span data-stu-id="90ff4-112">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="90ff4-113">**Gebruik van e-mailapps:** bekijk informatie over de e-mailapps die worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="90ff4-113">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="90ff4-114">Dit omvat het totale aantal verbindingen voor elke app en de versies van Outlook die verbinding maken.</span><span class="sxs-lookup"><span data-stu-id="90ff4-114">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="90ff4-115">**Postvakgebruik:** informatie weergeven over gebruikte opslag, quotumgebruik, aantal items en laatste activiteit (verzenden of lezen) voor postvakken.</span><span class="sxs-lookup"><span data-stu-id="90ff4-115">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="90ff4-116">Zie de volgende bronnen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="90ff4-116">See the following resources for more information:</span></span>

- [<span data-ttu-id="90ff4-117">Microsoft 365-rapporten in het beheercentrum - Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="90ff4-117">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](../../admin/activity-reports/office-365-groups.md)

- [<span data-ttu-id="90ff4-118">Microsoft 365-rapporten in het beheercentrum - E-mailactiviteit</span><span class="sxs-lookup"><span data-stu-id="90ff4-118">Microsoft 365 Reports in the admin center - Email activity</span></span>](../../admin/activity-reports/email-activity.md)

- [<span data-ttu-id="90ff4-119">Microsoft 365-rapporten in het beheercentrum - Gebruik van e-mailapps</span><span class="sxs-lookup"><span data-stu-id="90ff4-119">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](../../admin/activity-reports/email-apps-usage.md)

- [<span data-ttu-id="90ff4-120">Microsoft 365-rapporten in het beheercentrum - Postvakgebruik</span><span class="sxs-lookup"><span data-stu-id="90ff4-120">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](../../admin/activity-reports/mailbox-usage.md)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="90ff4-121">Beveiligingsrapporten & compliancerapporten in het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="90ff4-121">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="90ff4-122">Deze verbeterde rapporten bieden een interactieve rapportage-ervaring voor EOP-beheerders, met overzichtsinformatie en de mogelijkheid om in te zoomen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="90ff4-122">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="90ff4-123">**Defender voor Office 365:** informatie weergeven over veilige koppelingen en veilige bijlagen die deel uitmaken van Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="90ff4-123">**Defender for Office 365**: View information about Safe Links and Safe Attachments that are part of Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="90ff4-124">**EOP:** informatie weergeven over malwaredetectie, vervalste e-mail, spamdetecties en e-mailstromen van en naar uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="90ff4-124">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="90ff4-125">Rapporten voor Defender voor Office 365 weergeven</span><span class="sxs-lookup"><span data-stu-id="90ff4-125">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="90ff4-126">Aangepaste rapporten met Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="90ff4-126">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="90ff4-127">Via programmatisch rapporten maken die beschikbaar zijn in het beheercentrum met Behulp van Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="90ff4-127">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="90ff4-128">Zie Overview [of Microsoft Graph](https://docs.microsoft.com/graph/overview) and Working with Office 365 usage reports in Microsoft Graph (Overzicht van Microsoft Graph en werken met Office [365-gebruiksrapporten in Microsoft Graph) voor meer informatie.](https://docs.microsoft.com/graph/api/resources/report)</span><span class="sxs-lookup"><span data-stu-id="90ff4-128">For more information, see [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="90ff4-129">Bericht traceren</span><span class="sxs-lookup"><span data-stu-id="90ff4-129">Message trace</span></span>

<span data-ttu-id="90ff4-130">Volgt e-mailberichten terwijl ze door EOP reizen.</span><span class="sxs-lookup"><span data-stu-id="90ff4-130">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="90ff4-131">U kunt bepalen of een e-mailbericht is ontvangen, geweigerd, uitgesteld of bezorgd door de service.</span><span class="sxs-lookup"><span data-stu-id="90ff4-131">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="90ff4-132">U ziet ook welke acties er zijn uitgevoerd op het bericht voordat het de uiteindelijke status heeft bereikt.</span><span class="sxs-lookup"><span data-stu-id="90ff4-132">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="90ff4-133">U kunt deze informatie gebruiken om op een efficiënte manier antwoord te geven op vragen van gebruikers, problemen met de e-mailstroom op te lossen, beleidswijzigingen te valideren en de noodzaak om contact op te nemen met de technische ondersteuning voor hulp.</span><span class="sxs-lookup"><span data-stu-id="90ff4-133">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="90ff4-134">Zie [Bericht traceren in het beveiligings- & Compliancecentrum.](message-trace-scc.md)</span><span class="sxs-lookup"><span data-stu-id="90ff4-134">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="90ff4-135">Auditlogregistratie</span><span class="sxs-lookup"><span data-stu-id="90ff4-135">Audit logging</span></span>

<span data-ttu-id="90ff4-136">Houdt specifieke wijzigingen bij die zijn aangebracht door beheerders in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="90ff4-136">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="90ff4-137">Deze rapporten kunnen u helpen configuratieproblemen op te lossen of de oorzaak van beveiligings- of nalevingsproblemen te vinden.</span><span class="sxs-lookup"><span data-stu-id="90ff4-137">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="90ff4-138">Zie [Controlerapporten in EOP.](auditing-reports-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="90ff4-138">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="90ff4-139">Beschikbaarheid en latentie van rapportage- en bericht traceren van gegevens</span><span class="sxs-lookup"><span data-stu-id="90ff4-139">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="90ff4-140">In de volgende tabel wordt beschreven wanneer gegevens over EOP-rapporten en bericht traceren beschikbaar zijn en hoelang.</span><span class="sxs-lookup"><span data-stu-id="90ff4-140">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

****

|<span data-ttu-id="90ff4-141">Rapporttype</span><span class="sxs-lookup"><span data-stu-id="90ff4-141">Report type</span></span>|<span data-ttu-id="90ff4-142">Gegevens die beschikbaar zijn voor (terugkijken periode)</span><span class="sxs-lookup"><span data-stu-id="90ff4-142">Data available for (look back period)</span></span>|<span data-ttu-id="90ff4-143">Latentie</span><span class="sxs-lookup"><span data-stu-id="90ff4-143">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="90ff4-144">Overzichtsrapporten voor E-mailbeveiliging</span><span class="sxs-lookup"><span data-stu-id="90ff4-144">Mail protection summary reports</span></span>|<span data-ttu-id="90ff4-145">90 dagen</span><span class="sxs-lookup"><span data-stu-id="90ff4-145">90 days</span></span>|<span data-ttu-id="90ff4-146">De aggregatie van berichtgegevens wordt meestal binnen 24-48 uur voltooid.</span><span class="sxs-lookup"><span data-stu-id="90ff4-146">Message data aggregation is mostly complete within 24-48 hours.</span></span> <span data-ttu-id="90ff4-147">Enkele kleine, incrementele samengevoegde wijzigingen kunnen maximaal 5 dagen duren.</span><span class="sxs-lookup"><span data-stu-id="90ff4-147">Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="90ff4-148">Detailrapporten over E-mailbeveiliging</span><span class="sxs-lookup"><span data-stu-id="90ff4-148">Mail protection detail reports</span></span>|<span data-ttu-id="90ff4-149">90 dagen</span><span class="sxs-lookup"><span data-stu-id="90ff4-149">90 days</span></span>|<span data-ttu-id="90ff4-150">Voor detailgegevens die minder dan zeven dagen oud zijn, worden gegevens binnen 24 uur weergegeven, maar zijn ze mogelijk pas na 48 uur voltooid.</span><span class="sxs-lookup"><span data-stu-id="90ff4-150">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours.</span></span> <span data-ttu-id="90ff4-151">Enkele kleine incrementele wijzigingen kunnen maximaal 5 dagen duren.</span><span class="sxs-lookup"><span data-stu-id="90ff4-151">Some minor incremental changes may occur for up to 5 days.</span></span> <p> <span data-ttu-id="90ff4-152">Als u detailrapporten wilt weergeven voor berichten die meer dan zeven dagen oud zijn, kan het enkele uren duren voordat de resultaten zijn bekeken.</span><span class="sxs-lookup"><span data-stu-id="90ff4-152">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="90ff4-153">Gegevens voor bericht traceren</span><span class="sxs-lookup"><span data-stu-id="90ff4-153">Message trace data</span></span>|<span data-ttu-id="90ff4-154">90 dagen</span><span class="sxs-lookup"><span data-stu-id="90ff4-154">90 days</span></span>|<span data-ttu-id="90ff4-155">Wanneer u een bericht traceren voor berichten die minder dan zeven dagen oud zijn, worden de berichten binnen 5-30 minuten weergegeven.</span><span class="sxs-lookup"><span data-stu-id="90ff4-155">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><p> <span data-ttu-id="90ff4-156">Wanneer u een bericht traceren voor berichten die groter zijn dan zeven dagen oud, kan het enkele uren duren.</span><span class="sxs-lookup"><span data-stu-id="90ff4-156">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="90ff4-157">De beschikbaarheid en latentie van gegevens is hetzelfde, ongeacht of dit is aangevraagd via het beheercentrum of externe PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90ff4-157">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>
