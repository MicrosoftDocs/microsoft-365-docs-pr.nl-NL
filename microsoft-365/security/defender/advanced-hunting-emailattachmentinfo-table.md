---
title: De tabel EmailAttachmentInfo in het geavanceerde schema voor de jacht
description: Meer informatie over e-mailbijlagegegevens in de tabel EmailAttachmentInfo van het geavanceerde schema voor het zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, EmailAttachmentInfo, network message id, sender, recipient, attachment id, attachment name, malware verdict
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 84d0c1fd256b013291e3df33dc5d7a0524741685
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498932"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender



De tabel in het geavanceerde schema bevat informatie over bijlagen in e-mailberichten die zijn verwerkt door `EmailAttachmentInfo` Microsoft Defender voor Office 365. [](advanced-hunting-overview.md) Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Omschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is opgenomen |
| `NetworkMessageId` | tekenreeks | Unieke id voor het e-mailbericht, gegenereerd door Microsoft 365 |
| `SenderFromAddress` | tekenreeks | E-mailadres van afzender in de FROM-koptekst, die zichtbaar is voor e-mailontvangers op hun e-mail clients |
| `SenderDisplayName` | tekenreeks | Naam van de afzender die wordt weergegeven in het adresboek, meestal een combinatie van een gegeven of voornaam, een middelste initiale en een achternaam of achternaam |
| `SenderObjectId` | tekenreeks | Unieke id voor het account van de afzender in Azure AD |
| `RecipientEmailAddress` | tekenreeks | E-mailadres van de geadresseerde of e-mailadres van de geadresseerde na uitbreiding distributielijst |
| `RecipientObjectId` | tekenreeks | Unieke id voor de e-mailontvanger in Azure AD |
| `FileName` | tekenreeks | Naam van het bestand waar de opgenomen actie op is toegepast |
| `FileType` | tekenreeks | Bestandsextensietype |
| `SHA256` | tekenreeks | SHA-256 van het bestand waar de opgenomen actie op is toegepast. Dit veld wordt meestal niet ingevuld: gebruik de kolom SHA1 wanneer deze beschikbaar is. |
| `ThreatTypes` | tekenreeks | Oordeel van de filtertack voor e-mail over de vraag of de e-mail malware, phishing of andere bedreigingen bevat |
| `ThreatNames` | tekenreeks | Detectienaam voor malware of andere gevonden bedreigingen |
| `DetectionMethods` | tekenreeks | Methoden die worden gebruikt om malware, phishing of andere bedreigingen in de e-mail op te sporen |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp. |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
