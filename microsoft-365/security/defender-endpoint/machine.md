---
title: Type machineresource
description: Meer informatie over de methoden en eigenschappen van het type machineresource in Microsoft Defender voor Eindpunt.
keywords: api's, ondersteunde api's, get, machines
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 7b95fc487a8ee3e82e0f215b34aa564e063534af
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772075"
---
# <a name="machine-resource-type"></a>Type machineresource

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Methoden

Methode|Retourtype |Beschrijving
:---|:---|:---
[Lijst van computers](get-machines.md) | [machineverzameling](machine.md) | Lijstset [met machine-entiteiten](machine.md) in de organisatie.
[Machine kopen](get-machine-by-id.md) | [computer](machine.md) | Een [computer op](machine.md) de identiteit van de computer krijgen.
[Aangemelde gebruikers krijgen](get-machine-log-on-users.md) | [gebruikersverzameling](user.md) | De set gebruikers [die](user.md) zich bij de computer hebben [aangemeld.](machine.md)
[Gerelateerde waarschuwingen ontvangen](get-machine-related-alerts.md) | [waarschuwingsverzameling](alerts.md) | Haal de set [waarschuwingsentiteiten](alerts.md) op die zijn verhoogd op de [computer.](machine.md)
[Geïnstalleerde software ophalen](get-installed-software.md) | [softwareverzameling](software.md) | Hiermee wordt een verzameling geïnstalleerde software opgehaald die betrekking heeft op een bepaalde computer-id.
[Gevonden beveiligingsproblemen ophalen](get-discovered-vulnerabilities.md) | [kwetsbaarheidsverzameling](vulnerability.md) | Hiermee wordt een verzameling gevonden beveiligingslekken met betrekking tot een bepaalde computer-id opgehaald.
[Beveiligingsaanbevelingen ophalen](get-security-recommendations.md) | [aanbevelingsverzameling](recommendation.md) | Hiermee wordt een verzameling beveiligingsaanbevelingen opgehaald die betrekking hebben op een bepaalde computer-id.
[Computerlabels toevoegen of verwijderen](add-or-remove-machine-tags.md) | [computer](machine.md) | Tag toevoegen of verwijderen aan een bepaalde computer.
[Computers zoeken op IP](find-machines-by-ip.md) | [machineverzameling](machine.md) | Zoek machines die worden gezien met IP.
[Computers zoeken op tag](find-machines-by-tag.md) | [machineverzameling](machine.md) | Machines zoeken op [tag](machine-tags.md).
[Ontbrekende KB's ophalen](get-missing-kbs-machine.md) | KB-verzameling | Een lijst met ontbrekende KBs krijgen die zijn gekoppeld aan de computer-id
[Apparaatwaarde instellen](set-device-value.md)| [machineverzameling](machine.md) | Stel de [waarde van een apparaat in.](tvm-assign-device-value.md)

## <a name="properties"></a>Eigenschappen

Eigenschap |   Type   |   Beschrijving
:---|:---|:---
id | Tekenreeks | [](machine.md) computeridentiteit.
computerDnsName | Tekenreeks | [computer](machine.md) volledig gekwalificeerde naam.
firstSeen | DateTimeOffset | De eerste datum en tijd waarop [de computer](machine.md) is waargenomen door Microsoft Defender voor Eindpunt.
lastSeen | DateTimeOffset |Tijd en datum van het laatst ontvangen volledige apparaatrapport. Een apparaat verzendt meestal elke 24 uur een volledig rapport.
osPlatform | Tekenreeks | Besturingssysteemplatform.
osProcessor | Tekenreeks | Besturingssysteemprocessor. Gebruik in plaats daarvan de eigenschap osArchitecture.
Versie | Tekenreeks | Versie van besturingssysteem.
osBuild | Nullable long | Buildnummer van besturingssysteem.
lastIpAddress | Tekenreeks | Laatste IP op lokale NIC op de [computer](machine.md).
lastExternalIpAddress | Tekenreeks | Laatste IP waarmee de [computer toegang](machine.md) heeft tot internet.
statusStatus | Enum | [status van](machine.md) de machinestatus. Mogelijke waarden zijn: "Active", "Inactive", "ImpairedCommunication", "NoSensorData", "NoSensorDataImpairedCommunication" en "Unknown". 
rbacGroupName | Tekenreeks | Naam van machinegroep.
riskScore | Nullable Enum | Risicoscore zoals geëvalueerd door Microsoft Defender voor Eindpunt. Mogelijke waarden zijn: 'Geen', 'Informatief', 'Laag', 'Gemiddeld' en 'Hoog'.
exposureScore | Nullable Enum | [Blootstellingsscore](tvm-exposure-score.md) zoals geëvalueerd door Microsoft Defender voor Eindpunt. Mogelijke waarden zijn: 'Geen', 'Laag', 'Gemiddeld' en 'Hoog'.
aadDeviceId | Nullable representation Guid | AAD-apparaat-id (wanneer [de computer](machine.md) is verbonden met AAD).
machineTags | Tekenreeksverzameling | Set [met machinelabels.](machine.md)
exposureLevel | Nullable Enum | Blootstellingsniveau zoals geëvalueerd door Microsoft Defender voor Eindpunt. Mogelijke waarden zijn: 'Geen', 'Laag', 'Gemiddeld' en 'Hoog'.
deviceValue | Nullable Enum | De [waarde van het apparaat](tvm-assign-device-value.md). Mogelijke waarden zijn: 'Normaal', 'Laag' en 'Hoog'.
ipAddresses | IpAddress-verzameling | Set ***IpAddress-objecten.*** Zie [Machines API krijgen.](get-machines.md)
osArchitecture | Tekenreeks | Architectuur van besturingssysteem. Mogelijke waarden zijn: '32-bits', '64-bits'. Gebruik deze eigenschap in plaats van osProcessor.


