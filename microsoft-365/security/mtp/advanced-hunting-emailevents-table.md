---
title: EmailEvents-tabel in het geavanceerde jacht schema
description: Meer informatie over gebeurtenissen die zijn gekoppeld aan Microsoft 365-e-mails in de tabel EmailEvents van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat-jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema Reference, kusto, tabel, Column, datatype, een beschrijving, EmailEvents, de naam van de bijlage, de afzender, de naam van de e-mail, het aantal koppelingen, het aantal url's
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
ms.openlocfilehash: 63f95b281dd2284168817a8edd9777c470f01d34
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797920"
---
# <a name="emailevents"></a>EmailEvents

**Van toepassing op:**
- Microsoft Threat Protection



De `EmailEvents` tabel in het [geavanceerde jacht](advanced-hunting-overview.md) -schema bevat informatie over gebeurtenissen die betrekking hebben op het verwerken van e-mailberichten in Office 365 ATP. Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.

>[!TIP]
> Voor gedetailleerde informatie over de typen gebeurtenissen ( `ActionType` waarden) die door een tabel worden ondersteund, gebruikt u de [ingebouwde schema verwijzing](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) die beschikbaar is in het Beveiligingscentrum.

Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | tijd | De datum en tijd waarop de gebeurtenis is vastgelegd |
| `EmailId` | tekenreeks | Unieke e-mail en geadresseerden-id |
| `NetworkMessageId` | tekenreeks | Unieke id voor de e-mail, gegenereerd door Microsoft 365 |
| `InternetMessageId` | tekenreeks | Openbare id voor het e-mailbericht dat wordt ingesteld door het verzendende e-mailsysteem |
| `SenderMailFromAddress` | tekenreeks | E-mailadres van afzender in de header E-mail van, ook wel bekend als de afzender voor de envelop of het adres van de afzender. |
| `SenderFromAddress` | tekenreeks | Het e-mailadres van de afzender in de header van, die zichtbaar is voor e-mail geadresseerden op de e-mailclients |
| `SenderMailFromDomain` | tekenreeks | Het domein van de afzender in de header E-mail van, ook wel bekend als de afzender voor de envelop of het adres van de afzender. |
| `SenderFromDomain` | tekenreeks | Het domein van de afzender in de van-header, die zichtbaar is voor e-mail geadresseerden op de e-mailclients |
| `SenderIPv4` | tekenreeks | IPv4-adres van de laatst gedetecteerde e-mailserver die het bericht heeft doorgestuurd |
| `SenderIPv6` | tekenreeks | IPv6-adres van de laatst gedetecteerde e-mailserver die het bericht heeft doorgestuurd |
| `RecipientEmailAddress` | tekenreeks | Het e-mailadres van de geadresseerde of het e-mailadres van de geadresseerde na expansie van distributielijst |
| `Subject` | tekenreeks | Onderwerp van de e-mail |
| `EmailClusterId` | tekenreeks | Id van de groep verwante e-mailberichten gegroepeerd op basis van een heuristische analyse van de inhoud |
| `EmailDirection` | tekenreeks | Richting van de e-mail ten opzichte van uw netwerk: binnenkomende, uitgaande, intra organisatie |
| `DeliveryAction` | tekenreeks | Bezorgings actie van de e-mail: bezorgd, ongewenst, geblokkeerd of vervangen |
| `DeliveryLocation` | tekenreeks | De locatie waar het e-mailbericht is bezorgd: Postvak in/map, on-premises/extern, ongewenste E-mail, Quarantine, mislukt, neergezette, verwijderde items |
| `PhishFilterVerdict` | tekenreeks | Verdict van de filters stapel voor het filteren van e-mail of het e-mailbericht is gephishd: phishing of niet phishing |
| `PhishDetectionMethod` | tekenreeks | Methode die wordt gebruikt om het e-mailbericht als een phishing op te sporen: schadelijke URL-reputatie, vrije-vorm-URL-detonatie, algemeen phishing-filter, algemeen phishing-filter, anti-bedrog: intra organisatie, anti-spoof: extern domein, domein imitatie, gebruikers imitatie, merk persoon |
| `MalwareFilterVerdict` | tekenreeks | Verdict van de filters stapel voor e-mail om te bepalen of het e-mailbericht malware bevat: malware, geen malware |
| `MalwareDetectionMethod` | tekenreeks | Methode voor het detecteren van malware in de e-mail: antimalware-engine, reputatie van bestanden, veilige bijlagen van ATP |
| `FinalEmailAction` | tekenreeks | Laatste actie van de e-mail op basis van filter Verdict, beleidsregels en gebruikersacties: bericht verplaatsen naar map Ongewenste e-mail, X-header toevoegen, onderwerp wijzigen, bericht omleiden, geen actie ondernomen, berichten verzenden naar Quarantine |
| `FinalEmailActionPolicy` | tekenreeks | Actiebeleid dat heeft geduurd: spam hoge betrouwbaarheid, spam, spam bulkmail, spam phishing, anti phishing Domain disuserion, anti phishing, anti phishing Graph, anti phishing Graph, anti malafide Graph, anti malafide Graph, anti malafide Graph (ETR toe) |
| `FinalEmailActionPolicyGuid` | tekenreeks | Unieke id voor het beleid dat de definitieve actie heeft bepaald |
| `AttachmentCount` | int | Aantal bijlagen in het e-mailbericht |
| `UrlCount` | int | Aantal ingesloten Url's in het e-mailbericht |
| `EmailLanguage` | tekenreeks | Gedetecteerde taal van de e-mail inhoud |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
