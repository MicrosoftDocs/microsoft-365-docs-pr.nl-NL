---
title: DeviceFromIP() functie in advanced hunting for Microsoft 365 Defender
description: Meer informatie over het gebruik van de functie DeviceFromIP() om de apparaten te krijgen die aan een specifiek IP-adres zijn toegewezen
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, device, devicefromIP, function, enrichment
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
ms.openlocfilehash: 3ea951e35555721a989001b2a5235df5b89a8a55
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933179"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


Gebruik de `DeviceFromIP()` functie in uw geavanceerde [query's](advanced-hunting-overview.md) om snel de lijst met apparaten te verkrijgen die op een bepaald moment aan een bepaald IP-adres zijn toegewezen. 

Deze functie retourneert een tabel met de volgende kolommen:

| Kolom | Gegevenstype | Beschrijving |
|------------|-------------|-------------|
| `IP` | tekenreeks | IP-adres  |
| `DeviceId` | tekenreeks | Unieke id voor het apparaat in de service |


## <a name="syntax"></a>Syntaxis

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a>Argumenten

Deze functie wordt aangeroepen als onderdeel van een query.

- **x:** de eerste parameter is meestal al een kolom in de query. In dit geval is het de kolom met de naam , het IP-adres waarvoor u een lijst met apparaten wilt zien die aan de kolom `IP` zijn toegewezen. Het moet een lokaal IP-adres zijn. Externe IP-adressen worden niet ondersteund.
- **y**: een tweede optionele parameter is de , die de functie instrueert om de meest recente toegewezen apparaten te verkrijgen `Timestamp` vanaf een bepaalde tijd. Als dit niet is opgegeven, retourneert de functie de meest recente beschikbare records.

## <a name="example"></a>Voorbeeld


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a>De nieuwste apparaten krijgen die aan specifieke IP-adressen zijn toegewezen

```kusto
DeviceNetworkEvents 
| limit 100 
| project IP = LocalIP 
| invoke DeviceFromIP()
```

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
