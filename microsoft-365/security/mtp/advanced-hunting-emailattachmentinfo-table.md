---
title: Tabel E-mailbijlageInfo in het geavanceerde jachtschema
description: Meer informatie over e-mailbijlagen in de tabel EmailAttachmentInfo van het geavanceerde jachtschema
keywords: geavanceerde jacht, dreigingsjacht, cyberdreigingsjacht, bescherming tegen microsoft-bedreigingen, microsoft 365, mtp, m365, zoekopdracht, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, beschrijving, e-mailbijlageinfo, netwerkbericht-id, afzender, ontvanger, bevestigings-id, naam van de bijlage, malware vonnis
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
ms.openlocfilehash: d35313cf481ecd6892725ae385e7db1032565611
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42810453"
---
# <a name="emailattachmentinfo"></a>E-mailbijlageInfo

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging



De `EmailAttachmentInfo` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over bijlagen bij e-mails die zijn verwerkt door Office 365 ATP. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Voor informatie over andere tabellen in de geavanceerde jacht schema, [zie de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `AttachmentId` | Tekenreeks | Unieke e-mailbijlage-id |
| `NetworkMessageId` | Tekenreeks | Unieke id voor de e-mail, gegenereerd door Office 365 |
| `SenderFromAddress` | Tekenreeks | E-mailadres van afzender in de HEADER VAN, dat zichtbaar is voor e-mailontvangers op hun e-mailclients |
| `RecipientEmailAddress` | Tekenreeks | E-mailadres van de ontvanger of e-mailadres van de ontvanger na uitbreiding van de distributielijst |
| `FileName` | Tekenreeks | Naam van het bestand waarop de opgenomen actie is toegepast |
| `FileType` | Tekenreeks | Type bestandsextensie |
| `SHA256` | Tekenreeks | SHA-256 van het bestand waarop de opgenomen actie is toegepast. Dit veld is meestal niet gevuld : gebruik de SHA1-kolom indien beschikbaar. |
| `MalwareFilterVerdict` | Tekenreeks | Oordeel van de e-mail filtering stack over de vraag of de e-mail malware bevat: Malware, Niet malware |
| `MalwareDetectionMethod` | Tekenreeks | Methode die wordt gebruikt om malware in de e-mail te detecteren: Antimalware-engine, bestandsreputatie, ATP-veilige bijlagen |

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief op zoek naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Het schema begrijpen](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
