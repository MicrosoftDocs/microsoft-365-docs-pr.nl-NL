---
title: Tabel DeviceNetworkInfo in het geavanceerde schema voor de jacht
description: Meer informatie over netwerkconfiguratiegegevens in de tabel DeviceNetworkInfo van het geavanceerde schema voor de jacht
keywords: advanced hunting, threat hunting, cyber threat hunting, search, query, telemetry, schema reference, kusto, table, column, data type, description, devicenetworkinfo, device, device, mac, ip, adapter, dns, dhcp, gateway, tunnel, DeviceNetworkInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4ba3e81163cdbba54bf718dca929e2df3b39a1c3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059789"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

De tabel in het geavanceerde schema bevat informatie over netwerkconfiguratie van apparaten, zoals netwerkadapters, IP- en MAC-adressen en verbonden netwerken `DeviceNetworkInfo` of domeinen. [](advanced-hunting-overview.md) Gebruik deze verwijzing om query's te maken die gegevens uit de tabel retourneren.

Zie de geavanceerde verwijzing naar het schema voor de jacht voor meer informatie over andere tabellen in het geavanceerde schema voor [de jacht.](advanced-hunting-schema-reference.md)

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | datetime | Datum en tijd waarop de gebeurtenis is opgenomen |
| `DeviceId` | tekenreeks | Unieke id voor het apparaat in de service |
| `DeviceName` | tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van het apparaat |
| `ReportId` | lang | Gebeurtenis-id op basis van een herhalende teller. Als u unieke gebeurtenissen wilt identificeren, moet deze kolom worden gebruikt in combinatie met de `DeviceName` kolommen en `Timestamp` de kolommen |
| `NetworkAdapterName` | tekenreeks | Naam van de netwerkadapter |
| `MacAddress` | tekenreeks | MAC-adres van de netwerkadapter |
| `NetworkAdapterType` | tekenreeks | Type netwerkadapter. Voor de mogelijke waarden raadpleegt u [deze enumeratie](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2&preserve-view=true) |
| `NetworkAdapterStatus` | tekenreeks | Operationele status van de netwerkadapter. Voor de mogelijke waarden raadpleegt u [deze enumeratie](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2&preserve-view=true) |
| `TunnelType` | tekenreeks | Tunneling protocol, als de interface hiervoor wordt gebruikt, bijvoorbeeld 6to4, Teredo, ISATAP, PPTP, SSTP en SSH |
| `ConnectedNetworks` | tekenreeks | Netwerken waar de adapter mee is verbonden. Elke JSON-matrix bevat de netwerknaam, categorie (openbaar, privé of domein), een beschrijving en een vlag die aangeeft of deze openbaar is verbonden met internet |
| `DnsAddresses` | tekenreeks | DNS-serveradressen in JSON-matrixindeling |
| `IPv4Dhcp` | tekenreeks | IPv4-adres van DHCP-server |
| `IPv6Dhcp` | tekenreeks | IPv6-adres van DHCP-server |
| `DefaultGateways` | tekenreeks | Standaardgatewayadressen in JSON-matrixindeling |
| `IPAddresses` | tekenreeks | JSON-matrix met alle IP-adressen die aan de adapter zijn toegewezen, samen met hun respectievelijke subnet-voorvoegsel en IP-adresruimte, zoals openbaar, privé of link-local |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Meer informatie over het schema](advanced-hunting-schema-reference.md)
