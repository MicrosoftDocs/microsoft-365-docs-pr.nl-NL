---
title: Tabel DeviceNetworkInfo in het geavanceerde schema voor de jacht
description: Meer informatie over netwerkconfiguratiegegevens in de tabel DeviceNetworkInfo van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, machinenetworkinfo, DeviceNetworkInfo, device, machine, mac, ip, adapter, dns, dhcp, gateway, tunnel
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
ms.openlocfilehash: e6bfb781b3454025c5ce0f43899180c91761a56d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932557"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender



De tabel in het geavanceerde schema bevat informatie over netwerkconfiguratie van machines, zoals netwerkadapters, IP- en MAC-adressen en verbonden netwerken `DeviceNetworkInfo` of domeinen. [](advanced-hunting-overview.md) Gebruik deze verwijzing om query's te maken die gegevens uit deze tabel retourneren.

Zie de geavanceerde zoekverwijzing voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-tables.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is opgenomen |
| `DeviceId` | tekenreeks | Unieke id voor de machine in de service |
| `DeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de computer |
| `NetworkAdapterName` | tekenreeks | Naam van de netwerkadapter |
| `MacAddress` | tekenreeks | MAC-adres van de netwerkadapter |
| `NetworkAdapterType` | tekenreeks | Type netwerkadapter. Voor de mogelijke waarden raadpleegt u [deze enumeratie](/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) |
| `NetworkAdapterStatus` | tekenreeks | Operationele status van de netwerkadapter. Voor de mogelijke waarden raadpleegt u [deze enumeratie](/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2) |
| `TunnelType` | tekenreeks | Tunneling protocol, als de interface hiervoor wordt gebruikt, bijvoorbeeld 6to4, Teredo, ISATAP, PPTP, SSTP en SSH |
| `ConnectedNetworks` | tekenreeks | Netwerken waar de adapter mee is verbonden. Elke JSON-matrix bevat de netwerknaam, categorie (openbaar, privé of domein), een beschrijving en een vlag die aangeeft of deze openbaar is verbonden met internet |
| `DnsAddresses` | tekenreeks | DNS-serveradressen in JSON-matrixindeling |
| `IPv4Dhcp` | tekenreeks | IPv4-adres van DHCP-server |
| `IPv6Dhcp` | tekenreeks | IPv6-adres van DHCP-server |
| `DefaultGateways` | tekenreeks | Standaardgatewayadressen in JSON-matrixindeling |
| `IPAddresses` | tekenreeks | JSON-matrix met alle IP-adressen die aan de adapter zijn toegewezen, samen met hun respectievelijke subnet-voorvoegsel en IP-adresruimte, zoals openbaar, privé of link-local |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)