---
title: DeviceFromIP() functie in geavanceerd zoeken naar Microsoft 365 Defender
description: Informatie over het gebruik van de functie DeviceFromIP() om de apparaten te krijgen aan welke een specifiek IP-adres is toegewezen
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, device, devicefromIP, function, enrichment
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 86373c903252fde4ab71c80a81404428a7366da7
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931300"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


Gebruik de functie in uw geavanceerde zoekquery's om snel een lijst te verkrijgen met apparaten die op een bepaald moment aan een bepaald `DeviceFromIP()` IP-adres [](advanced-hunting-overview.md) zijn toegewezen. 

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

- **x:** de eerste parameter is meestal al een kolom in de query. In dit geval is het de kolom met de naam , het IP-adres waarvoor u een lijst wilt zien met apparaten `IP` die aan het adres zijn toegewezen. Het moet een lokaal IP-adres zijn. Externe IP-adressen worden niet ondersteund.
- **y:** een tweede optionele parameter is de , die de functie opdracht geeft om de meest recente toegewezen apparaten op `Timestamp` een bepaald moment op te halen. Als deze niet is opgegeven, worden met de functie de laatst beschikbare records als retourneert.

## <a name="example"></a>Voorbeeld


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a>Haal de meest recente apparaten op die specifieke IP-adressen hebben gekregen

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
