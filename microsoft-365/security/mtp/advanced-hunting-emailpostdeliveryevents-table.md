---
title: Tabel EmailPostDeliveryEvents in het geavanceerde schema voor zoeken
description: Meer informatie over acties na de bezorging van Microsoft 365-e-mailberichten in de tabel EmailPostDeliveryEvents van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, EmailPostDeliveryEvents, network message id, sender, recipient, attachment id, attachment name, malware phishing op basis van phishing, attachment attachment count, link count, url count
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d7920be05156320411f3907cbcdae88d315b5136
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929704"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="0bbef-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="0bbef-104">EmailPostDeliveryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0bbef-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="0bbef-105">**Applies to:**</span></span>
- <span data-ttu-id="0bbef-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0bbef-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="0bbef-107">De tabel in het geavanceerde schema voor zoeken bevat informatie over acties na bezorging die zijn uitgevoerd op e-mailberichten die worden `EmailPostDeliveryEvents` verwerkt door Microsoft 365. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="0bbef-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="0bbef-108">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="0bbef-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="0bbef-109">Voor gedetailleerde informatie over de gebeurtenistypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` [ingebouwde schemaverwijzing in](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) het beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="0bbef-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="0bbef-110">Voor meer informatie over afzonderlijke e-mailberichten kunt u ook de [`EmailEvents`](advanced-hunting-emailevents-table.md) tabellen en de tabellen [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0bbef-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="0bbef-111">Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="0bbef-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0bbef-112">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="0bbef-112">Column name</span></span> | <span data-ttu-id="0bbef-113">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="0bbef-113">Data type</span></span> | <span data-ttu-id="0bbef-114">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="0bbef-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0bbef-115">datetime</span><span class="sxs-lookup"><span data-stu-id="0bbef-115">datetime</span></span> | <span data-ttu-id="0bbef-116">Datum en tijd waarop de gebeurtenis is vastgelegd</span><span class="sxs-lookup"><span data-stu-id="0bbef-116">Date and time when the event was recorded</span></span> |
| `EventId` | <span data-ttu-id="0bbef-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0bbef-117">string</span></span> | <span data-ttu-id="0bbef-118">Unieke id voor de gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="0bbef-118">Unique identifier for the event</span></span> |
| `NetworkMessageId` | <span data-ttu-id="0bbef-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0bbef-119">string</span></span> | <span data-ttu-id="0bbef-120">Unieke id voor het e-mailbericht, gegenereerd door Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0bbef-120">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="0bbef-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0bbef-121">string</span></span> | <span data-ttu-id="0bbef-122">Openbare id voor de e-mail die wordt ingesteld door het verzendende e-mailsysteem</span><span class="sxs-lookup"><span data-stu-id="0bbef-122">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="0bbef-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0bbef-123">string</span></span> | <span data-ttu-id="0bbef-124">Actie ondernomen op de entiteit</span><span class="sxs-lookup"><span data-stu-id="0bbef-124">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="0bbef-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0bbef-125">string</span></span> | <span data-ttu-id="0bbef-126">Het type activiteit dat de gebeurtenis heeft geactiveerd: Handmatige oplossing, Phish ZAP, Malware ZAP</span><span class="sxs-lookup"><span data-stu-id="0bbef-126">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="0bbef-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0bbef-127">string</span></span> | <span data-ttu-id="0bbef-128">Geeft aan of een actie is geactiveerd door een beheerder (handmatig of via goedkeuring van een geautomatiseerde actie in behandeling) of door een speciaal mechanisme, zoals ZAP of Dynamische levering</span><span class="sxs-lookup"><span data-stu-id="0bbef-128">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="0bbef-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0bbef-129">string</span></span> | <span data-ttu-id="0bbef-130">Resultaat van de actie</span><span class="sxs-lookup"><span data-stu-id="0bbef-130">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="0bbef-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0bbef-131">string</span></span> | <span data-ttu-id="0bbef-132">Het e-mailadres van de geadresseerde of het e-mailadres van de ontvanger na uitbreiding van de distributielijst</span><span class="sxs-lookup"><span data-stu-id="0bbef-132">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="0bbef-133">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="0bbef-133">string</span></span> | <span data-ttu-id="0bbef-134">Locatie waar de e-mail is bezorgd: Postvak IN/map, On-premises/Extern, Ongewenste e-mail, Quarantaine, Mislukt, Geplaatst, Verwijderde items</span><span class="sxs-lookup"><span data-stu-id="0bbef-134">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="0bbef-135">Ondersteunde gebeurtenistypen</span><span class="sxs-lookup"><span data-stu-id="0bbef-135">Supported event types</span></span>
<span data-ttu-id="0bbef-136">In deze tabel worden gebeurtenissen met de volgende waarden `ActionType` vastleggen:</span><span class="sxs-lookup"><span data-stu-id="0bbef-136">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="0bbef-137">**Handmatig herstel: een** beheerder heeft handmatig actie ondernomen op een e-mailbericht nadat het is bezorgd in het postvak van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="0bbef-137">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="0bbef-138">Dit geldt ook voor acties die handmatig worden [ondernomen](../office-365-security/threat-explorer.md) via Bedreigingsverkenner of goedkeuringen van acties voor geautomatiseerd onderzoek en antwoorden [(AIR).](mtp-autoir-actions.md)</span><span class="sxs-lookup"><span data-stu-id="0bbef-138">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](mtp-autoir-actions.md).</span></span>
- <span data-ttu-id="0bbef-139">**Phish ZAP** – [Zero-hour Auto Purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) heeft actie ondernomen op een phishing-e-mail na bezorging.</span><span class="sxs-lookup"><span data-stu-id="0bbef-139">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="0bbef-140">**Malware ZAP** – Zero-hour Auto Purge (ZAP) heeft actie ondernomen op een e-mailbericht dat malware bevat na bezorging.</span><span class="sxs-lookup"><span data-stu-id="0bbef-140">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0bbef-141">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="0bbef-141">Related topics</span></span>
- [<span data-ttu-id="0bbef-142">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="0bbef-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0bbef-143">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="0bbef-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0bbef-144">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="0bbef-144">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0bbef-145">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="0bbef-145">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0bbef-146">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="0bbef-146">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0bbef-147">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="0bbef-147">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
