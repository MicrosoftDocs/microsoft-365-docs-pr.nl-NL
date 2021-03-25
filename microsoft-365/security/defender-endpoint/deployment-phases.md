---
title: Implementatiefasen
description: Meer informatie over het implementeren van Microsoft Defender voor eindpunten door eindpunten voor die service voor te bereiden, in te stellen en te onboarden
keywords: implementeren, voorbereiden, instellen, onboard, fase, implementatie, implementeren, acceptatie, configureren
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
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3f0527192a55d67df7e23507bed46df446f8b2b7
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165163"
---
# <a name="deployment-phases"></a>Implementatiefasen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Lees hoe u Microsoft Defender voor Eindpunt implementeert, zodat uw bedrijf kan profiteren van preventieve beveiliging, detectie na inbreuken, geautomatiseerd onderzoek en antwoord. 


Deze handleiding helpt u met alle belanghebbenden samen te werken om uw omgeving voor te bereiden en apparaten vervolgens op een methodische manier aan te boord te nemen, van evaluatie naar een zinvolle pilot, naar volledige implementatie.

Elke sectie komt overeen met een afzonderlijk artikel in deze oplossing.

![Afbeelding van implementatiefasen met details uit tabel](images/deployment-guide-phases.png)


![Overzicht van implementatiefasen: voorbereiden, instellen, onboard](images/phase-diagrams/deployment-phases.png)

|Fase | Beschrijving | 
|:-------|:-----|
| [Fase 1: Voorbereiden](prepare-deployment.md)| Meer informatie over waar u rekening mee moet houden bij het implementeren van Defender voor eindpunten, zoals goedkeuringen van belanghebbenden, milieuoverwegingen, toegangsmachtigingen en acceptatieorder van mogelijkheden. 
| [Fase 2: Setup](production-deployment.md)|  Krijg richtlijnen voor de eerste stappen die u moet uitvoeren, zodat u toegang hebt tot de portal, zoals het valideren van licenties, het voltooien van de installatiewizard en de netwerkconfiguratie. 
| [Fase 3: Onboard](onboarding.md) | Meer informatie over het gebruik van implementatieringen, ondersteunde onboarding-hulpprogramma's op basis van het type eindpunt en het configureren van beschikbare mogelijkheden. 


Nadat u deze handleiding hebt voltooid, wordt u ingesteld met de juiste toegangsmachtigingen, worden uw eindpunten onboarded en worden sensorgegevens aan de service gemeld, en zijn er mogelijkheden zoals bescherming van de volgende generatie en de beperking van het aanvalsoppervlak aanwezig.



Ongeacht de omgevingsarchitectuur en de implementatiemethode die [](deployment-strategy.md) u in de implementatiehulplijnen voor plannen hebt beschreven, wordt u in deze handleiding ondersteund bij het onboarden van eindpunten. 








## <a name="key-capabilities"></a>Belangrijke mogelijkheden

Hoewel Microsoft Defender voor Endpoint veel mogelijkheden biedt, is het primaire doel van deze implementatiehandleiding om u op weg te helpen met onboarding-apparaten. Naast onboarding kunt u met deze richtlijnen aan de slag met de volgende mogelijkheden.



Mogelijkheid | Beschrijving 
:---|:---
Eindpuntdetectie en -antwoord | De mogelijkheden voor eindpuntdetectie en -reactie worden gebruikt om inbraakpogingen en actieve inbreuken op te sporen, te onderzoeken en te reageren.
Beveiliging van de volgende generatie | Om de beveiligingsperimeter van uw netwerk verder te versterken, gebruikt Microsoft Defender voor Eindpunt de volgende generatie beveiliging die is ontworpen om alle soorten nieuwe bedreigingen op te vangen.
Surface-beperking voor aanvallen |  Geef de eerste verdedigingslinie in de stapel op. Door ervoor te zorgen dat configuratie-instellingen correct zijn ingesteld en technieken voor risicobeperking worden toegepast, zijn deze mogelijkheden bestand tegen aanvallen en misbruik.

Al deze mogelijkheden zijn beschikbaar voor licentiehouders van Microsoft Defender voor eindpunten. Zie Licentievereisten voor [meer informatie.](minimum-requirements.md#licensing-requirements)

## <a name="scope"></a>Bereik

### <a name="in-scope"></a>In bereik

-   Gebruik van Microsoft Endpoint Manager en Microsoft Endpoint Manager om eindpunten aan te nemen in de service en mogelijkheden te configureren

-   EDR-mogelijkheden (Defender for Endpoint Endpoint Detection and Response) inschakelen

-   De mogelijkheden van Defender voor Endpoint Endpoint Protection Platform (EPP) inschakelen

    -   Beveiliging van de volgende generatie

    -   Surface-beperking voor aanvallen


### <a name="out-of-scope"></a>Buiten bereik

De volgende opties vallen buiten het bereik van deze implementatiehandleiding:

-   Configuratie van oplossingen van derden die kunnen worden geïntegreerd met Defender voor Eindpunt

-   Penetratietests in de productieomgeving




## <a name="see-also"></a>Zie ook
- [Fase 1: Voorbereiden](prepare-deployment.md)
- [Fase 2: Instellen](production-deployment.md)
- [Fase 3: Onboard](onboarding.md)
- [Implementatie plannen](deployment-strategy.md)