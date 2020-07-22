---
title: AppFileEvents tabel in het geavanceerde jachtschema
description: Meer informatie over bestandsgerelateerde gebeurtenissen die zijn gekoppeld aan cloud-apps en -services in de tabel AppFileEvents van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, gegevenstype, beschrijving, AppFileEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 663dc2a3de676fa2daeab3d9621254e956d42fc4
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204753"
---
# <a name="appfileevents"></a>AppFileEvents

**Van toepassing op:**
- Microsoft Threat Protection

De `AppFileEvents` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over bestandsgerelateerde activiteiten in cloud-apps en -services die worden gecontroleerd door Microsoft Cloud App Security. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `ActionType` | Tekenreeks | Type activiteit dat de gebeurtenis heeft geactiveerd |
| `Application` | Tekenreeks | Toepassing die de opgenomen actie heeft uitgevoerd |
| `FileName` | Tekenreeks | Naam van het bestand waarop de geregistreerde actie is toegepast |
| `FolderPath` | Tekenreeks | Map met het bestand waarop de opgenomen actie is toegepast |
| `PreviousFileName` | Tekenreeks | Oorspronkelijke naam van het bestand dat naar aanleiding van de actie is hernoemd |
| `PreviousFolderPath` | Tekenreeks | Oorspronkelijke map met het bestand voordat de opgenomen actie werd toegepast |
| `Protocol` | Tekenreeks | Netwerkprotocol gebruikt |
| `AccountName` | Tekenreeks | Gebruikersnaam van het account |
| `AccountDomain` | Tekenreeks | Domein van het account |
| `AccountUpn` | Tekenreeks | Gebruikersnaam (UPN) van het account |
| `AccountObjectId` | Tekenreeks | Unieke id voor het account in Azure AD |
| `AccountDisplayName` | Tekenreeks | Naam van de accountgebruiker die in het adresboek wordt weergegeven. Typisch een combinatie van een bepaalde of voornaam, een middelste initiatie, en een achternaam of achternaam. |
| `DeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat |
| `DeviceType` | Tekenreeks | Type apparaat | 
| `OSPlatform` | Tekenreeks | Platform van het besturingssysteem dat op het apparaat draait. Dit duidt op specifieke besturingssystemen, waaronder variaties binnen dezelfde familie, zoals Windows 10 en Windows 7. |
| `IPAddress` | Tekenreeks | IP-adres toegewezen aan het eindpunt en gebruikt tijdens gerelateerde netwerkcommunicatie |
| `DestinationDeviceName` | Tekenreeks | Naam van het apparaat waarop de servertoepassing wordt uitgevoerd die de geregistreerde actie heeft verwerkt |
| `DestinationIPAddress` | Tekenreeks | IP-adres van het apparaat waarop de servertoepassing wordt uitgevoerd die de geregistreerde actie heeft verwerkt |
| `Location` | Tekenreeks | Plaats, land of andere geografische locatie die aan het evenement is gekoppeld |
| `Isp` | Tekenreeks | Internetserviceprovider (ISP) die is gekoppeld aan het IP-adres van het eindpunt |
| `ReportId` | Lange | Unieke id voor het evenement |
| `AdditionalFields` | Tekenreeks | Aanvullende informatie over de entiteit of gebeurtenis |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
