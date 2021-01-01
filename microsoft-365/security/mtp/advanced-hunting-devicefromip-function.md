---
title: DeviceFromIP (), functie in geavanceerde jacht voor Microsoft 365 Defender
description: Meer informatie over het gebruik van de functie DeviceFromIP () om de apparaten te krijgen aan wie een specifiek IP-adres is toegewezen
keywords: geavanceerde jacht, Threat jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, Telemetry, schema naslag, kusto, devicefromIP,, functie, verrijking
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 65409dd93f3703f1af115178c4cd9fa470fb7497
ms.sourcegitcommit: 25ac2736a66bb72c0d574c3fbde7472ac98d5321
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/31/2020
ms.locfileid: "49741106"
---
# <a name="devicefromip"></a>DeviceFromIP()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender


[!INCLUDE [Prerelease information](../includes/prerelease.md)]


Gebruik de `DeviceFromIP()` functie in uw [geavanceerde jacht](advanced-hunting-overview.md) -query's om snel de lijst te verkrijgen met apparaten die op een bepaald moment aan een bepaald IP-adres zijn toegewezen. 

Deze functie retourneert een tabel met de volgende kolommen:

| Kolom | Gegevenstype | Beschrijving |
|------------|-------------|-------------|
| `IP` | tekenreeks | IP-adres  |
| `DeviceId` | tekenreeks | Unieke id van het apparaat in de service |


## <a name="syntax"></a>Syntaxis

```kusto
invoke DeviceFromIP()
```

## <a name="arguments"></a>Argumenten

Deze functie wordt geactiveerd als onderdeel van een query.

- **x**— de eerste parameter is meestal al een kolom in de query. Dit is de kolom genaamd `IP` , het IP-adres waarvan u een lijst wilt weergeven met apparaten die aan de lijst zijn toegewezen. Dit moet een lokaal IP-adres zijn. Externe IP-adressen worden niet ondersteund.
- **y**: een tweede optionele parameter is de `Timestamp` functie, die de functie vraagt om de nieuwste, toegewezen apparaten uit een bepaalde tijd te verkrijgen. Als dit niet wordt opgegeven, geeft de functie de laatste beschikbare records als resultaat.

## <a name="example"></a>Voorbeeld


### <a name="get-the-latest-devices-that-have-been-assigned-specific-ip-addresses"></a>Schaf de nieuwste apparaten aan waaraan specifiek IP-adressen zijn toegewezen.

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
