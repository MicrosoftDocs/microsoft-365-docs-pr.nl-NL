---
title: DeviceNetworkInfo-tabel in het geavanceerde schema voor zoeken
description: Meer informatie over netwerkconfiguratiegegevens vindt u in de tabel DeviceNetworkInfo van het geavanceerde schema voor zoeken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machinenetworkinfo, DeviceNetworkInfo, device, machine, mac, ip, adapter, dns, gateway, tunnel
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
ms.openlocfilehash: 9e2657631eb2ba8c784f38f76fad46166a450bf0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931204"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender



De tabel in het geavanceerde schema voor zoeken bevat informatie over de netwerkconfiguratie van computers, waaronder `DeviceNetworkInfo` netwerkadapters, IP- en MAC-adressen en verbonden netwerken [](advanced-hunting-overview.md) of domeinen. Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

Zie het geavanceerde zoekschema voor meer informatie over andere tabellen in het geavanceerde schema [voor zoeken.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is vastgelegd |
| `DeviceId` | tekenreeks | Unieke id voor de computer in de service |
| `DeviceName` | tekenreeks | FQDN (Fully Qualified Domain Name) van de computer |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen Apparaatnaam en Tijdstempel |
| `NetworkAdapterName` | tekenreeks | Naam van de netwerkadapter |
| `MacAddress` | tekenreeks | Mac-adres van de netwerkadapter |
| `NetworkAdapterType` | tekenreeks | Type netwerkadapter. Voor de mogelijke waarden raadpleegt u [deze enumeratie](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) |
| `NetworkAdapterStatus` | tekenreeks | De operationele status van de netwerkadapter. Voor de mogelijke waarden raadpleegt u [deze enumeratie](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2) |
| `TunnelType` | tekenreeks | Tunneling-protocol, als de interface hiervoor wordt gebruikt, bijvoorbeeld 6to4, Teredo, ISATAP, PPTP, SSTP en SSH |
| `ConnectedNetworks` | tekenreeks | Netwerken waar de adapter mee is verbonden. Elke JSON-matrix bevat de netwerknaam, -categorie (openbaar, privé of domein), een beschrijving en een vlag die aangeeft of deze openbaar is verbonden met internet |
| `DnsAddresses` | tekenreeks | DNS-serveradressen in JSON-matrixindeling |
| `IPv4Dhcp` | tekenreeks | IPv4-adres van SERVER |
| `IPv6Dhcp` | tekenreeks | IPv6-adres van SERVER SERVER |
| `DefaultGateways` | tekenreeks | Standaard gatewayadressen in JSON-matrixindeling |
| `IPAddresses` | tekenreeks | JSON-matrix met alle IP-adressen die aan de adapter zijn toegewezen, samen met het desbetreffende subnetnummer en de IP-adresruimte, zoals openbaar, privé of link-lokaal |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
