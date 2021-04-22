---
title: AssignedIPAddresses() functie in advanced hunting for Microsoft 365 Defender
description: Meer informatie over het gebruik van de functie AssignedIPAddresses() om de meest recente IP-adressen aan een apparaat te krijgen
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, FileProfile, file profile, function, enrichment
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
ms.openlocfilehash: d3ebd301d6c79bf5286d9293e04e4073b99d1e35
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934907"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Gebruik de `AssignedIPAddresses()` functie in uw geavanceerde [zoekquery's](advanced-hunting-overview.md) om snel de meest recente IP-adressen te verkrijgen die aan een apparaat zijn toegewezen. Als u een tijdstempelargument opgeeft, verkrijgt deze functie de meest recente IP-adressen op de opgegeven tijd. 

Deze functie retourneert een tabel met de volgende kolommen:

| Kolom | Gegevenstype | Beschrijving |
|------------|-------------|-------------|
| `Timestamp` | datetime | De laatste keer dat het apparaat werd waargenomen met behulp van het IP-adres |
| `IPAddress` | tekenreeks | IP-adres dat door het apparaat wordt gebruikt |
| `IPType` | tekenreeks | Geeft aan of het IP-adres een openbaar of privéadres is |
| `NetworkAdapterType` | int | Netwerkadaptertype dat wordt gebruikt door het apparaat dat aan het IP-adres is toegewezen. Voor de mogelijke waarden raadpleegt u [deze enumeratie](/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `ConnectedNetworks` | int | Netwerken waar de adapter met het toegewezen IP-adres op is aangesloten. Elke JSON-matrix bevat de netwerknaam, categorie (openbaar, privé of domein), een beschrijving en een vlag die aangeeft of deze openbaar is verbonden met internet |

## <a name="syntax"></a>Syntaxis

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Argumenten

- **x** of `DeviceId` waarde die het apparaat `DeviceName` identificeert
- **y-**(datetime) waarde die de functie instrueert om de meest recente toegewezen IP-adressen te verkrijgen `Timestamp` vanaf een bepaalde tijd. Als dit niet is opgegeven, retourneert de functie de meest recente IP-adressen.

## <a name="examples"></a>Voorbeelden

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>De lijst met IP-adressen die 24 uur geleden door een apparaat zijn gebruikt

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>IP-adressen krijgen die door een apparaat worden gebruikt en apparaten zoeken waarmee wordt gecommuniceerd
Deze query gebruikt de functie om toegewezen IP-adressen voor het apparaat () op of vóór een bepaalde datum `AssignedIPAddresses()` `example-device-name` () te `example-date` krijgen. Vervolgens worden de IP-adressen gebruikt om verbindingen te zoeken met het apparaat dat door andere apparaten is gestart. 

```kusto
let Date = datetime(example-date);
let DeviceName = "example-device-name";
// List IP addresses used on or before the specified date
AssignedIPAddresses(DeviceName, Date)
| project DeviceName, IPAddress, AssignedTime = Timestamp 
// Get all network events on devices with the assigned IP addresses as the destination addresses
| join kind=inner DeviceNetworkEvents on $left.IPAddress == $right.RemoteIP
// Get only network events around the time the IP address was assigned
| where Timestamp between ((AssignedTime - 1h) .. (AssignedTime + 1h))
```

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)