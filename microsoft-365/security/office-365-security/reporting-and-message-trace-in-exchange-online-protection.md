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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: In dit artikel vindt u meer informatie over hulpprogramma's voor het oplossen van rapporten die beschikbaar zijn voor Microsoft Exchange Online Protection (EOP)-beheerders.
ms.openlocfilehash: 9a8eb8e35ef73eb27604eef4bf701982b1d51710
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845550"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="1da43-103">Rapporten en berichten traceren in EOP</span><span class="sxs-lookup"><span data-stu-id="1da43-103">Reporting and message trace in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="1da43-104">In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken, biedt EOP veel verschillende rapporten waarmee u de algehele status en de status van uw organisatie kunt bepalen.</span><span class="sxs-lookup"><span data-stu-id="1da43-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="1da43-105">Er zijn ook hulpmiddelen waarmee u problemen kunt oplossen, zoals een bericht dat niet aan de bedoelde geadresseerden voldoet, en de controlerapporten voor de nalevingsvereisten.</span><span class="sxs-lookup"><span data-stu-id="1da43-105">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="1da43-106">Gebruiksrapporten</span><span class="sxs-lookup"><span data-stu-id="1da43-106">Usage reports</span></span>

<span data-ttu-id="1da43-107">**Activiteiten van Microsoft 365 groepen** : informatie weergeven over het aantal microsoft 365-groepen dat is gemaakt en gebruikt.</span><span class="sxs-lookup"><span data-stu-id="1da43-107">**Microsoft 365 groups activity** : View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="1da43-108">**E-mail activiteit** : Hier vindt u informatie over het aantal verzonden, ontvangen en gelezen berichten in uw hele organisatie en van specifieke gebruikers.</span><span class="sxs-lookup"><span data-stu-id="1da43-108">**Email activity** : View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="1da43-109">**Gebruik van e-mail-apps** : informatie weergeven over de gebruikte e-mail-apps.</span><span class="sxs-lookup"><span data-stu-id="1da43-109">**Email app usage** : View information about the email apps that are used.</span></span> <span data-ttu-id="1da43-110">Dit omvat het totale aantal verbindingen voor elke app en de versies van Outlook die verbinding maken.</span><span class="sxs-lookup"><span data-stu-id="1da43-110">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="1da43-111">**Postvakgebruik** : informatie weergeven over gebruikte opslagruimte, quota verbruik, aantal items, en laatste activiteit (verzenden of lezen) voor postvakken.</span><span class="sxs-lookup"><span data-stu-id="1da43-111">**Mailbox usage** : View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="1da43-112">Raadpleeg de volgende bronnen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="1da43-112">See the following resources for more information:</span></span>

