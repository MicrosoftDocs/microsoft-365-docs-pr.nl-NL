---
title: MailPostDeliveryEvents tabel in de geavanceerde jacht schema
description: Meer informatie over acties na levering op Microsoft 365-e-mails in de tabel EmailPostDeliveryEvents van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, gegevenstype, beschrijving, EmailPostDeliveryEvents, netwerk bericht id, afzender, ontvanger, bijlage id, bijlage naam, malware verdict, phishing verdict, bijlage tellen, link tellen, url tellen
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: f5c226b6028c845acc674ec0a0536727386c2380
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899385"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

**Van toepassing op:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

De `EmailPostDeliveryEvents` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over acties na levering die zijn uitgevoerd op e-mailberichten die door Microsoft 365 zijn verwerkt. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Voor meer informatie over afzonderlijke e-mailberichten u ook de [`EmailEvents`](advanced-hunting-emailevents-table.md) tabellen en de tabellen [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) gebruiken. Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `EventId` | Tekenreeks | Unieke id voor het evenement |
| `NetworkMessageId` | Tekenreeks | Unieke id voor de e-mail, gegenereerd door Microsoft 365 |
| `InternetMessageId` | Tekenreeks | Openbare id voor de e-mail die is ingesteld door het verzendende e-mailsysteem |
| `Action` | Tekenreeks | Maatregelen tegen de entiteit |
| `ActionType` | Tekenreeks | Type activiteit dat de gebeurtenis heeft geactiveerd: Handmatige sanering, Phish ZAP, Malware ZAP |
| `ActionTrigger` | Tekenreeks | Geeft aan of een actie is geactiveerd door een beheerder (handmatig of door goedkeuring van een in behandeling zijnde geautomatiseerde actie) of door een speciaal mechanisme, zoals een ZAP of Dynamic Delivery |
| `ActionResult` | Tekenreeks | Resultaat van de actie |
| `RecipientEmailAddress` | Tekenreeks | E-mailadres van de ontvanger of e-mailadres van de ontvanger na uitbreiding van de distributielijst |
| `DeliveryLocation` | Tekenreeks | Locatie waar de e-mail is bezorgd: Postvak IN/map, On-premises/Extern, Ongewenste e-mail, Quarantaine, Mislukt, Verwijderd, Verwijderde items |

## <a name="supported-event-types"></a>Ondersteunde gebeurtenistypen
In deze tabel worden gebeurtenissen met de volgende `ActionType` waarden vastgelegd:

- **Handmatige herstel** : een beheerder heeft handmatig actie ondernomen op een e-mailbericht nadat het is afgeleverd bij het postvak van de gebruiker. Dit omvat acties die handmatig worden uitgevoerd via [Threat Explorer](../office-365-security/threat-explorer.md) of goedkeuringen van [geautomatiseerde acties voor onderzoek en respons (AIR).](mtp-autoir-actions.md)
- **Phish ZAP** - [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) heeft actie ondernomen op een phishing-e-mail na levering.
- **Malware ZAP** - Zero-hour auto purge (ZAP) heeft actie ondernomen op een e-mailbericht gevonden met malware na levering.

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)