---
title: E-mailPostDeliveryEvents-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over acties na levering die zijn ondernomen op Microsoft 365-e-mailberichten in de tabel EmailPostDeliveryEvents van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, EmailPostDeliveryEvents, network message id, sender, recipient, attachment id, attachment name, malware verdict, phishing, attachment count, link count, url count, url count
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 25f1a177571862e92c502b584bbd51801141069a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060593"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="6c4be-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="6c4be-104">EmailPostDeliveryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6c4be-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="6c4be-105">**Applies to:**</span></span>
- <span data-ttu-id="6c4be-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6c4be-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6c4be-107">De tabel in het geavanceerde schema bevat informatie over acties na bezorging die zijn uitgevoerd op e-mailberichten die zijn verwerkt `EmailPostDeliveryEvents` door Microsoft [](advanced-hunting-overview.md) 365.</span><span class="sxs-lookup"><span data-stu-id="6c4be-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="6c4be-108">Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.</span><span class="sxs-lookup"><span data-stu-id="6c4be-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="6c4be-109">Voor gedetailleerde informatie over de gebeurtenissentypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` ingebouwde schemaverwijzing die beschikbaar is in het beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="6c4be-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="6c4be-110">Voor meer informatie over afzonderlijke e-mailberichten kunt u ook de [`EmailEvents`](advanced-hunting-emailevents-table.md) , en de tabellen [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6c4be-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="6c4be-111">Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="6c4be-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6c4be-112">Kolomnaam</span><span class="sxs-lookup"><span data-stu-id="6c4be-112">Column name</span></span> | <span data-ttu-id="6c4be-113">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="6c4be-113">Data type</span></span> | <span data-ttu-id="6c4be-114">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="6c4be-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6c4be-115">datetime</span><span class="sxs-lookup"><span data-stu-id="6c4be-115">datetime</span></span> | <span data-ttu-id="6c4be-116">Datum en tijd waarop de gebeurtenis is opgenomen</span><span class="sxs-lookup"><span data-stu-id="6c4be-116">Date and time when the event was recorded</span></span> |
| `NetworkMessageId` | <span data-ttu-id="6c4be-117">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6c4be-117">string</span></span> | <span data-ttu-id="6c4be-118">Unieke id voor het e-mailbericht, gegenereerd door Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6c4be-118">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="6c4be-119">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6c4be-119">string</span></span> | <span data-ttu-id="6c4be-120">Openbare id voor de e-mail die is ingesteld door het verzendende e-mailsysteem</span><span class="sxs-lookup"><span data-stu-id="6c4be-120">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="6c4be-121">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6c4be-121">string</span></span> | <span data-ttu-id="6c4be-122">Actie ondernomen op de entiteit</span><span class="sxs-lookup"><span data-stu-id="6c4be-122">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="6c4be-123">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6c4be-123">string</span></span> | <span data-ttu-id="6c4be-124">Type activiteit dat de gebeurtenis heeft geactiveerd: Handmatig herstellen, Phish ZAP, Malware ZAP</span><span class="sxs-lookup"><span data-stu-id="6c4be-124">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="6c4be-125">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6c4be-125">string</span></span> | <span data-ttu-id="6c4be-126">Geeft aan of een actie is geactiveerd door een beheerder (handmatig of door goedkeuring van een geautomatiseerde actie in behandeling) of door een speciaal mechanisme, zoals een ZAP of Dynamische bezorging</span><span class="sxs-lookup"><span data-stu-id="6c4be-126">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="6c4be-127">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6c4be-127">string</span></span> | <span data-ttu-id="6c4be-128">Resultaat van de actie</span><span class="sxs-lookup"><span data-stu-id="6c4be-128">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="6c4be-129">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6c4be-129">string</span></span> | <span data-ttu-id="6c4be-130">E-mailadres van de geadresseerde of e-mailadres van de geadresseerde na uitbreiding distributielijst</span><span class="sxs-lookup"><span data-stu-id="6c4be-130">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="6c4be-131">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="6c4be-131">string</span></span> | <span data-ttu-id="6c4be-132">Locatie waar het e-mailbericht is bezorgd: Postvak IN/Map, On-premises/Extern, Ongewenste e-mail, Quarantaine, Mislukt, Verwijderde items</span><span class="sxs-lookup"><span data-stu-id="6c4be-132">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |
| `ReportId` | <span data-ttu-id="6c4be-133">lang</span><span class="sxs-lookup"><span data-stu-id="6c4be-133">long</span></span> | <span data-ttu-id="6c4be-134">Gebeurtenis-id op basis van een herhalende teller.</span><span class="sxs-lookup"><span data-stu-id="6c4be-134">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="6c4be-135">Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp.</span><span class="sxs-lookup"><span data-stu-id="6c4be-135">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="6c4be-136">Ondersteunde gebeurtenistypen</span><span class="sxs-lookup"><span data-stu-id="6c4be-136">Supported event types</span></span>
<span data-ttu-id="6c4be-137">In deze tabel worden gebeurtenissen met de volgende waarden `ActionType` vast gelegd:</span><span class="sxs-lookup"><span data-stu-id="6c4be-137">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="6c4be-138">**Handmatig herstellen:** een beheerder heeft handmatig actie ondernomen voor een e-mailbericht nadat het is bezorgd in het postvak van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="6c4be-138">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="6c4be-139">Dit geldt ook voor acties die handmatig worden ondernomen via [Threat Explorer](../defender-365-security/threat-explorer.md) of goedkeuringen van geautomatiseerde onderzoek- en [antwoordacties (AIR).](m365d-autoir-actions.md)</span><span class="sxs-lookup"><span data-stu-id="6c4be-139">This includes actions taken manually through [Threat Explorer](../defender-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](m365d-autoir-actions.md).</span></span>
- <span data-ttu-id="6c4be-140">**Phish ZAP** – [Zero-hour Auto Purge (ZAP)](../defender-365-security/zero-hour-auto-purge.md) heeft actie ondernomen op een phishing-e-mail na de bezorging.</span><span class="sxs-lookup"><span data-stu-id="6c4be-140">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../defender-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="6c4be-141">**Malware ZAP** - Zap (Zero Hour Auto Purge) heeft actie ondernomen op een e-mailbericht dat malware bevat na de bezorging.</span><span class="sxs-lookup"><span data-stu-id="6c4be-141">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6c4be-142">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="6c4be-142">Related topics</span></span>
- [<span data-ttu-id="6c4be-143">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="6c4be-143">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6c4be-144">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="6c4be-144">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6c4be-145">Gedeelde query's gebruiken</span><span class="sxs-lookup"><span data-stu-id="6c4be-145">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6c4be-146">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="6c4be-146">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6c4be-147">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="6c4be-147">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6c4be-148">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="6c4be-148">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
