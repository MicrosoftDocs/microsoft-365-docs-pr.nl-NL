---
title: Tabel E-mailgebeurtenissen in het geavanceerde jachtschema
description: Meer informatie over gebeurtenissen die zijn gekoppeld aan Microsoft-e-mails in de tabel E-mailgebeurtenissen van het geavanceerde jachtschema
keywords: geavanceerde jacht, dreigingjacht, cyberdreigingsjacht, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, beschrijving, E-mailEvents, netwerkbericht-id, afzender, ontvanger, bijlage-id, bijlagenaam, malwarevonnis, phishingvonnis, bijlagetelling, linktelling, url-telling
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
ms.openlocfilehash: 3146c428edcf276d0a4d5e7797ed913be48dd2ae
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633529"
---
# <a name="emailevents"></a>EmailEvents

**Geldt voor:**
- Microsoft Threat Protection



De `EmailEvents` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over gebeurtenissen met betrekking tot de verwerking van e-mails op Office 365 ATP. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Voor informatie over andere tabellen in de geavanceerde jacht schema, [zie de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `EmailId` | Tekenreeks | Unieke identificatie van e-mail en geadresseerden |
| `NetworkMessageId` | Tekenreeks | Unieke id voor de e-mail, gegenereerd door Microsoft 365 |
| `InternetMessageId` | Tekenreeks | Id voor openbaar gerichte identificatie voor de e-mail die is ingesteld door het verzendende e-mailsysteem |
| `SenderMailFromAddress` | Tekenreeks | E-mailadres van afzender in de kop-mail van, ook wel de afzender van de envelop of het retourpadadres genoemd |
| `SenderFromAddress` | Tekenreeks | E-mailadres van afzender in de HEADER VAN, dat zichtbaar is voor e-mailontvangers op hun e-mailclients |
| `SenderMailFromDomain` | Tekenreeks | Afzenderdomein in de kop-mail van, ook wel de afzender van de envelop of het retourpadadres genoemd |
| `SenderFromDomain` | Tekenreeks | Afzenderdomein in de HEADER VAN, die zichtbaar is voor e-mailontvangers op hun e-mailclients |
| `SenderIPv4` | Tekenreeks | IPv4-adres van de laatst gedetecteerde e-mailserver die het bericht heeft doorgegeven |
| `SenderIPv6` | Tekenreeks | IPv6-adres van de laatst gedetecteerde e-mailserver die het bericht heeft doorgegeven |
| `RecipientEmailAddress` | Tekenreeks | E-mailadres van de ontvanger of e-mailadres van de ontvanger na uitbreiding van de distributielijst |
| `Subject` | Tekenreeks | Onderwerp van de e-mail |
| `EmailClusterId` | Tekenreeks | Id voor de groep vergelijkbare e-mails geclusterd op basis van heuristische analyse van de inhoud ervan |
| `EmailDirection` | Tekenreeks | Richting van de e-mail ten opzichte van uw netwerk: Inbound, Outbound, Intra-org |
| `DeliveryAction` | Tekenreeks | Leveringsactie van de e-mail: geleverd, gejunked, geblokkeerd of vervangen |
| `DeliveryLocation` | Tekenreeks | Locatie waar de e-mail is bezorgd: Postvak IN,Ofein/map, On-premises/Extern, Ongewenste e-mail, Mislukt, Gedropt, Verwijderde items |
| `PhishFilterVerdict` | Tekenreeks | Oordeel van de e-mail filtering stack over de vraag of de e-mail is phish: Phish of niet Phish |
| `PhishDetectionMethod` | Tekenreeks | Methode die wordt gebruikt om de e-mail te detecteren als een phish: Kwaadaardige URL reputatie, ATP Safe Links URL Detonation, Advanced phish filter, General phish filter, Anti-Spoof: Intra-org, Anti-spoof: external domain, Domain impersonation, User impersonation, Brand impersonation |
| `MalwareFilterVerdict` | Tekenreeks | Oordeel van de e-mail filtering stack over de vraag of de e-mail malware bevat: Malware, Niet malware |
| `MalwareDetectionMethod` | Tekenreeks | Methode die wordt gebruikt om malware in de e-mail te detecteren: Antimalware-engine, bestandsreputatie, ATP-veilige bijlagen |
| `FinalEmailAction` | Tekenreeks | Laatste actie op basis van de e-mail op basis van filtervonnis, beleid en gebruikersacties: Bericht verplaatsen naar map met ongewenste e-mail, X-header toevoegen, Onderwerp wijzigen, Bericht omleiden, Bericht verwijderen, verzenden naar quarantaine, Geen actie ondernomen, BCC-bericht |
| `FinalEmailActionPolicy` | Tekenreeks | Actie beleid dat van kracht werd: Antispam high-confidence, Antispam, Antispam bulk mail, Antispam phishing, Anti-phishing domein imitatie, Anti-phishing gebruiker imitatie, Anti-phishing spoof, Anti-phishing grafiek imitatie, Antimalware, Safe Attachments, Enterprise Transport Rules (ETR) |
| `FinalEmailActionPolicyGuid` | Tekenreeks | Unieke id voor het beleid dat de uiteindelijke e-mailactie bepaalde |
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
