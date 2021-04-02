---
title: E-mailEvents-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over gebeurtenissen die zijn gekoppeld aan Microsoft 365-e-mailberichten in de tabel EmailEvents van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, EmailEvents, network message id, sender, recipient, attachment id, attachment name, malware verdict, phishing verdict, attachment count, link count, url count
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 460668c281dff378867a721f4e3635a36cb590e2
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498898"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**

- Microsoft 365 Defender

De tabel in het geavanceerde schema bevat informatie over gebeurtenissen met betrekking tot het verwerken van `EmailEvents` e-mailberichten op Microsoft Defender voor Office 365. [](advanced-hunting-overview.md) Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

>[!TIP]
> Voor gedetailleerde informatie over de gebeurtenissentypen (waarden) die door een tabel worden ondersteund, gebruikt u de `ActionType` ingebouwde schemaverwijzing die beschikbaar is in het beveiligingscentrum.

Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Omschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is opgenomen |
| `NetworkMessageId` | tekenreeks | Unieke id voor het e-mailbericht, gegenereerd door Microsoft 365 |
| `InternetMessageId` | tekenreeks | Openbare id voor de e-mail die is ingesteld door het verzendende e-mailsysteem |
| `SenderMailFromAddress` | tekenreeks | E-mailadres van afzender in de koptekst MAIL FROM, ook wel de afzender van de envelop of het Return-Path genoemd |
| `SenderFromAddress` | tekenreeks | E-mailadres van afzender in de FROM-koptekst, die zichtbaar is voor e-mailontvangers op hun e-mail clients |
| `SenderDisplayName` | tekenreeks | Naam van de afzender die wordt weergegeven in het adresboek, meestal een combinatie van een gegeven of voornaam, een middelste initiale en een achternaam of achternaam |
| `SenderObjectId` | tekenreeks |Unieke id voor het account van de afzender in Azure AD |
| `SenderMailFromDomain` | tekenreeks | Afzenderdomein in de koptekst MAIL FROM, ook wel de afzender van de envelop of het Return-Path adres |
| `SenderFromDomain` | tekenreeks | Sender domain in the FROM header, which is visible to email recipients on their email clients |
| `SenderIPv4` | tekenreeks | IPv4-adres van de laatst gedetecteerde e-mailserver die het bericht heeft doorgestuurd |
| `SenderIPv6` | tekenreeks | IPv6-adres van de laatst gedetecteerde e-mailserver die het bericht heeft doorgestuurd |
| `RecipientEmailAddress` | tekenreeks | E-mailadres van de geadresseerde of e-mailadres van de geadresseerde na uitbreiding distributielijst |
| `RecipientObjectId` | tekenreeks | Unieke id voor de e-mailontvanger in Azure AD |
| `Subject` | tekenreeks | Onderwerp van het e-mailbericht |
| `EmailClusterId` | tekenreeks | Id voor de groep soortgelijke e-mailberichten gegroepeerd op basis van heuristische analyse van de inhoud |
| `EmailDirection` | tekenreeks | Richting van de e-mail ten opzichte van uw netwerk: Binnenkomende, Uitgaande, Intra-org |
| `DeliveryAction` | tekenreeks | Bezorgingsactie van het e-mailbericht: Bezorgd, Ongewenste e-mail, Geblokkeerd of Vervangen |
| `DeliveryLocation` | tekenreeks | Locatie waar het e-mailbericht is bezorgd: Postvak IN/Map, On-premises/Extern, Ongewenste e-mail, Quarantaine, Mislukt, Verwijderde items |
| `ThreatTypes` | tekenreeks | Oordeel van de filtertack voor e-mail over de vraag of de e-mail malware, phishing of andere bedreigingen bevat |
| `ThreatNames` | tekenreeks |Detectienaam voor malware of andere gevonden bedreigingen |
| `DetectionMethods` | tekenreeks | Methoden die worden gebruikt om malware, phishing of andere bedreigingen in de e-mail op te sporen |
| `ConfidenceLevel` | tekenreeks | Lijst met betrouwbaarheidsniveaus van spam- of phishingberichten. Voor spam wordt in deze kolom het betrouwbaarheidsniveau voor spam (SCL) aangegeven, waarmee wordt aangegeven of de e-mail is overgeslagen (-1), dat geen spam (0,1) is, dat spam met matige betrouwbaarheid (5,6) is of dat spam met veel vertrouwen is gevonden (9). Voor phishing wordt in deze kolom weergegeven of het betrouwbaarheidsniveau 'Hoog' of 'Laag' is. |
| `EmailAction` | tekenreeks | Definitieve actie voor het e-mailbericht op basis van filteruitspraak, beleid en gebruikersacties: Bericht verplaatsen naar map ongewenste e-mail, X-koptekst toevoegen, Onderwerp wijzigen, Bericht omleiden, Bericht verwijderen, verzenden naar quarantaine, Geen actie ondernomen, BCC-bericht |
| `EmailActionPolicy` | tekenreeks | Actiebeleid dat van kracht is: Antispam met hoog vertrouwen, Antispam, Antispam bulkmail, Antispam phishing, Anti-phishing domein imitatie, Anti-phishing gebruikers imitatie, Anti-phishing spoof, Anti-phishing graph impersonation, Antimalware, Safe Attachments, Enterprise Transport Rules (ETR) |
| `EmailActionPolicyGuid` | tekenreeks | Unieke id voor het beleid dat de uiteindelijke e-mailactie heeft bepaald |
| `AttachmentCount` | int | Aantal bijlagen in het e-mailbericht |
| `UrlCount` | int | Aantal ingesloten URL's in de e-mail |
| `EmailLanguage` | tekenreeks | Gedetecteerde taal van de e-mailinhoud |
| `Connectors` | tekenreeks | Aangepaste instructies voor het definiëren van de organisatie-e-mailstroom en de manier waarop de e-mail is gerouteerd |
| `OrgLevelAction` | tekenreeks | Actie ondernomen op het e-mailbericht als antwoord op overeenkomsten met een beleid dat is gedefinieerd op organisatieniveau |
| `OrgLevelPolicy` | tekenreeks | Organisatiebeleid dat de actie heeft geactiveerd die is ondernomen op het e-mailbericht |
| `UserLevelAction` | tekenreeks | Actie ondernomen op het e-mailbericht als antwoord op overeenkomsten met een postvakbeleid dat door de geadresseerde is gedefinieerd |
| `UserLevelPolicy` | tekenreeks | Postvakbeleid van eindgebruiker die de actie heeft geactiveerd die is ondernomen op het e-mailbericht |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp. |

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
