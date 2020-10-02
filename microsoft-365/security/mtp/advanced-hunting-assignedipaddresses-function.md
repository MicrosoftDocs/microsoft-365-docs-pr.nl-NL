---
title: AssignedIPAddresses (), functie in geavanceerde jacht voor Microsoft Threat Protection
description: Meer informatie over het gebruik van de functie AssignedIPAddresses () om de meest recente IP-adressen aan een apparaat te krijgen
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, FileProfile, bestands profiel, functie, verrijking
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
ms.openlocfilehash: ea6b65e5e6d676c5efb2622193197bae5b9ba1b2
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338543"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection

Gebruik de `AssignedIPAddresses()` functie in uw [geavanceerde jacht](advanced-hunting-overview.md) -query's om snel de nieuwste IP-adressen te verkrijgen die aan een apparaat zijn toegewezen. Als u een argument voor een tijdstempel opgeeft, worden voor deze functie de meest recente IP-adressen op de opgegeven tijd opgehaald. 

Deze functie retourneert een tabel met de volgende kolommen:

| Kolom | Gegevenstype | Beschrijving |
|------------|-------------|-------------|
| `Timestamp` | tijd | Laatste keer dat het apparaat is waargenomen met behulp van het IP-adres |
| `IPAddress` | tekenreeks | IP-adres dat door het apparaat wordt gebruikt |
| `IPType` | tekenreeks | Geeft aan of het IP-adres een openbaar of privéadres is |
| `NetworkAdapterType` | int | Type netwerkadapter dat wordt gebruikt door het apparaat waaraan het IP-adres is toegewezen. Voor de mogelijke waarden raadpleegt u [deze inventarisatie](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype) |
| `ConnectedNetworks` | int | Netwerken waarmee de adapter met het toegewezen IP-adres is verbonden. Elke JSON-matrix bevat de naam van een netwerk, categorie (openbaar, privé of domein), een beschrijving en een vlag die aangeven of de verbinding openbaar met internet is. |

## <a name="syntax"></a>Syntaxis

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Argumenten

- **x**— `DeviceId` of `DeviceName` waarde die het apparaat identificeert
- **y** `Timestamp` de waarde y (datetime) die de functie vraagt om de meest recente IP-adressen van een specifieke tijd te verkrijgen. Als dat niet is opgegeven, retourneert de functie de nieuwste IP-adressen.

## <a name="examples"></a>Voorbeelden

### <a name="get-the-list-of-ip-addresses-used-by-a-device-24-hours-ago"></a>De lijst met IP-adressen die worden gebruikt door een apparaat, 24 uur geleden weergeven

```kusto
AssignedIPAddresses('example-device-name', ago(1d))
```

### <a name="get-ip-addresses-used-by-a-device-and-find-devices-communicating-with-it"></a>IP-adressen van een apparaat achterhalen en apparaten communiceren
Deze query maakt gebruik `AssignedIPAddresses()` van de functie om toegewezen IP-adressen voor het apparaat ( `example-device-name` ) op of vóór een bepaalde datum () te krijgen `example-date` . Vervolgens gebruikt u de IP-adressen om verbindingen te vinden met het apparaat dat door andere apparaten wordt gestart. 

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
