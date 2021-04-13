---
title: Nieuwe bedreigingen bijhouden en beantwoorden met Microsoft Defender voor endpoint threat analytics
ms.reviewer: ''
description: Meer informatie over nieuwe bedreigingen en aanvalstechnieken en hoe u deze kunt stoppen. Beoordeel de impact ervan op uw organisatie en evalueer uw organisatiebestendigheid.
keywords: bedreigingsanalyse, risicoanalyse, mitigatie van besturingssysteem, microcodebeperking, mitigatiestatus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 61b6b0c19730045468c77e5f24bf18470aa5dbd5
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688259"
---
# <a name="track-and-respond-to-emerging-threats-with-threat-analytics"></a>Nieuwe bedreigingen bijhouden en beantwoorden met bedreigingsanalyse 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Met geavanceerdere tegenstanders en nieuwe bedreigingen die regelmatig en regelmatig verschijnen, is het essentieel om snel te kunnen:

- De impact van nieuwe bedreigingen beoordelen
- Uw tolerantie voor of blootstelling aan de bedreigingen controleren
- De acties identificeren die u kunt uitvoeren om de bedreigingen te stoppen of te bevatten

Bedreigingsanalyse is een reeks rapporten van deskundige Microsoft-beveiligingsonderzoekers over de meest relevante bedreigingen, waaronder:

- Actieve bedreigingsacteurs en hun campagnes
- Populaire en nieuwe aanvalstechnieken
- Kritieke beveiligingslekken
- Veelvoorkomende aanvalsoppervlakken
- Voorkomende malware

Elk rapport bevat een gedetailleerde analyse van een bedreiging en uitgebreide richtlijnen voor het beschermen tegen die bedreiging. Het bevat ook gegevens uit uw netwerk, waarmee wordt aangegeven of de bedreiging actief is en of u over toepasselijke beveiliging beschikt.

Bekijk deze korte video voor meer informatie over hoe u met bedreigingsanalyse de meest recente bedreigingen kunt bijhouden en stoppen.
<p></p>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bw1f]

## <a name="view-the-threat-analytics-dashboard"></a>Het dashboard bedreigingsanalyse bekijken

Het dashboard bedreigingsanalyse is een goed uitgangspunt om naar de rapporten te gaan die het meest relevant zijn voor uw organisatie. De bedreigingen worden in de volgende secties samengevat:

- **Meest recente bedreigingen:** bevat de meest recent gepubliceerde bedreigingsrapporten, samen met het aantal apparaten met actieve en opgeloste waarschuwingen.
- **Bedreigingen met een hoge** impact : hier worden de bedreigingen vermeld die de grootste impact hebben gehad op de organisatie. In deze sectie worden bedreigingen gerangeerd op het aantal apparaten met actieve waarschuwingen.
- **Overzicht van** bedreigingen: toont de algehele impact van bijgespoorde bedreigingen door het aantal bedreigingen met actieve en opgeloste waarschuwingen weer te geven.

Selecteer een bedreiging in het dashboard om het rapport voor die bedreiging weer te geven.

![Afbeelding van een dashboard voor bedreigingsanalyse](images/ta_dashboard.png)

## <a name="view-a-threat-analytics-report"></a>Een bedreigingsanalyserapport weergeven

Elk rapport voor bedreigingsanalyse bevat informatie in drie secties: **Overzicht,** **Analistrapport** en **Mitigaties.**

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a>Overzicht: Snel inzicht krijgen in de bedreiging, de impact ervan beoordelen en verdedigingslinie bekijken

De **sectie** Overzicht bevat een voorbeeld van het gedetailleerde analistenrapport. Het bevat ook grafieken die de impact van de bedreiging voor uw organisatie en uw blootstelling markeren via verkeerd geconfigureerde en ongepatchte apparaten.

![Afbeelding van de overzichtssectie van een rapport Voor bedreigingsanalyse ](images/ta-overview.png)
 _Overzicht sectie van een bedreigingsanalyserapport_

