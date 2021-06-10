---
title: CloudAppEvents-tabel in het geavanceerde schema voor de jacht
description: Meer informatie over gebeurtenissen uit cloud-apps en -services in de tabel CloudAppEvents van het geavanceerde schema voor het zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 17f424d368c0df2f07cda41917f005e4163e5750
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935867"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender



De `CloudAppEvents` tabel in het geavanceerde schema [bevat](advanced-hunting-overview.md) informatie over activiteiten in verschillende cloud-apps en -services die onder de Microsoft Cloud App Security. Voor een volledige lijst gaat u naar [Apps en services die worden behandeld.](#apps-and-services-covered) Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren. 

>[!IMPORTANT]
>Deze tabel bevat informatie die beschikbaar was in de `AppFileEvents` tabel. Vanaf 7 maart 2021 moeten gebruikers die op zoek zijn naar bestandsgerelateerde activiteiten in cloudservices op en na deze datum, de tabel `CloudAppEvents` gebruiken. <br><br>Zoek naar query's en aangepaste detectieregels die de tabel nog steeds gebruiken en bewerk ze om `AppFileEvents` de tabel te `CloudAppEvents` gebruiken. Meer richtlijnen over het converteren van beïnvloede query's vindt u in [Hunt voor cloud-app-activiteiten](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)met Microsoft 365 Defender advanced hunting .


Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is opgenomen |
| `ActionType` | tekenreeks | Type activiteit dat de gebeurtenis heeft geactiveerd |
| `Application` | tekenreeks | Toepassing die de opgenomen actie heeft uitgevoerd |
| `ApplicationId` | tekenreeks | Unieke id voor de toepassing |
| `AccountObjectId` | tekenreeks | Unieke id voor het account in Azure Active Directory |
| `AccountDisplayName` | tekenreeks | Naam van de accountgebruiker die wordt weergegeven in het adresboek. Meestal een combinatie van een bepaalde of voornaam, een middelste initiatie en een achternaam of achternaam. |
| `IsAdminOperation` | tekenreeks | Geeft aan of de activiteit is uitgevoerd door een beheerder |
| `DeviceType` | tekenreeks | Type apparaat op basis van doel en functionaliteit, zoals 'Netwerkapparaat', 'Workstation', 'Server', 'Mobile', 'Gaming console' of 'Printer' | 
| `OSPlatform` | tekenreeks | Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd. Deze kolom geeft specifieke besturingssystemen aan, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. |
| `IPAddress` | tekenreeks | IP-adres toegewezen aan het eindpunt en gebruikt tijdens gerelateerde netwerkcommunicatie |
| `IsAnonymousProxy` | tekenreeks | Geeft aan of het IP-adres behoort tot een bekende anonieme proxy |
| `CountryCode` | tekenreeks | Code met twee letters waarmee het land wordt aangegeven waar het IP-adres van de client is geloceerd |
| `City` | tekenreeks | Plaats waar het IP-adres van de client geolocatie is |
| `Isp` | tekenreeks | Internetprovider die is gekoppeld aan het IP-adres |
| `UserAgent` | tekenreeks | Gebruikersagentgegevens uit de webbrowser of een andere clienttoepassing |
| `ActivityType` | tekenreeks | Type activiteit dat de gebeurtenis heeft geactiveerd |
| `ActivityObjects` | tekenreeks | Lijst met objecten, zoals bestanden of mappen, die betrokken waren bij de opgenomen activiteit |
| `ObjectName` | tekenreeks | Naam van het object waar de opgenomen actie op is toegepast |
| `ObjectType` | tekenreeks | Type object, zoals een bestand of map, waar de opgenomen actie op is toegepast |
| `ObjectId` | tekenreeks | Unieke id van het object waar de opgenomen actie op is toegepast |
| `ReportId` | tekenreeks | Unieke id voor de gebeurtenis |
| `RawEventData` | tekenreeks | Onbewerkte gebeurtenisgegevens uit de brontoepassing of -service in JSON-indeling |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de entiteit of gebeurtenis |

## <a name="apps-and-services-covered"></a>Apps en services die worden behandeld

- Dropbox
- Dynamics 365
- Exchange Online
- Microsoft Teams
- OneDrive voor Bedrijven
- Power Automate
- Power BI
- SharePoint Online
- Skype voor Bedrijven
- Office 365
- Yammer 

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
