---
title: Rapport Kwetsbare apparaten - bedreigings- en kwetsbaarheidsbeheer
description: Een rapport met zwakke apparaattrends en huidige statistieken. Het doel is dat u de adem en het bereik van de blootstelling van uw apparaat begrijpt.
keywords: Microsoft Defender for Endpoint-tvm vulnerable devices, Microsoft Defender for Endpoint, tvm, reduce threat & vulnerability exposure, reduce threat and vulnerability, monitor security configuration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4b2b581d570bd0924970a845c66a599495ff9829
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933707"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a>Rapport Kwetsbare apparaten - bedreigings- en kwetsbaarheidsbeheer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedreigings- en kwetsbaarheidsbeheer](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Het rapport bevat grafieken en staafdiagrammen met kwetsbare apparaattrends en huidige statistieken. Het doel is dat u de adem en het bereik van de blootstelling van uw apparaat begrijpt. 

Toegang tot het rapport in het Microsoft Defender-beveiligingscentrum door naar **Rapporten > Kwetsbare apparaten**

Er zijn twee kolommen:

- Trends (in de tijd). Kan de afgelopen 30 dagen, 3 maanden, 6 maanden of een aangepast datumbereik laten zien.
- Vandaag (huidige informatie)

**Filter:** U kunt de gegevens filteren op ernst van de kwetsbaarheid, misbruik maken van beschikbaarheid, leeftijd van kwetsbaarheid, besturingssysteemplatform, Windows 10-versie of apparaatgroep.

**Inzoomen:** Als er een inzicht is dat u verder wilt verkennen, selecteert u het relevante staafdiagram om een gefilterde lijst met apparaten weer te geven op de pagina Apparaatvoorraad. Van hieruit kunt u de lijst exporteren.

## <a name="severity-level-graphs"></a>Ernstniveaugrafieken

Elk apparaat wordt slechts eenmaal geteld op basis van het ernstigste beveiligingsprobleem dat op dat apparaat is gevonden.

![Eén grafiek met de ernst van de kwetsbaarheid van het huidige apparaat en één grafiek met niveaus in de tijd.](images/tvm-report-severity.png)

## <a name="exploit-availability-graphs"></a>Beschikbaarheidsgrafieken benutten

Elk apparaat wordt slechts eenmaal geteld op basis van het hoogste niveau van bekende exploit.

![Eén grafiek met de beschikbaarheid van het huidige apparaat en één grafiek met beschikbaarheid in de tijd.](images/tvm-report-exploit-availability.png)

## <a name="vulnerability-age-graphs"></a>Leeftijdsgrafieken van kwetsbaarheid

Elk apparaat wordt slechts eenmaal geteld onder de oudste publicatiedatum van het beveiligingsprobleem. Oudere beveiligingslekken hebben een grotere kans op misbruik.

![Eén grafiek van de huidige leeftijd van de kwetsbaarheid van het apparaat en één grafiek met de leeftijd in de tijd.](images/tvm-report-age.png)

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a>Kwetsbare apparaten per besturingssysteemplatformgrafieken

Het aantal apparaten op elk besturingssysteem dat wordt blootgesteld als gevolg van softwareproblemen.

![Eén grafiek van huidige, kwetsbare apparaten per besturingssysteemplatform en één grafiek met kwetsbare apparaten van besturingssysteemplatforms in de tijd.](images/tvm-report-os.png)

## <a name="vulnerable-devices-by-windows-10-version-graphs"></a>Kwetsbare apparaten door Windows 10-versiegrafieken

Het aantal apparaten op elke Windows 10-versie dat wordt blootgesteld aan kwetsbare toepassingen of besturingssysteem.

![Eén grafiek met huidige, kwetsbare apparaten per Windows 10-versie en één grafiek met kwetsbare apparaten van windows 10-versie in de tijd.](images/tvm-report-version.png)

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van bedreigings- en kwetsbaarheidsbeheer](next-gen-threat-and-vuln-mgt.md)
- [Beveiligingsaanbevelingen](tvm-security-recommendation.md)
