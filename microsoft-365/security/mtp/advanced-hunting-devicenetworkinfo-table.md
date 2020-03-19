---
title: DeviceNetworkInfo-tabel in het geavanceerde jachtschema
description: Meer informatie over netwerkconfiguratie-informatie in de tabel DeviceNetworkInfo van het geavanceerde jachtschema
keywords: geavanceerde jacht, dreigingjacht, cyberdreigingsjacht, bescherming tegen microsoft-dreigingen, microsoft 365, mtp, m365, zoekopdracht, query, telemetrie, schemareferentie, kusto, tabel, kolom, gegevenstype, beschrijving, machinenetworkinfo, DeviceNetworkInfo, apparaat, machine, mac, ip, adapter, dns, dhcp, gateway, tunnel
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
ms.openlocfilehash: ce392ee074327114b0794edfeef9eb83091447d6
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42812073"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging



De `DeviceNetworkInfo` tabel in het [geavanceerde jachtschema](advanced-hunting-overview.md) bevat informatie over netwerkconfiguratie van machines, waaronder netwerkadapters, IP- en MAC-adressen en verbonden netwerken of domeinen. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Voor informatie over andere tabellen in de geavanceerde jacht schema, [zie de geavanceerde jacht referentie](advanced-hunting-schema-tables.md).

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `DeviceId` | Tekenreeks | Unieke id voor de machine in de service |
| `DeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de machine |
| `ReportId` | Lange | Gebeurtenis-id op basis van een herhalingsteller. Om unieke gebeurtenissen te identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp |
| `NetworkAdapterName` | Tekenreeks | Naam van de netwerkadapter |
| `MacAddress` | Tekenreeks | MAC-adres van de netwerkadapter |
| `NetworkAdapterType` | Tekenreeks | Type netwerkadapter. Voor de mogelijke waarden, verwijzen wij u naar [deze opsomming](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) |
| `NetworkAdapterStatus` | Tekenreeks | Operationele status van de netwerkadapter. Voor de mogelijke waarden, verwijzen wij u naar [deze opsomming](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2) |
| `TunnelType` | Tekenreeks | Tunnelingprotocol, als de interface voor dit doel wordt gebruikt, bijvoorbeeld 6to4, Teredo, ISATAP, PPTP, SSTP en SSH |
| `ConnectedNetworks` | Tekenreeks | Netwerken waarmee de adapter is verbonden. Elke JSON-array bevat de netwerknaam, categorie (openbaar, privé of domein), een beschrijving en een vlag die aangeeft of deze openbaar is verbonden met internet |
| `DnsAddresses` | Tekenreeks | DNS-serveradressen in JSON-arrayindeling |
| `IPv4Dhcp` | Tekenreeks | IPv4-adres van DHCP-server |
| `IPv6Dhcp` | Tekenreeks | IPv6-adres van DHCP-server |
| `DefaultGateways` | Tekenreeks | Standaardgatewayadressen in JSON-arrayindeling |
| `IPAddresses` | Tekenreeks | JSON-array met alle IP-adressen die aan de adapter zijn toegewezen, samen met hun respectieve subnetvoorvoegsel- en IP-adresruimte, zoals openbare, particuliere of link-lokale |

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief op zoek naar bedreigingen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Het schema begrijpen](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
