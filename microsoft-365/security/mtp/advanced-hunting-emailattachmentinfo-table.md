---
title: EmailAttachmentInfo-tabel in het geavanceerde jacht schema
description: Meer informatie over e-mailbijlage gegevens in de tabel EmailAttachmentInfo van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber bedreigings jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema Reference, kusto, Table, Column, datatype, een beschrijving, EmailAttachmentInfo, e-mail type, naam van schadelijke software verdict
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
ms.openlocfilehash: ce80b68784392f5e74f18378e7f074b8273fe73b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198095"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection



De `EmailAttachmentInfo` tabel in het [geavanceerde jacht](advanced-hunting-overview.md) -schema bevat informatie over bijlagen voor e-mailberichten die zijn verwerkt door Office 365 ATP. Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.

Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | tijd | De datum en tijd waarop de gebeurtenis is vastgelegd |
| `AttachmentId` | tekenreeks | Unieke e-mailbijlage-id |
| `NetworkMessageId` | tekenreeks | Unieke id voor de e-mail, gegenereerd door Microsoft 365 |
| `SenderFromAddress` | tekenreeks | Het e-mailadres van de afzender in de header van, die zichtbaar is voor e-mail geadresseerden op de e-mailclients |
| `RecipientEmailAddress` | tekenreeks | Het e-mailadres van de geadresseerde of het e-mailadres van de geadresseerde na expansie van distributielijst |
| `FileName` | tekenreeks | De naam van het bestand waarop de opgenomen actie is toegepast |
| `FileType` | tekenreeks | Type bestandsextensie |
| `SHA256` | tekenreeks | SHA-256 van het bestand waarop de opgenomen actie is toegepast. Dit veld wordt meestal niet ingevuld, met behulp van de SHA1-kolom. |
| `MalwareFilterVerdict` | tekenreeks | Verdict van de filters stapel voor e-mail om te bepalen of het e-mailbericht malware bevat: malware, geen malware |
| `MalwareDetectionMethod` | tekenreeks | Methode voor het detecteren van malware in de e-mail: antimalware-engine, reputatie van bestanden, veilige bijlagen van ATP |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
