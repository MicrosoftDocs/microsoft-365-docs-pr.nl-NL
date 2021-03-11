---
title: Tabel EmailPostDeliveryEvents in het geavanceerde schema voor zoeken
description: Meer informatie over acties na de bezorging van Microsoft 365-e-mailberichten in de tabel EmailPostDeliveryEvents van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, EmailPostDeliveryEvents, network message id, sender, recipient, attachment id, attachment name, malware phishing op basis van phishing, attachment count, link count, url count
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
ms.openlocfilehash: 6e12ddfc402f1bd420f57369cc6d54f2e670d710
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712376"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

De tabel in het geavanceerde schema voor zoeken bevat informatie over acties na bezorging die zijn uitgevoerd op e-mailberichten die worden `EmailPostDeliveryEvents` verwerkt door Microsoft 365. [](advanced-hunting-overview.md) Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

>[!TIP]
> Voor gedetailleerde informatie over de gebeurtenistypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` ingebouwde schemaverwijzing in het beveiligingscentrum.

Voor meer informatie over afzonderlijke e-mailberichten kunt u ook de [`EmailEvents`](advanced-hunting-emailevents-table.md) tabellen en de tabellen [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) gebruiken. Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is vastgelegd |
| `NetworkMessageId` | tekenreeks | Unieke id voor het e-mailbericht, gegenereerd door Microsoft 365 |
| `InternetMessageId` | tekenreeks | Openbare id voor de e-mail die wordt ingesteld door het verzendende e-mailsysteem |
| `Action` | tekenreeks | Actie ondernomen op de entiteit |
| `ActionType` | tekenreeks | Het type activiteit dat de gebeurtenis heeft geactiveerd: Handmatige oplossing, Phish ZAP, Malware ZAP |
| `ActionTrigger` | tekenreeks | Geeft aan of een actie is geactiveerd door een beheerder (handmatig of via goedkeuring van een geautomatiseerde actie in behandeling) of door een speciaal mechanisme, zoals ZAP of Dynamic Delivery |
| `ActionResult` | tekenreeks | Resultaat van de actie |
| `RecipientEmailAddress` | tekenreeks | Het e-mailadres van de geadresseerde of het e-mailadres van de ontvanger na uitbreiding van de distributielijst |
| `DeliveryLocation` | tekenreeks | Locatie waar de e-mail is bezorgd: Postvak IN/map, On-premises/Extern, Ongewenste e-mail, Quarantaine, Mislukt, Geplaatst, Verwijderde items |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp. |

## <a name="supported-event-types"></a>Ondersteunde gebeurtenistypen
In deze tabel worden gebeurtenissen met de volgende waarden `ActionType` vastleggen:

- **Handmatig herstel: een** beheerder heeft handmatig actie ondernomen op een e-mailbericht nadat het is bezorgd in het postvak van de gebruiker. Dit geldt ook voor acties die handmatig worden [ondernomen](../office-365-security/threat-explorer.md) via Bedreigingsverkenner of goedkeuringen van acties voor geautomatiseerd onderzoek en antwoorden [(AIR).](mtp-autoir-actions.md)
- **Phish ZAP** – [Zero-hour Auto Purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) heeft actie ondernomen op een phishing-e-mail na bezorging.
- **Malware ZAP** – Zero-hour Auto Purge (ZAP) heeft actie ondernomen op een e-mailbericht dat malware bevat na bezorging.

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
