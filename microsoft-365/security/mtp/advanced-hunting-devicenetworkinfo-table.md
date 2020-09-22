---
title: DeviceNetworkInfo-tabel in het geavanceerde jacht schema
description: Meer informatie over Netwerkconfiguratiegegevens in de tabel DeviceNetworkInfo van het schema geavanceerde jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, tabel, kolom, gegevenstype, beschrijving, machinenetworkinfo, DeviceNetworkInfo, apparaat, computer, Mac, IP, adapter, computer, Mac, IP, adapter, DNS, DHCP, gateway, tunnel
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
ms.openlocfilehash: b874ef77dcf6efacd7adeff18553c0c8e6752bda
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197071"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection



De `DeviceNetworkInfo` tabel in het [geavanceerde jacht](advanced-hunting-overview.md) -schema bevat informatie over de netwerkconfiguratie van machines, waaronder netwerkadapters, IP-adressen en MAC-adressen, en verbonden netwerken of domeinen. Gebruik deze verwijzing voor het maken van query's waarmee informatie uit deze tabel wordt geretourneerd.

Zie voor meer informatie over andere tabellen in het geavanceerde jacht-schema [de Naslaggids voor Geavanceerd](advanced-hunting-schema-tables.md)zoeken.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | tijd | De datum en tijd waarop de gebeurtenis is vastgelegd |
| `DeviceId` | tekenreeks | Unieke id voor de computer in de service |
| `DeviceName` | tekenreeks | FQDN-naam (Fully Qualified Domain Name) van de computer |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de naam van het apparaat en de timestamp-kolommen. |
| `NetworkAdapterName` | tekenreeks | Naam van de netwerkadapter |
| `MacAddress` | tekenreeks | MAC-adres van de netwerkadapter |
| `NetworkAdapterType` | tekenreeks | Type netwerkadapter. Voor de mogelijke waarden raadpleegt u [deze inventarisatie](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) |
| `NetworkAdapterStatus` | tekenreeks | De operationele status van de netwerkadapter. Voor de mogelijke waarden raadpleegt u [deze inventarisatie](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2) |
| `TunnelType` | tekenreeks | Protocol voor tunneling, als de interface voor dit doel wordt gebruikt, bijvoorbeeld 6to4, Teredo, ISATAP, PPTP, SSTP en SSH |
| `ConnectedNetworks` | tekenreeks | Netwerken waarmee de adapter is verbonden. Elke JSON-matrix bevat de netwerknaam, categorie (openbaar, privé of domein), een beschrijving en een vlag waarmee wordt aangegeven of de verbinding openbaar met internet is verbonden. |
| `DnsAddresses` | tekenreeks | DNS-serveradressen in JSON-matrix indeling |
| `IPv4Dhcp` | tekenreeks | IPv4-adres van DHCP-server |
| `IPv6Dhcp` | tekenreeks | IPv6-adres van DHCP-server |
| `DefaultGateways` | tekenreeks | Standaardgatewayadressen in de JSON-matrix indeling |
| `IPAddresses` | tekenreeks | JSON-matrix met alle IP-adressen die zijn toegewezen aan de adapter, samen met hun bijbehorende subnet prefix en IP-adresruimte, zoals openbaar, privé, of link-local |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Opsporen op apparaten en in e-mailberichten, apps en identiteiten](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
