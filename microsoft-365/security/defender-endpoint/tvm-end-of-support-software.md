---
title: Software- en softwareversies voor het einde van de ondersteuning plannen
description: Ontdek en plan voor software- en softwareversies die niet meer worden ondersteund en geen beveiligingsupdates ontvangen.
keywords: Threat and Vulnerability Management, Microsoft Defender voor endpoint tvm-beveiligingsaanbeveling, aanbeveling voor cyberbeveiliging, actie-aanbevelingen voor beveiliging
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bb436cbd2d0fa453872760c1d2656585e02d1767
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538865"
---
# <a name="plan-for-end-of-support-software-and-software-versions-with-threat-and-vulnerability-management"></a>Plan voor end-of-support software- en softwareversies met Threat and Vulnerability Management

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedreiging en vulnerability management](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

End-of-support (EOS), ook wel bekend als end-of-life (EOL), voor software- of softwareversies betekent dat ze niet meer worden ondersteund of geserviced en geen beveiligingsupdates ontvangen. Wanneer u software- of softwareversies met beëindigde ondersteuning gebruikt, wordt uw organisatie blootgelegd aan beveiligingsproblemen, juridische en financiële risico's.

Het is essentieel voor beveiligings- en IT-beheerders om samen te werken en ervoor te zorgen dat de softwarevoorraad van de organisatie is geconfigureerd voor optimale resultaten, naleving en een gezond netwerkecosysteem. Ze moeten de opties bekijken om apps te verwijderen of te vervangen die einde-of-ondersteunings- en updateversies hebben bereikt die niet meer worden ondersteund. U kunt het beste een  plan maken en implementeren vóór het einde van de ondersteuningsdatum.

>[!NOTE]
> EOS-functionaliteit is momenteel niet beschikbaar voor niet-Windows producten (Mac, Linux); deze wordt echter in de toekomst toegevoegd.

## <a name="find-software-or-software-versions-that-are-no-longer-supported"></a>Software- of softwareversies zoeken die niet meer worden ondersteund

1. Ga in Threat and Vulnerability Management menu naar [**Beveiligingsaanbevelingen.**](tvm-security-recommendation.md)
2. Ga naar het **deelvenster Filters** en zoek naar de sectie Tags. Selecteer een of meer van de EOS-tagopties. Vervolgens **toepassen.**

    ![Schermafbeeldingen met EOS-software, EOS-versies en toekomstige EOS-versies.](images/tvm-eos-tag.png)

3. U ziet een lijst met aanbevelingen met betrekking tot software met beëindigde ondersteuning, softwareversies die het einde van de ondersteuning zijn of versies met een binnenkort einde van de ondersteuning. Deze tags zijn ook zichtbaar op de [pagina softwarevoorraad.](tvm-software-inventory.md)

    ![Aanbevelingen met EOS-tag.](images/tvm-eos-tags-column.png)

## <a name="list-of-versions-and-dates"></a>Lijst met versies en datums

Als u een lijst wilt weergeven met versies die het einde van de ondersteuning hebben bereikt, of binnenkort eindigen of ondersteunen, en deze datums, volgt u de volgende stappen:

1. Er wordt een bericht weergegeven in de flyout beveiligingsaanbeveling voor software met versies die het einde van de ondersteuning hebben bereikt of binnenkort het einde van de ondersteuning bereiken.

    ![Schermafbeelding van de koppeling versieverdeling.](images/eos-upcoming-eos.png)

2. Selecteer de **koppeling versiedistributie** om naar de inzoompagina van de software te gaan. Daar ziet u een gefilterde lijst met versies met tags die deze identificeren als einde van de ondersteuning of het aanstaande einde van de ondersteuning.

    ![Schermafbeelding van de inzoompagina van de software met het einde van de ondersteuningssoftware.](images/software-drilldown-eos.png)

3. Selecteer een van de versies in de tabel die u wilt openen. Bijvoorbeeld versie 10.0.18362.1. Er wordt een flyout weergegeven met het einde van de ondersteuningsdatum.

    ![Schermafbeelding van het einde van de ondersteuningsdatum.](images/version-eos-date.png)

Nadat u hebt bepaald welke software- en softwareversies kwetsbaar zijn vanwege de status van het einde van de ondersteuning, moet u beslissen of u deze wilt bijwerken of verwijderen uit uw organisatie. Hierdoor worden uw organisaties minder blootgesteld aan beveiligingslekken en geavanceerde permanente bedreigingen.

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van bedreigingen en vulnerability management](next-gen-threat-and-vuln-mgt.md)
- [Beveiligingsaanbevelingen](tvm-security-recommendation.md)
- [Software-inventaris](tvm-software-inventory.md)
