---
title: DeviceNetworkInfo-tabel in het geavanceerde jachtschema
description: Meer informatie over netwerkconfiguratie-informatie in de tabel DeviceNetworkInfo van het geavanceerde jachtschema
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, schema referentie, kusto, tabel, kolom, datatype, beschrijving, machinenetworkinfo, DeviceNetworkInfo, apparaat, machine, mac, ip, adapter, dns, dhcp, gateway, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel, tunnel
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
ms.openlocfilehash: 0fd6000f4d3a4b9fafb0eede74cbbe4e6c3d494e
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899241"
---
# <a name="devicenetworkinfo"></a>DeviceNetworkInfo

**Van toepassing op:**
- Microsoft Threat Protection



De `DeviceNetworkInfo` tabel in het geavanceerde [jachtschema](advanced-hunting-overview.md) bevat informatie over netwerkconfiguratie van machines, waaronder netwerkadapters, IP- en MAC-adressen en verbonden netwerken of domeinen. Gebruik deze verwijzing om query's te construeren die informatie uit deze tabel retourneren.

Zie [de geavanceerde jachtreferentie](advanced-hunting-schema-tables.md)voor informatie over andere tabellen in het geavanceerde jachtschema.

| Kolomnaam | Gegevenstype | Beschrijving |
|-------------|-----------|-------------|
| `Timestamp` | Datetime | Datum en tijdstip waarop de gebeurtenis is geregistreerd |
| `DeviceId` | Tekenreeks | Unieke id voor de machine in de service |
| `DeviceName` | Tekenreeks | Volledig gekwalificeerde domeinnaam (FQDN) van de machine |
| `ReportId` | Lange | Gebeurtenis-id op basis van een herhalende teller. Om unieke gebeurtenissen te identificeren, moet deze kolom worden gebruikt in combinatie met de kolommen DeviceName en Timestamp |
| `NetworkAdapterName` | Tekenreeks | Naam van de netwerkadapter |
| `MacAddress` | Tekenreeks | MAC-adres van de netwerkadapter |
| `NetworkAdapterType` | Tekenreeks | Type netwerkadapter. Voor de mogelijke waarden, verwijzen naar [deze opsoming](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2) |
| `NetworkAdapterStatus` | Tekenreeks | Operationele status van de netwerkadapter. Voor de mogelijke waarden, verwijzen naar [deze opsoming](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.operationalstatus?view=netframework-4.7.2) |
| `TunnelType` | Tekenreeks | Tunnelingprotocol, als de interface hiervoor wordt gebruikt, bijvoorbeeld 6to4, Teredo, ISATAP, PPTP, SSTP en SSH |
| `ConnectedNetworks` | Tekenreeks | Netwerken waarmee de adapter is verbonden. Elke JSON-array bevat de netwerknaam, categorie (openbaar, privé of domein), een beschrijving en een vlag die aangeeft of deze openbaar is verbonden met internet |
| `DnsAddresses` | Tekenreeks | DNS-serveradressen in JSON-arrayindeling |
| `IPv4Dhcp` | Tekenreeks | IPv4-adres van DHCP-server |
| `IPv6Dhcp` | Tekenreeks | IPv6-adres van DHCP-server |
| `DefaultGateways` | Tekenreeks | Standaardgatewayadressen in JSON-arrayindeling |
| `IPAddresses` | Tekenreeks | JSON-array met alle IP-adressen die aan de adapter zijn toegewezen, samen met hun respectieve subnetvoorvoegsel en IP-adresruimte, zoals openbaar, privé of linklokal |

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Gedeelde query's gebruiken](advanced-hunting-shared-queries.md)
- [Zoek naar bedreigingen op verschillende apparaten en e-mails](advanced-hunting-query-emails-devices.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
