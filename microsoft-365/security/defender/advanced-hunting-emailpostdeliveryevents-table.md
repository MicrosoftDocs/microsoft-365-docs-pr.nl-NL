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
ms.openlocfilehash: 8940d1dd370f804f8539bf4e753b1112d3c8d3bf
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198195"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

De tabel in het geavanceerde schema bevat informatie over acties na bezorging die zijn uitgevoerd op e-mailberichten die zijn verwerkt `EmailPostDeliveryEvents` door Microsoft [](advanced-hunting-overview.md) 365. Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

>[!TIP]
> Voor gedetailleerde informatie over de gebeurtenissentypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` ingebouwde schemaverwijzing die beschikbaar is in het beveiligingscentrum.

Voor meer informatie over afzonderlijke e-mailberichten kunt u ook de [`EmailEvents`](advanced-hunting-emailevents-table.md) , en de tabellen [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) gebruiken. Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is opgenomen |
| `NetworkMessageId` | tekenreeks | Unieke id voor het e-mailbericht, gegenereerd door Microsoft 365 |
| `InternetMessageId` | tekenreeks | Openbare id voor de e-mail die is ingesteld door het verzendende e-mailsysteem |
| `Action` | tekenreeks | Actie ondernomen op de entiteit |
| `ActionType` | tekenreeks | Type activiteit dat de gebeurtenis heeft geactiveerd: Handmatig herstellen, Phish ZAP, Malware ZAP |
| `ActionTrigger` | tekenreeks | Geeft aan of een actie is geactiveerd door een beheerder (handmatig of door goedkeuring van een geautomatiseerde actie in behandeling) of door een speciaal mechanisme, zoals een ZAP of Dynamische bezorging |
| `ActionResult` | tekenreeks | Resultaat van de actie |
| `RecipientEmailAddress` | tekenreeks | E-mailadres van de geadresseerde of e-mailadres van de geadresseerde na uitbreiding distributielijst |
| `DeliveryLocation` | tekenreeks | Locatie waar het e-mailbericht is bezorgd: Postvak IN/Map, On-premises/Extern, Ongewenste e-mail, Quarantaine, Mislukt, Verwijderde items |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp. |

## <a name="supported-event-types"></a>Ondersteunde gebeurtenistypen
In deze tabel worden gebeurtenissen met de volgende waarden `ActionType` vast gelegd:

- **Handmatig herstellen:** een beheerder heeft handmatig actie ondernomen voor een e-mailbericht nadat het is bezorgd in het postvak van de gebruiker. Dit geldt ook voor acties die handmatig worden ondernomen via [Threat Explorer](../office-365-security/threat-explorer.md) of goedkeuringen van geautomatiseerde onderzoek- en [antwoordacties (AIR).](m365d-autoir-actions.md)
- **Phish ZAP** – [Zero-hour Auto Purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) heeft actie ondernomen op een phishing-e-mail na de bezorging.
- **Malware ZAP** - Zap (Zero Hour Auto Purge) heeft actie ondernomen op een e-mailbericht dat malware bevat na de bezorging.

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