- [<span data-ttu-id="1da43-113">Microsoft 365-rapporten in het Beheercentrum-Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="1da43-113">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="1da43-114">Microsoft 365-rapporten in het Beheercentrum-e-mail activiteit</span><span class="sxs-lookup"><span data-stu-id="1da43-114">Microsoft 365 Reports in the admin center - Email activity</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [<span data-ttu-id="1da43-115">Microsoft 365-rapporten in het Beheercentrum-gebruik van e-mail-apps</span><span class="sxs-lookup"><span data-stu-id="1da43-115">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="1da43-116">Microsoft 365-rapporten in het Beheercentrum-postvakgebruik</span><span class="sxs-lookup"><span data-stu-id="1da43-116">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="1da43-117">Beveiligings & nalevings rapporten in het Microsoft 365-Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="1da43-117">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="1da43-118">Deze verbeterde rapporten bieden een interactieve rapportering van EOP-beheerders, waaronder samenvattende informatie en de mogelijkheid om te inzoomen voor meer details.</span><span class="sxs-lookup"><span data-stu-id="1da43-118">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="1da43-119">**Defender voor Office 365** : informatie weergeven over veilige koppelingen en veilige bijlagen die deel uitmaken van Microsoft Defender for Office 365.</span><span class="sxs-lookup"><span data-stu-id="1da43-119">**Defender for Office 365** : View information about Safe Links and Safe Attachments that are part of Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="1da43-120">**EOP** : informatie over detectie van malware, spoofing voor e-mail, detectie van spam, en de e-mail stroom van en naar uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="1da43-120">**EOP** : View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="1da43-121">Rapporten weergeven voor Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="1da43-121">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="1da43-122">Aangepaste rapporten met Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="1da43-122">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="1da43-123">U maakt via programmering rapporten die beschikbaar zijn in het Beheercentrum met behulp van Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="1da43-123">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="1da43-124">Zie voor meer informatie: [overzicht van Microsoft Graph](https://docs.microsoft.com/graph/overview) en [werken met Office 365-gebruiksrapporten in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span><span class="sxs-lookup"><span data-stu-id="1da43-124">For more information, see [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="1da43-125">Bericht traceren</span><span class="sxs-lookup"><span data-stu-id="1da43-125">Message trace</span></span>

<span data-ttu-id="1da43-126">Volg deze e-mailberichten wanneer ze onderweg zijn via EOP.</span><span class="sxs-lookup"><span data-stu-id="1da43-126">Follows email messages as they travel through EOP.</span></span> <span data-ttu-id="1da43-127">U kunt bepalen of een e-mailbericht is ontvangen, afgewezen, uitgesteld of geleverd door de service.</span><span class="sxs-lookup"><span data-stu-id="1da43-127">You can determine if an email message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="1da43-128">Ook ziet u welke acties zijn uitgevoerd op het bericht voordat het de definitieve status bereikte.</span><span class="sxs-lookup"><span data-stu-id="1da43-128">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="1da43-129">U kunt deze gegevens gebruiken om de vragen van uw gebruikers op de juiste manier op te lossen, problemen met de e-mail stroom op te lossen, beleidswijzigingen te valideren en contact op te nemen met technische ondersteuning voor hulp.</span><span class="sxs-lookup"><span data-stu-id="1da43-129">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="1da43-130">Zie [bericht traceren in de beveiligings & nalevings centrum](message-trace-scc.md).</span><span class="sxs-lookup"><span data-stu-id="1da43-130">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="1da43-131">Controlelogboekregistratie</span><span class="sxs-lookup"><span data-stu-id="1da43-131">Audit logging</span></span>

<span data-ttu-id="1da43-132">Hiermee kunt u specifieke wijzigingen van beheerders bijhouden in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="1da43-132">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="1da43-133">Deze rapporten kunnen u helpen bij het oplossen van problemen met de configuratie of voor het oplossen van problemen met betrekking tot beveiliging of compliance.</span><span class="sxs-lookup"><span data-stu-id="1da43-133">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="1da43-134">Zie [controlerapporten in EOP](auditing-reports-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="1da43-134">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="1da43-135">Beschikbaarheid en latentie van de gegevens van rapporten en berichten traceren</span><span class="sxs-lookup"><span data-stu-id="1da43-135">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="1da43-136">In de volgende tabel wordt beschreven wanneer EOP-rapporten en-traceringsgegevens beschikbaar zijn en hoe lang dit duurt.</span><span class="sxs-lookup"><span data-stu-id="1da43-136">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

****

|<span data-ttu-id="1da43-137">Rapporttype</span><span class="sxs-lookup"><span data-stu-id="1da43-137">Report type</span></span>|<span data-ttu-id="1da43-138">Beschikbare gegevens voor (weergeven als periode)</span><span class="sxs-lookup"><span data-stu-id="1da43-138">Data available for (look back period)</span></span>|<span data-ttu-id="1da43-139">Tijd</span><span class="sxs-lookup"><span data-stu-id="1da43-139">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="1da43-140">Overzichtsrapporten mail beveiliging</span><span class="sxs-lookup"><span data-stu-id="1da43-140">Mail protection summary reports</span></span>|<span data-ttu-id="1da43-141">90 dagen</span><span class="sxs-lookup"><span data-stu-id="1da43-141">90 days</span></span>|<span data-ttu-id="1da43-142">Het samenvoegen van berichtgegevens is vooral binnen 24-48 uur voltooid.</span><span class="sxs-lookup"><span data-stu-id="1da43-142">Message data aggregation is mostly complete within 24-48 hours.</span></span> <span data-ttu-id="1da43-143">Sommige kleine, incrementele, incrementele, ondergebrachte wijzigingen worden gedurende vijf dagen veroorzaakt.</span><span class="sxs-lookup"><span data-stu-id="1da43-143">Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="1da43-144">Details van e-mail beveiligingsrapporten</span><span class="sxs-lookup"><span data-stu-id="1da43-144">Mail protection detail reports</span></span>|<span data-ttu-id="1da43-145">90 dagen</span><span class="sxs-lookup"><span data-stu-id="1da43-145">90 days</span></span>|<span data-ttu-id="1da43-146">Voor detailgegevens die minder dan zeven dagen oud zijn, moeten de gegevens binnen 24 uur worden weergegeven, maar mogelijk niet voltooien tot 48 uur.</span><span class="sxs-lookup"><span data-stu-id="1da43-146">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours.</span></span> <span data-ttu-id="1da43-147">U kunt maximaal 5 dagen enkele kleine incrementele wijzigingen voordoen.</span><span class="sxs-lookup"><span data-stu-id="1da43-147">Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="1da43-148">Als u detailrapporten wilt weergeven voor berichten die ouder zijn dan zeven dagen, kan het tot een paar uur duren voordat de resultaten zijn afgelopen.</span><span class="sxs-lookup"><span data-stu-id="1da43-148">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="1da43-149">Berichten traceren</span><span class="sxs-lookup"><span data-stu-id="1da43-149">Message trace data</span></span>|<span data-ttu-id="1da43-150">90 dagen</span><span class="sxs-lookup"><span data-stu-id="1da43-150">90 days</span></span>|<span data-ttu-id="1da43-151">Wanneer u een bericht tracering uitvoert voor berichten die minder dan zeven dagen oud zijn, worden de berichten weergegeven binnen 5-30 minuten.</span><span class="sxs-lookup"><span data-stu-id="1da43-151">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="1da43-152">Wanneer u een bericht tracering uitvoert voor berichten die ouder zijn dan zeven dagen, kunnen de resultaten enkele uren duren.</span><span class="sxs-lookup"><span data-stu-id="1da43-152">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="1da43-153">De beschikbaarheid en latentie van de gegevens is afhankelijk van het aangevraagde verzoek via het Beheercentrum of vanuit een externe PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1da43-153">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>
