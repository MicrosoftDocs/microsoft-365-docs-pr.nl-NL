---
title: AppFileEvents-tabel in het geavanceerde jacht schema
description: Meer informatie over bestanden die zijn gekoppeld aan Cloud-apps en-services in de tabel AppFileEvents van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, tabel, kolom, gegevenstype, beschrijving, AppFileEvents, Cloud app Security, MCAS
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
ms.openlocfilehash: 4e7ddbc5b5cc330496c01d956c4bcecceb897a9a
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/18/2020
ms.locfileid: "46798036"
---
# <a name="appfileevents"></a>AppFileEvents

**Van toepassing op:**
- Microsoft Threat Protection

De `AppFileEvents` tabel in het [Geavanceerde bejachts](advanced-hunting-overview.md) schema bevat informatie over Bestandsactiviteiten in Cloud-apps en services die worden gecontroleerd in de beveiliging van de Microsoft Cloud-app. Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.

>[!TIP]
> Voor gedetailleerde informatie over de typen gebeurtenissen ( `ActionType` waarden) die door een tabel worden ondersteund, gebruikt u de [ingebouwde schema verwijzing](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) die beschikbaar is in het Beveiligingscentrum.

Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | tijd | De datum en tijd waarop de gebeurtenis is vastgelegd |
| `ActionType` | tekenreeks | Type activiteit waarmee de gebeurtenis wordt geactiveerd. Zie de [verwijzingen naar het portal schema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) voor Details |
| `Application` | tekenreeks | De toepassing die de opgenomen actie heeft uitgevoerd |
| `FileName` | tekenreeks | De naam van het bestand waarop de opgenomen actie is toegepast |
| `FolderPath` | tekenreeks | Map met het bestand waarop de opgenomen actie is toegepast |
| `PreviousFileName` | tekenreeks | De oorspronkelijke naam van het bestand dat de naam van het bestand heeft gewijzigd en waarvan de naam is gewijzigd. |
| `PreviousFolderPath` | tekenreeks | De oorspronkelijke map met het bestand voordat de opgenomen actie is toegepast |
| `Protocol` | tekenreeks | Gebruikte netwerkprotocollen |
| `AccountName` | tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | tekenreeks | Domein van het account |
| `AccountUpn` | tekenreeks | UPN (User Principal Name) van het account |
| `AccountObjectId` | tekenreeks | Unieke id voor het account in azure AD |
| `AccountDisplayName` | tekenreeks | Naam van de account gebruiker die in het adresboek wordt weergegeven. Meestal een combinatie van een bepaalde of voornaam, een tweede opening en een achternaam of achternaam. |
| `DeviceName` | tekenreeks | FQDN (Fully Qualified Domain Name) van het apparaat |
| `DeviceType` | tekenreeks | Type apparaat | 
| `OSPlatform` | tekenreeks | Platform van het besturingssysteem dat op het apparaat wordt uitgevoerd. Dit geeft specifieke besturingssystemen aan, met inbegrip van variaties in dezelfde familie, zoals Windows 10 en Windows 7. |
| `IPAddress` | tekenreeks | Het IP-adres dat is toegewezen aan het eindpunt en die wordt gebruikt tijdens gerelateerde netwerkcommunicatie |
| `DestinationDeviceName` | tekenreeks | Naam van het apparaat waarop de servertoepassing wordt uitgevoerd die de opgenomen actie heeft verwerkt |
| `DestinationIPAddress` | tekenreeks | IP-adres van het apparaat waarop de servertoepassing wordt uitgevoerd die de opgenomen actie heeft verwerkt |
| `Location` | tekenreeks | Plaats, land of andere geografische locatie die is gekoppeld aan de gebeurtenis |
| `Isp` | tekenreeks | Internetprovider (ISP) die is gekoppeld aan het IP-adres van het eindpunt |
| `ReportId` | lang | Unieke id voor de gebeurtenis |
| `AdditionalFields` | tekenreeks | Aanvullende informatie over de entiteit of gebeurtenis |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
