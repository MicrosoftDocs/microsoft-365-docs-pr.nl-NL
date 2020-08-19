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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 88074de8792124557c65b5be074e3b02bfec2511
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797884"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

**Van toepassing op:**
- Microsoft Threat Protection

De `EmailPostDeliveryEvents` tabel in het [Geavanceerde](advanced-hunting-overview.md) bezorgings schema bevat informatie over acties voor de bezorging van de bezorging van e-mailberichten die worden verwerkt door Microsoft 365. Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.

>[!TIP]
> Voor gedetailleerde informatie over de typen gebeurtenissen ( `ActionType` waarden) die door een tabel worden ondersteund, gebruikt u de [ingebouwde schema verwijzing](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) die beschikbaar is in het Beveiligingscentrum.

Als u meer informatie wilt over afzonderlijke e-mailberichten, kunt u ook de [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) tabellen, en de [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tabellen gebruiken. Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | tijd | De datum en tijd waarop de gebeurtenis is vastgelegd |
| `EventId` | tekenreeks | Unieke id voor de gebeurtenis |
| `NetworkMessageId` | tekenreeks | Unieke id voor de e-mail, gegenereerd door Microsoft 365 |
| `InternetMessageId` | tekenreeks | Openbare id voor het e-mailbericht dat wordt ingesteld door het verzendende e-mailsysteem |
| `Action` | tekenreeks | Actie die is uitgevoerd voor de entiteit |
| `ActionType` | tekenreeks | Type activiteit dat de gebeurtenis heeft veroorzaakt: handmatig herbemiddeling, Phishman, malware ZAP |
| `ActionTrigger` | tekenreeks | Geeft aan of een actie is geactiveerd door een beheerder (handmatig of via goedkeuring van een geautomatiseerde actie in behandeling), of met een speciaal mechanisme, zoals een ZAP-of dynamische bezorging |
| `ActionResult` | tekenreeks | Resultaat van de actie |
| `RecipientEmailAddress` | tekenreeks | Het e-mailadres van de geadresseerde of het e-mailadres van de geadresseerde na expansie van distributielijst |
| `DeliveryLocation` | tekenreeks | De locatie waar het e-mailbericht is bezorgd: Postvak in/map, on-premises/extern, ongewenste E-mail, Quarantine, mislukt, neergezette, verwijderde items |

## <a name="supported-event-types"></a>Ondersteunde gebeurtenistypen
In deze tabel worden gebeurtenissen vastgelegd met de volgende `ActionType` waarden:

- **Handmatig herstel** : een beheerder heeft handmatig een actie uitgevoerd voor een e-mailbericht nadat het is afgeleverd bij het gebruikerspostvak. Dit omvat ook acties die u handmatig hebt uitgevoerd via de [bedreigings Verkenner](../office-365-security/threat-explorer.md) of de goedkeuring van [automatisch onderzoek en antwoord acties (lucht)](mtp-autoir-actions.md).
- **Phishing ZAP** - [Zero-Hour auto leegmaak (ZAP)](../office-365-security/zero-hour-auto-purge.md) nam na ontvangst actie een malafide e-mailbericht.
- **Malware ZAP** -voor een e-mailbericht met malware na de levering de actie ' ZAP '.

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)