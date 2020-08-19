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
ms.openlocfilehash: 72d02bafa168e48c2d588771f5289da09e6d6000
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794229"
---
# <a name="assignedipaddresses"></a>AssignedIPAddresses()

**Van toepassing op:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Gebruik de `AssignedIPAddresses()` functie om snel de nieuwste IP-adressen te verkrijgen die zijn toegewezen aan een apparaat of de meest recente IP-adressen vanaf een bepaald moment. Deze functie retourneert een tabel met de volgende kolommen:

| Kolom | Gegevenstype | Beschrijving |
|------------|-------------|-------------|
| Tempels | tijd | Laatste keer dat het apparaat is waargenomen met behulp van het IP-adres |
| Adressen | tekenreeks | IP-adres dat door het apparaat wordt gebruikt |
| IPType | tekenreeks | Geeft aan of het IP-adres een openbaar of privéadres is |
| NetworkAdapterType | int | Type netwerkadapter dat wordt gebruikt door het apparaat waaraan het IP-adres is toegewezen. Voor de mogelijke waarden raadpleegt u [deze inventarisatie](https://docs.microsoft.com/dotnet/api/system.net.networkinformation.networkinterfacetype?view=netframework-4.7.2)  |
| ConnectedNetworks | int | Netwerken waarmee de adapter met het toegewezen IP-adres is verbonden. Elke JSON-matrix bevat de netwerknaam, categorie (openbaar, privé of domein), een beschrijving en een vlag waarmee wordt aangegeven of de verbinding openbaar met internet is verbonden. |


## <a name="syntax"></a>Syntaxis

```kusto
AssignedIPAddresses(x, y)
```

## <a name="arguments"></a>Argumenten

- **x** — `DeviceId` of `DeviceName` waarde die het apparaat identificeert
- **y** `Timestamp` de waarde y, (datetime) die het specifieke tijdstip aangeeft waarop de meest recente IP-adressen moeten worden opgehaald. Als dat niet is opgegeven, retourneert de functie de nieuwste IP-adressen.

## <a name="examples"></a>Voorbeelden

### <a name="get-the-list-of-ip-addresses-used-by-a-device-as-of-24-hours-ago"></a>De lijst met IP-adressen die een apparaat 24 uur geleden gebruikt, wordt weergeven

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