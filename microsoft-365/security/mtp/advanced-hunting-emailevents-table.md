---
title: E-mailEvenementen tabel in de geavanceerde jacht schema
description: Meer informatie over gebeurtenissen die zijn gekoppeld aan Microsoft 365-e-mails in de tabel E-events van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, gegevenstype, beschrijving, E-mailevents, netwerkbericht id, afzender, ontvanger, bijlage id, bijlage naam, malware verdict, phishing verdict, bijlage tellen, link tellen, url tellen
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
ms.openlocfilehash: be86f446e05952f7e88dc32e12a6a0d05e380afd
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515853"
---
# <a name="emailevents"></a>EmailEvents

**Van toepassing op:**
- Microsoft Threat Protection



De `EmailEvents` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over gebeurtenissen met betrekking tot de verwerking van e-mails op Office 365 ATP. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `EmailId` | Tekenreeks | Unieke e-mail- en ontvanger-id |
| `NetworkMessageId` | Tekenreeks | Unieke id voor de e-mail, gegenereerd door Microsoft 365 |
| `InternetMessageId` | Tekenreeks | Openbare id voor de e-mail die is ingesteld door het verzendende e-mailsysteem |
| `SenderMailFromAddress` | Tekenreeks | E-mailadres verzenden in de koptekst MAIL FROM, ook wel bekend als de afzender van de envelop of het adres Retourpad |
| `SenderFromAddress` | Tekenreeks | E-mailadres van afzender in de koptekst VAN, die zichtbaar is voor e-mailontvangers op hun e-mailclients |
| `SenderMailFromDomain` | Tekenreeks | Afzenderdomein in de koptekst MAIL FROM, ook wel de afzender van de envelop of het adres Retourpad genoemd |
| `SenderFromDomain` | Tekenreeks | Afzenderdomein in de kop van FROM, dat zichtbaar is voor e-mailontvangers op hun e-mailclients |
| `SenderIPv4` | Tekenreeks | IPv4-adres van de laatst gedetecteerde e-mailserver die het bericht heeft doorgegeven |
| `SenderIPv6` | Tekenreeks | IPv6-adres van de laatst gedetecteerde e-mailserver die het bericht heeft doorgegeven |
| `RecipientEmailAddress` | Tekenreeks | E-mailadres van de ontvanger of e-mailadres van de ontvanger na uitbreiding van de distributielijst |
| `Subject` | Tekenreeks | Onderwerp van de e-mail |
| `EmailClusterId` | Tekenreeks | Identificatie voor de groep van soortgelijke e-mails geclusterd op basis van heuristische analyse van de inhoud ervan |
| `EmailDirection` | Tekenreeks | Richting van de e-mail ten opzichte van uw netwerk: Binnenkomend, Uitgaand, Intra-org |
| `DeliveryAction` | Tekenreeks | Leveringsactie van de e-mail: geleverd, ge junked, geblokkeerd of vervangen |
| `DeliveryLocation` | Tekenreeks | Locatie waar de e-mail is bezorgd: Postvak IN/map, On-premises/Extern, Ongewenste e-mail, Quarantaine, Mislukt, Verwijderd, Verwijderde items |
| `PhishFilterVerdict` | Tekenreeks | Oordeel van de e-mail filteren stack op de vraag of de e-mail is phish: Phish of Niet Phish |
| `PhishDetectionMethod` | Tekenreeks | Methode die wordt gebruikt om de e-mail te detecteren als een phish: Kwaadaardige URL reputatie, ATP Safe Links URL Detonation, Advanced phish filter, General phish filter, Anti-Spoof: Intra-org, Anti-spoof: external domain, Domain imitatation, User imitatation, Brand imitatation |
| `MalwareFilterVerdict` | Tekenreeks | Oordeel van de e-mail filteren stack op de vraag of de e-mail bevat malware: Malware, Niet malware |
| `MalwareDetectionMethod` | Tekenreeks | Methode die wordt gebruikt om malware in de e-mail te detecteren: Antimalware engine, Bestandsreputatie, ATP Safe Attachments |
| `FinalEmailAction` | Tekenreeks | Definitieve actie op de e-mail op basis van filteroordeel, beleid en gebruikersacties: Bericht verplaatsen naar map ongewenste e-mail, X-header toevoegen, onderwerp wijzigen, Bericht omleiden, bericht verwijderen, verzenden naar quarantaine, Geen actie ondernomen, BCC-bericht |
| `FinalEmailActionPolicy` | Tekenreeks | Actie beleid dat van kracht werd: Antispam high-confidence, Antispam, Antispam bulk mail, Antispam phishing, Anti-phishing domein imitatie, Anti-phishing gebruiker imitatie, Anti-phishing spoof, Anti-phishing grafiek imitatie, Antimalware, Safe Attachments, Enterprise Transport Rules (ETR) |
| `FinalEmailActionPolicyGuid` | Tekenreeks | Unieke id voor het beleid dat de uiteindelijke e-mailactie heeft bepaald |
| `AttachmentCount` | Int | Aantal bijlagen in de e-mail |
| `UrlCount` | Int | Aantal ingesloten URL's in de e-mail |
| `EmailLanguage` | Tekenreeks | Gedetecteerde taal van de e-mailinhoud |

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief op zoek naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
