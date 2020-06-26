---
title: MailAttachmentInfo tabel in het geavanceerde jachtschema
description: Meer informatie over e-mailbijlagen vindt u in de tabel EmailAttachmentInfo van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, gegevenstype, beschrijving, EmailAttachmentInfo, netwerk bericht id, afzender, ontvanger, bijlage id, bijlage naam, malware verdict
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
ms.openlocfilehash: c396689942a72a03120f0acd41d0d76abb720702
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899397"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

**Van toepassing op:**
- Microsoft Threat Protection



De `EmailAttachmentInfo` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over bijlagen in e-mails die door Office 365 ATP worden verwerkt. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `AttachmentId` | Tekenreeks | Unieke id voor e-mailbijlagen |
| `NetworkMessageId` | Tekenreeks | Unieke id voor de e-mail, gegenereerd door Microsoft 365 |
| `SenderFromAddress` | Tekenreeks | E-mailadres van afzender in de koptekst VAN, die zichtbaar is voor e-mailontvangers op hun e-mailclients |
| `RecipientEmailAddress` | Tekenreeks | E-mailadres van de ontvanger of e-mailadres van de ontvanger na uitbreiding van de distributielijst |
| `FileName` | Tekenreeks | Naam van het bestand waarop de geregistreerde actie is toegepast |
| `FileType` | Tekenreeks | Type bestandsextensie |
| `SHA256` | Tekenreeks | SHA-256 van het bestand waarop de geregistreerde actie is toegepast. Dit veld wordt meestal niet ingevuld - gebruik de SHA1-kolom indien beschikbaar. |
| `MalwareFilterVerdict` | Tekenreeks | Oordeel van de e-mail filteren stack op de vraag of de e-mail bevat malware: Malware, Niet malware |
| `MalwareDetectionMethod` | Tekenreeks | Methode die wordt gebruikt om malware in de e-mail te detecteren: Antimalware engine, Bestandsreputatie, ATP Safe Attachments |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
