---
title: De tabel EmailAttachmentInfo in het geavanceerde schema voor zoeken
description: Meer informatie over informatie over e-mailbijlagen in de tabel EmailAttachmentInfo van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, EmailAttachmentInfo, network message id, sender, recipient, attachment id, attachment name, malware wordt gebruikt
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
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b810d7b15ef47a33a0675086219d2193cea00f2e
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145017"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender



De tabel in het geavanceerde schema voor zoeken bevat informatie over bijlagen in e-mailberichten die worden `EmailAttachmentInfo` verwerkt door Microsoft Defender voor Office 365. [](advanced-hunting-overview.md) Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is vastgelegd |
| `NetworkMessageId` | tekenreeks | Unieke id voor het e-mailbericht, gegenereerd door Microsoft 365 |
| `SenderFromAddress` | tekenreeks | Het e-mailadres van de afzender in de FROM-header, die zichtbaar is voor e-mailontvangers in hun e-mail clients |
| `SenderDisplayName` | tekenreeks | De naam van de afzender die wordt weergegeven in het adresboek, meestal een combinatie van een bepaalde of voornaam, een middelste initiitiitie en een achternaam of achternaam. |
| `SenderObjectId` | tekenreeks | Unieke id voor het account van de afzender in Azure AD |
| `RecipientEmailAddress` | tekenreeks | Het e-mailadres van de geadresseerde of het e-mailadres van de ontvanger na uitbreiding van de distributielijst |
| `RecipientObjectId` | tekenreeks | Unieke id voor de e-mailontvanger in Azure AD |
| `FileName` | tekenreeks | Naam van het bestand waar de opgenomen actie op is toegepast |
| `FileType` | tekenreeks | Bestandsextensietype |
| `SHA256` | tekenreeks | SHA-256 van het bestand waar de opgenomen actie op is toegepast. Dit veld wordt meestal niet ingevuld. Gebruik indien beschikbaar de kolom SHA1. |
| `MalwareFilterVerdict` | tekenreeks | Door het gebruik van e-mailfilters wordt bepaald of de e-mail malware bevat: Malware, Geen malware |
| `MalwareDetectionMethod` | tekenreeks | Methode die wordt gebruikt om malware in het e-mailbericht te detecteren: Antimalware-engine, Bestandsreputatie, Veilige bijlagen |
| `ThreatTypes` | tekenreeks | Op basis van het gebruik van e-mailfilters wordt bepaald of de e-mail malware, phishing of andere bedreigingen bevat. |
| `ThreatNames` | tekenreeks | Naam van detectie voor malware of andere bedreigingen gevonden |
| `DetectionMethods` | tekenreeks | Methoden die worden gebruikt om malware, phishing of andere bedreigingen te detecteren die in de e-mail worden gevonden |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp. |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
