---
title: De tabel EmailEvents in het geavanceerde schema voor zoeken
description: Meer informatie over gebeurtenissen die zijn gekoppeld aan Microsoft 365-e-mailberichten in de tabel EmailEvents van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, EmailEvents, network message id, sender, recipient, attachment id, attachment name, attachment name, malware op basis van phishing, attachment attachment attachment count, link count, url count
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
ms.openlocfilehash: 5e9fce199d253cf22f73ec8620c5441d8bf1305d
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712388"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

De tabel in het geavanceerde zoekschema bevat informatie over gebeurtenissen die betrekking hebben op de verwerking van e-mailberichten op `EmailEvents` Microsoft Defender voor Office 365. [](advanced-hunting-overview.md) Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

>[!TIP]
> Voor gedetailleerde informatie over de gebeurtenistypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` ingebouwde schemaverwijzing in het beveiligingscentrum.

Zie het geavanceerde zoekschema voor informatie over andere tabellen in het geavanceerde schema voor [het zoeken.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is vastgelegd |
| `NetworkMessageId` | tekenreeks | Unieke id voor het e-mailbericht, gegenereerd door Microsoft 365 |
| `InternetMessageId` | tekenreeks | Openbare id voor de e-mail die wordt ingesteld door het verzendende e-mailsysteem |
| `SenderMailFromAddress` | tekenreeks | Het e-mailadres van de afzender in de kop MAIL FROM, ook wel de afzender van de envelop genoemd of het Return-Path mailadres |
| `SenderFromAddress` | tekenreeks | Het e-mailadres van de afzender in de FROM-header, die zichtbaar is voor e-mailontvangers in hun e-mail clients |
| `SenderDisplayName` | tekenreeks | De naam van de afzender die wordt weergegeven in het adresboek, meestal een combinatie van een bepaalde of voornaam, een middelste initiitiitie en een achternaam of achternaam. |
| `SenderObjectId` | tekenreeks |Unieke id voor het account van de afzender in Azure AD |
| `SenderMailFromDomain` | tekenreeks | Sender domain in the MAIL FROM header, also known as the envelope sender or the Return-Path address |
| `SenderFromDomain` | tekenreeks | Sender domain in the FROM header, which is visible to email recipients on their email clients |
| `SenderIPv4` | tekenreeks | IPv4-adres van de laatst gedetecteerde e-mailserver die het bericht heeft doorgestuurd |
| `SenderIPv6` | tekenreeks | IPv6-adres van de laatst gedetecteerde e-mailserver die het bericht heeft doorgestuurd |
| `RecipientEmailAddress` | tekenreeks | Het e-mailadres van de geadresseerde of het e-mailadres van de ontvanger na uitbreiding van de distributielijst |
| `RecipientObjectId` | tekenreeks | Unieke id voor de e-mailontvanger in Azure AD |
| `Subject` | tekenreeks | Onderwerp van de e-mail |
| `EmailClusterId` | tekenreeks | Id voor de groep vergelijkbare e-mailberichten gegroepeerd op basis van heuristische analyse van de inhoud |
| `EmailDirection` | tekenreeks | Richting van het e-mailbericht ten opzichte van uw netwerk: Binnenkomende, uitgaande, rente-organisatie |
| `DeliveryAction` | tekenreeks | Bezorgingsactie van het e-mailbericht: Bezorgd, Ongewenste e-mail, Geblokkeerd of Vervangen |
| `DeliveryLocation` | tekenreeks | Locatie waar de e-mail is bezorgd: Postvak IN/map, On-premises/Extern, Ongewenste e-mail, Quarantaine, Mislukt, Geplaatst, Verwijderde items |
| `ThreatTypes` | tekenreeks | Op basis van het gebruik van e-mailfilters wordt bepaald of de e-mail malware, phishing of andere bedreigingen bevat. |
| `ThreatNames` | tekenreeks |Naam van detectie voor malware of andere bedreigingen gevonden |
| `DetectionMethods` | tekenreeks | Methoden die worden gebruikt om malware, phishing of andere bedreigingen te detecteren die in de e-mail worden gevonden |
| `ConfidenceLevel` | tekenreeks | Lijst met betrouwbaarheidsniveaus van eventuele spam- of phishingberichten. Voor spam toont deze kolom het betrouwbaarheidsniveau voor spam, waarmee wordt aangegeven of de e-mail is overgeslagen (-1), die wordt gevonden als geen spam (0,1), die spam met een gemiddelde betrouwbaarheid (5,6) of als spam met hoge betrouwbaarheid (9) blijkt te zijn. Bij phishing wordt in deze kolom weergegeven of het betrouwbaarheidsniveau 'Hoog' of 'Laag' is. |
| `EmailAction` | tekenreeks | Uiteindelijke actie die wordt ondernomen op basis van filterbeleid, beleid en gebruikersacties: Bericht verplaatsen naar map Ongewenste e-mail, X-koptekst toevoegen, Onderwerp wijzigen, Bericht omleiden, Bericht verwijderen, Verzenden naar quarantaine, Geen actie ondernomen, BCC-bericht |
| `EmailActionPolicy` | tekenreeks | Actiebeleid dat van kracht is: antispam met hoge betrouwbaarheid, Antispam, Antispam-bulkmail, Antispam-phishing, Imitatie van anti-phishingdomein, Imitatie van anti-phishinggebruikers, Anti-phishing-spoofing, Anti-Phishing Graph-imitatie, Antimalware, Veilige bijlagen, ETR (Enterprise Transport Rules) |
| `EmailActionPolicyGuid` | tekenreeks | Unieke id voor het beleid dat de uiteindelijke e-mailactie bepaalt |
| `AttachmentCount` | int | Aantal bijlagen in de e-mail |
| `UrlCount` | int | Aantal ingesloten URL's in de e-mail |
| `EmailLanguage` | tekenreeks | Taal van de e-mailinhoud gedetecteerd |
| `Connectors` | tekenreeks | Aangepaste instructies die de e-mailstroom van de organisatie definiëren en bepalen hoe de e-mail is doorgestuurd |
| `OrgLevelAction` | tekenreeks | Actie die wordt ondernomen op het e-mailbericht als reactie op overeenkomsten met een beleid dat is gedefinieerd op organisatieniveau |
| `OrgLevelPolicy` | tekenreeks | Organisatiebeleid dat de actie heeft veroorzaakt die wordt ondernomen op het e-mailbericht |
| `UserLevelAction` | tekenreeks | Actie die wordt ondernomen op de e-mail als reactie op overeenkomsten met een postvakbeleid dat is gedefinieerd door de geadresseerde |
| `UserLevelPolicy` | tekenreeks | Postvakbeleid voor eindgebruikers dat de actie heeft veroorzaakt die wordt ondernomen op de e-mail |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp. |

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
