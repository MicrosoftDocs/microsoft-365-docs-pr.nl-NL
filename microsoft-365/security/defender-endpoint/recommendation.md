---
title: Aanbevelingsmethoden en -eigenschappen
description: Hiermee worden de meest recente waarschuwingen opgehaald.
keywords: api's, graph api, ondersteunde api's, get, waarschuwingen, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: bd7aa2af2c7500bbe02108bb8aa5dee452ff2998
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771595"
---
# <a name="recommendation-resource-type"></a>Type aanbevelingsresource

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Methoden
Methode |Retourtype |Beschrijving
:---|:---|:---
[Lijst van alle aanbevelingen](get-all-recommendations.md) | Aanbevelingsverzameling | Hiermee wordt een lijst opgehaald met alle beveiligingsaanbevelingen die van invloed zijn op de organisatie
[Aanbevelingen per id ophalen](get-recommendation-by-id.md) | Aanbeveling | Haalt een beveiligingsaanbeveling op met de id
[Aanbevelingssoftware downloaden](get-recommendation-software.md)| [Software](software.md) | Haalt een beveiligingsaanbeveling op die betrekking heeft op een specifieke software
[Aanbevelingsapparaten krijgen](get-recommendation-machines.md)|MachineRef-verzameling | Hiermee wordt een lijst opgehaald met apparaten die zijn gekoppeld aan de beveiligingsaanbeveling
[Beveiligingsproblemen met aanbevelingen krijgen](get-recommendation-vulnerabilities.md) | [Kwetsbaarheidsverzameling](vulnerability.md) | Hiermee wordt een lijst met beveiligingsproblemen opgehaald die zijn gekoppeld aan de beveiligingsaanbeveling


## <a name="properties"></a>Eigenschappen
Eigenschap |   Type   |   Beschrijving
:---|:---|:---
id | Tekenreeks | Aanbevelings-id
productNaam | Tekenreeks | Gerelateerde softwarenaam  
recommendationName | Tekenreeks | Naam van aanbeveling
Zwakke punten | Lang | Aantal gevonden beveiligingslekken
Leverancier | Tekenreeks | Naam van gerelateerde leverancier
aanbevolenVersie | Tekenreeks | Aanbevolen versie
aanbevelingCategory | Tekenreeks | Aanbevelingscategorie. Mogelijke waarden zijn: 'Accounts', 'Toepassing', 'Netwerk', 'OS', 'SecurityStack'
subCategorie | Tekenreeks | Subcategorie Aanbeveling
ernstScore | Dubbel | Mogelijke gevolgen van de configuratie voor de Microsoft Secure Score voor apparaten van de organisatie (1-10)
publicExploit | Booleaanse waarde | Openbare exploit is beschikbaar 
activeAlert | Booleaanse waarde | Actieve waarschuwing is gekoppeld aan deze aanbeveling
associatedThreats | Tekenreeksverzameling | Bedreigingsanalyserapport is gekoppeld aan deze aanbeveling
hersteltype | Tekenreeks | Hersteltype. Mogelijke waarden zijn: "ConfigurationChange","Update","Upgrade","Uninstall"
Status | Enum | Uitzonderingsstatus van aanbeveling. Mogelijke waarden zijn: 'Actief' en 'Uitzondering'
configScoreImpact | Dubbel | Microsoft Secure Score for Devices impact
exposureImpacte | Dubbel | Impact van blootstellingsscore
totalMachineCount | Lang | Aantal geïnstalleerde apparaten
exposedMachinesCount | Lang | Aantal geïnstalleerde apparaten dat wordt blootgesteld aan beveiligingslekken
nonProductivityImpactedAssets | Lang | Aantal apparaten dat niet wordt beïnvloed  
relatedComponent | Tekenreeks |  Gerelateerde softwarecomponent