#### <a name="assess-the-impact-to-your-organization"></a>De impact voor uw organisatie beoordelen
Elk rapport bevat grafieken die zijn ontworpen om informatie te verstrekken over de invloed van een bedreiging op de organisatie:
- **Apparaten met waarschuwingen**: toont het huidige aantal verschillende apparaten dat door de bedreiging is beïnvloed. Een apparaat wordt gecategoriseerd als Actief als er  ten  minste één waarschuwing is gekoppeld aan die bedreiging en Opgelost als alle waarschuwingen die zijn gekoppeld aan de bedreiging op het apparaat zijn opgelost. 
- **Apparaten met waarschuwingen in de tijd**: toont het aantal verschillende apparaten met **actieve** en **opgeloste** waarschuwingen in de tijd. Het aantal opgeloste waarschuwingen geeft aan hoe snel uw organisatie reageert op waarschuwingen die zijn gekoppeld aan een bedreiging. In het ideale kader moet de grafiek binnen enkele dagen waarschuwingen weergeven die zijn opgelost.

#### <a name="review-security-resilience-and-posture"></a>Beveiligingsweerbaarheid en -houding controleren
Elk rapport bevat grafieken die een overzicht geven van hoe veerkrachtig uw organisatie is tegen een bepaalde bedreiging:
- **Beveiligingsconfiguratiestatus:** toont het aantal apparaten dat de aanbevolen beveiligingsinstellingen heeft toegepast om de bedreiging te beperken. Apparaten worden beschouwd **als Veilig** als ze alle _bijgespoorde_ instellingen hebben toegepast.
- **Status van beveiligingspatches:** toont het aantal apparaten dat beveiligingsupdates of patches heeft toegepast waarmee beveiligingsproblemen worden aangepakt die door de bedreiging worden misbruikt.

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a>Analistrapport: Krijg inzicht van microsoft-beveiligingsonderzoekers
Ga naar de **sectie Analistrapport** om de gedetailleerde expert write-up te lezen. De meeste rapporten bevatten gedetailleerde beschrijvingen van aanvalsketens, waaronder tactieken en technieken die zijn toegesneden op het MITRE ATT&CK-framework, uitgebreide lijsten met aanbevelingen en krachtige richtlijnen voor het zoeken naar [bedreigingen.](advanced-hunting-overview.md)

[Meer informatie over het analistenrapport](threat-analytics-analyst-reports.md)

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a>Risicobeperking: Lijst met risico's en de status van uw apparaten controleren
Bekijk in **de sectie Mitigaties** de lijst met specifieke actie-aanbevelingen die u kunnen helpen uw organisatieweerbaarheid tegen de bedreiging te vergroten. De lijst met bijgespoorde risico's bevat:

- **Beveiligingsupdates**: implementatie van beveiligingsupdates of patches voor beveiligingsproblemen
- **Microsoft Defender Antivirus-instellingen**
  - Versie van beveiligingsinformatie
  - Beveiliging in de cloud  
  - Potentieel ongewenste toepassingsbeveiliging (PUA)
  - Realtime beveiliging
 
Mitigatiegegevens in deze [](next-gen-threat-and-vuln-mgt.md)sectie bevatten gegevens van bedreigings- en kwetsbaarheidsbeheer, die ook gedetailleerde inzoomgegevens bevatten van verschillende koppelingen in het rapport.

![Afbeelding van de sectie risicobeperking van een sectie ](images/ta-mitigations.png)
 _Risicoanalyse-sectie Mitigatie van een bedreigingsanalyserapport_

## <a name="additional-report-details-and-limitations"></a>Aanvullende rapportdetails en -beperkingen
Houd bij het gebruik van de rapporten rekening met het volgende: 

- Gegevens hebben een bereik op basis van uw RBAC-bereik (Role-Based Access Control). U ziet de status van apparaten in [groepen die u kunt openen.](machine-groups.md)
- Grafieken geven alleen risico's weer die worden bijgespoord. Controleer het rapportoverzicht op aanvullende risico's die niet in de grafieken worden weergegeven.
- Risicobeperking garandeert geen volledige tolerantie. De geleverde risico's weerspiegelen de best mogelijke acties die nodig zijn om de tolerantie te verbeteren.
- Apparaten worden geteld als 'niet beschikbaar' als ze geen gegevens naar de service hebben verzonden.
- Antivirusgerelateerde statistieken zijn gebaseerd op de antivirusinstellingen van Microsoft Defender. Apparaten met antivirusoplossingen van derden kunnen worden weergegeven als 'blootgesteld'.

## <a name="related-topics"></a>Verwante onderwerpen
- [Proactief bedreigingen zoeken met geavanceerde jacht](advanced-hunting-overview.md) 
- [De sectie Analistrapport begrijpen](threat-analytics-analyst-reports.md)
- [Beveiligingszwakheden en blootstellingen beoordelen en oplossen](next-gen-threat-and-vuln-mgt.md)