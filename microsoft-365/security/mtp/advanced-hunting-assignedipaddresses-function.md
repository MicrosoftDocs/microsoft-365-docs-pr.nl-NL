---
title: AssignedIPAddresses() functie in geavanceerd zoeken naar Microsoft 365 Defender
description: Informatie over het gebruik van de functieAssignedIPAddresses() om de meest recente IP-adressen aan een apparaat toe te werken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, FileProfile, file profile, function, enrichment
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
ms.openlocfilehash: d16cd7efc49cc2498eff3f705bb43fa62f37d975
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933016"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Gebruik de `AssignedIPAddresses()` functie in uw geavanceerde [zoekquery's](advanced-hunting-overview.md) om snel de meest recente IP-adressen te verkrijgen die aan een apparaat zijn toegewezen. Als u een tijdstempelargument opgeeft, worden met deze functie de meest recente IP-adressen op de opgegeven tijd bepaald. 

Deze functie retourneert een tabel met de volgende kolommen:

| Kolom | Gegevenstype | Beschrijving |
|------------|-------------|-------------|
| `Timestamp` | datetime | De laatste keer dat het apparaat werd waargenomen met behulp van het IP-adres |
| `IPAddress` | tekenreeks | IP-adres dat door het apparaat is gebruikt |
| `IPType` | tekenreeks | Geeft aan of het IP-adres een openbaar of persoonlijk adres is |
| `NetworkAdapterType` | int | Het type netwerkadapter dat wordt gebruikt door het apparaat dat aan het IP-adres is toegewezen. Voor de mogelijke waarden raadpleegt u [deze enumeratie](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `ConnectedNetworks` | int | Netwerken waar de adapter met het toegewezen IP-adres mee is verbonden. Elke JSON-matrix bevat de netwerknaam, -categorie (openbaar, privé of domein), een beschrijving en een vlag die aangeeft of deze openbaar is verbonden met internet |

## <a name="syntax"></a>Syntaxis

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Argumenten

- **x** of `DeviceId` een waarde die het apparaat `DeviceName` identificeert
- **y**— (datetime) met de instructie van de functie om de meest recent toegewezen IP-adressen van `Timestamp` een bepaalde tijd te verkrijgen. Als deze niet is opgegeven, retourneert de functie de meest recente IP-adressen.

## <a name="examples"></a>Voorbeelden

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>De lijst met IP-adressen vinden die 24 uur geleden door een apparaat zijn gebruikt

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>IP-adressen krijgen die door een apparaat worden gebruikt en zoek naar apparaten die met het apparaat communiceren
Deze query gebruikt de functie om ip-adressen voor het apparaat () op of vóór een bepaalde datum `AssignedIPAddresses()` `example-device-name` () te `example-date` krijgen. Vervolgens worden de IP-adressen gebruikt om verbindingen te zoeken met het apparaat dat door andere apparaten is gestart. 

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
