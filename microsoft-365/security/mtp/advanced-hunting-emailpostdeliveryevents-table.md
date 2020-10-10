---
title: EmailPostDeliveryEvents-tabel in het geavanceerde jacht schema
description: Meer informatie over de acties voor de bezorging van de bezorging van Microsoft 365-e-mails in de tabel EmailPostDeliveryEvents van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat-jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema Reference, kusto, tabel, Column, datatype, een beschrijving, EmailPostDeliveryEvents, de naam van de bijlage, de afzender, de naam van de e-mail, het aantal koppelingen, het aantal url's
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 65cd02f4277cf3694d85eac92392899b140c9f74
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412140"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="2819d-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="2819d-104">EmailPostDeliveryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2819d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2819d-105">**Applies to:**</span></span>
- <span data-ttu-id="2819d-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2819d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="2819d-107">De `EmailPostDeliveryEvents` tabel in het [Geavanceerde](advanced-hunting-overview.md) bezorgings schema bevat informatie over acties voor de bezorging van de bezorging van e-mailberichten die worden verwerkt door Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2819d-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="2819d-108">Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="2819d-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="2819d-109">Voor gedetailleerde informatie over de typen gebeurtenissen ( `ActionType` waarden) die door een tabel worden ondersteund, gebruikt u de [ingebouwde schema verwijzing](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) die beschikbaar is in het Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="2819d-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="2819d-110">Als u meer informatie wilt over afzonderlijke e-mailberichten, kunt u ook de [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) tabellen, en de [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tabellen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2819d-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="2819d-111">Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.</span><span class="sxs-lookup"><span data-stu-id="2819d-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="2819d-112">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="2819d-112">Column name</span></span> | <span data-ttu-id="2819d-113">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="2819d-113">Data type</span></span> | <span data-ttu-id="2819d-114">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="2819d-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="2819d-115">tijd</span><span class="sxs-lookup"><span data-stu-id="2819d-115">datetime</span></span> | <span data-ttu-id="2819d-116">De datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="2819d-116">Date and time when the event was recorded</span></span> |
| `EventId` | <span data-ttu-id="2819d-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2819d-117">string</span></span> | <span data-ttu-id="2819d-118">Unieke id voor de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="2819d-118">Unique identifier for the event</span></span> |
| `NetworkMessageId` | <span data-ttu-id="2819d-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2819d-119">string</span></span> | <span data-ttu-id="2819d-120">Unieke id voor de e-mail, gegenereerd door Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2819d-120">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="2819d-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2819d-121">string</span></span> | <span data-ttu-id="2819d-122">Openbare id voor het e-mailbericht dat wordt ingesteld door het verzendende e-mailsysteem</span><span class="sxs-lookup"><span data-stu-id="2819d-122">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="2819d-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2819d-123">string</span></span> | <span data-ttu-id="2819d-124">Actie die is uitgevoerd voor de entiteit</span><span class="sxs-lookup"><span data-stu-id="2819d-124">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="2819d-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2819d-125">string</span></span> | <span data-ttu-id="2819d-126">Type activiteit dat de gebeurtenis heeft veroorzaakt: handmatig herbemiddeling, Phishman, malware ZAP</span><span class="sxs-lookup"><span data-stu-id="2819d-126">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="2819d-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2819d-127">string</span></span> | <span data-ttu-id="2819d-128">Geeft aan of een actie is geactiveerd door een beheerder (handmatig of via goedkeuring van een geautomatiseerde actie in behandeling), of met een speciaal mechanisme, zoals een ZAP-of dynamische bezorging</span><span class="sxs-lookup"><span data-stu-id="2819d-128">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="2819d-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2819d-129">string</span></span> | <span data-ttu-id="2819d-130">Resultaat van de actie</span><span class="sxs-lookup"><span data-stu-id="2819d-130">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="2819d-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2819d-131">string</span></span> | <span data-ttu-id="2819d-132">Het e-mailadres van de geadresseerde of het e-mailadres van de geadresseerde na expansie van distributielijst</span><span class="sxs-lookup"><span data-stu-id="2819d-132">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="2819d-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="2819d-133">string</span></span> | <span data-ttu-id="2819d-134">De locatie waar het e-mailbericht is bezorgd: Postvak in/map, on-premises/extern, ongewenste E-mail, Quarantine, mislukt, neergezette, verwijderde items</span><span class="sxs-lookup"><span data-stu-id="2819d-134">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="2819d-135">Ondersteunde gebeurtenistypen</span><span class="sxs-lookup"><span data-stu-id="2819d-135">Supported event types</span></span>
<span data-ttu-id="2819d-136">In deze tabel worden gebeurtenissen vastgelegd met de volgende `ActionType` waarden:</span><span class="sxs-lookup"><span data-stu-id="2819d-136">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="2819d-137">**Handmatig herstel** : een beheerder heeft handmatig een actie uitgevoerd voor een e-mailbericht nadat het is afgeleverd bij het gebruikerspostvak.</span><span class="sxs-lookup"><span data-stu-id="2819d-137">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="2819d-138">Dit omvat ook acties die u handmatig hebt uitgevoerd via de [bedreigings Verkenner](../office-365-security/threat-explorer.md) of de goedkeuring van [automatisch onderzoek en antwoord acties (lucht)](mtp-autoir-actions.md).</span><span class="sxs-lookup"><span data-stu-id="2819d-138">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](mtp-autoir-actions.md).</span></span>
- <span data-ttu-id="2819d-139">**Phishing ZAP** - [Zero-Hour auto leegmaak (ZAP)](../office-365-security/zero-hour-auto-purge.md) nam na ontvangst actie een malafide e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="2819d-139">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="2819d-140">**Malware ZAP** -voor een e-mailbericht met malware na de levering de actie ' ZAP '.</span><span class="sxs-lookup"><span data-stu-id="2819d-140">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2819d-141">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="2819d-141">Related topics</span></span>
- [<span data-ttu-id="2819d-142">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="2819d-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2819d-143">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="2819d-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2819d-144">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="2819d-144">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="2819d-145">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="2819d-145">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="2819d-146">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="2819d-146">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2819d-147">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="2819d-147">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
