---
title: CloudAppEvents-tabel in het geavanceerde jacht schema
description: Meer informatie over gebeurtenissen van Cloud-apps en-services in de tabel CloudAppEvents van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, tabel, kolom, gegevenstype, beschrijving, CloudAppEvents, Cloud app Security, MCAS
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 3cb4498e5db6a7752e99b8c677bc8936d2c975ef
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087764"
---
# <a name="cloudappevents"></a>CloudAppEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Op dit moment is er een voorvertoning, de `CloudAppEvents` tabel in het [geavanceerde jacht](advanced-hunting-overview.md) schema bevat informatie over activiteiten in diverse Cloud-apps en-services, met name Microsoft teams en Exchange Online. Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.

Deze tabel wordt uitgebreid met meer activiteiten gecontroleerd op de beveiliging van de Microsoft Cloud-app. Deze tabel bevat uiteindelijk ook Bestandsactiviteit die is opgeslagen in de tabel [AppFileEvents](advanced-hunting-appfileevents-table.md) . Microsoft biedt extra richtlijnen, zodat meer gegevens naar deze tabel worden verplaatst.

Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | tijd | De datum en tijd waarop de gebeurtenis is vastgelegd |
| `ActionType` | tekenreeks | Type activiteit waarmee de gebeurtenis wordt geactiveerd |
| `Application` | tekenreeks | De toepassing die de opgenomen actie heeft uitgevoerd |
| `ApplicationId` | tekenreeks | Unieke id voor de toepassing |
| `AccountObjectId` | tekenreeks | Unieke id voor het account in azure Active Directory |
| `AccountDisplayName` | tekenreeks | Naam van de account gebruiker die in het adresboek wordt weergegeven. Meestal een combinatie van een bepaalde of voornaam, een tweede opening en een achternaam of achternaam. |
| `IsAdminOperation` | tekenreeks | Geeft aan of de activiteit is uitgevoerd door een beheerder |
| `DeviceType` | tekenreeks | Type apparaat op basis van doel en functionaliteit, zoals ' netwerkapparaat ', ' werkstation ', ' server ', ' Mobiel ', ' gaming console ' of ' printer ' | 
| `OSPlatform` | tekenreeks | Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd. In deze kolom worden specifieke besturingssystemen aangegeven, waaronder variaties in dezelfde familie, zoals Windows 10 en Windows 7. |
| `IPAddress` | tekenreeks | Het IP-adres dat is toegewezen aan het eindpunt en die wordt gebruikt tijdens gerelateerde netwerkcommunicatie |
| `IsAnonymousProxy` | tekenreeks | Geeft aan of het IP-adres bij een bekende anonieme proxy behoort |
| `CountryCode` | tekenreeks | Tweeletterige code die het land aangeeft waarin het IP-adres van de client geolocatie is |
| `City` | tekenreeks | Plaats waar het IP-adres van de client geolocatie is |
| `Isp` | tekenreeks | Internetprovider (ISP) die is gekoppeld aan het IP-adres |
| `UserAgent` | tekenreeks | Gegevens van de gebruikersagent van de webbrowser of een andere clienttoepassing |
| `ActivityType` | tekenreeks | Type activiteit waarmee de gebeurtenis wordt geactiveerd |
| `ActivityObjects` | tekenreeks | Lijst met objecten, zoals bestanden of mappen, die zijn betrokken bij de opgenomen activiteit |
| `ObjectName` | tekenreeks | Naam van het object waarop de opgenomen actie is toegepast |
| `ObjectType` | tekenreeks | Type object, zoals een bestand of een map, waarop de opgenomen actie is toegepast |
| `ObjectId` | tekenreeks | Unieke id van het object waarop de opgenomen actie is toegepast |
| `ReportId` | tekenreeks | Unieke id voor de gebeurtenis |
| `RawEventData` | tekenreeks | Gegevens van onbewerkte gebeurtenissen uit de brontoepassing of service in de JSON-indeling |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de entiteit of gebeurtenis |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
