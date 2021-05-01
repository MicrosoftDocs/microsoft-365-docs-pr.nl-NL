---
title: Uw beveiligingshouding voorbereiden op het eerste incident
description: Stel de beveiligingsstatus Microsoft 365 van uw tenant in voor uw eerste incident in Microsoft 365 Defender.
keywords: incidenten, waarschuwingen, onderzoeken, correlatie, aanval, machines, apparaten, gebruikers, identiteiten, identiteit, postvak, e-mail, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 88001dc7126a55539213d4c560127d573a09f4bd
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114651"
---
# <a name="prepare-your-security-posture-for-your-first-incident"></a>Uw beveiligingshouding voorbereiden op het eerste incident

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

Als u zich voorbereidt op incidentafhandeling, moet het netwerk van een organisatie voldoende worden beschermd tegen verschillende soorten beveiligingsincidenten. Om het risico op beveiligingsincidenten te beperken, raadt het National Institute of Standards and Technology (NIST) verschillende beveiligingspraktijken aan, waaronder risicobeoordelingen, het verbeteren van de beveiliging van de host, het veilig configureren van netwerken en het voorkomen van malware. 

Microsoft 365 Defender kan helpen bij het aanpakken van verschillende aspecten van incidentpreventie: 

- Een [Zero Trust-framework](https://docs.microsoft.com/security/zero-trust/) implementeren
- Uw beveiligingsstatus bepalen door een score toe te wijzen met [Microsoft Secure Score](microsoft-secure-score.md)
- Bedreigingen voorkomen via kwetsbaarheidsbeoordelingen in [Bedreigings- en kwetsbaarheidsbeheer](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)
- Inzicht in de meest recente beveiligingsrisico's, zodat u zich op deze bedreigingen kunt voorbereiden

## <a name="step-1-implement-zero-trust"></a>Stap 1. Nul vertrouwen implementeren

[Zero Trust](https://docs.microsoft.com/security/zero-trust/) is een geïntegreerde beveiligingsbeschouwing en end-to-endstrategie waarin rekening wordt gehouden met de complexe aard van elke moderne omgeving, met inbegrip van het mobiele personeel en de gebruikers, apparaten, toepassingen en gegevens, waar ze zich ook bevinden. Door één deelvenster met glas te bieden om alle eindpuntdetecties op een consistente manier te beheren, kan [](https://docs.microsoft.com/security/zero-trust/#guiding-principles-of-zero-trust) Microsoft 365 Defender het uw beveiligingsteam gemakkelijker maken om de basisprincipes van Zero Trust te implementeren. 

Onderdelen van Microsoft 365 Defender kunnen schendingen van regels weergeven die zijn geïmplementeerd om beleid voor voorwaardelijke toegang voor Zero Trust tot stand te brengen door gegevens van Microsoft Defender voor Eindpunt (MDE) of andere mobiele beveiligingsleveranciers te integreren als informatiebron voor beleidsregels voor apparaat compliance en implementatie van beleidsregels voor voorwaardelijke toegang op apparaten. 

Apparaatrisico is rechtstreeks van invloed op de bronnen die toegankelijk zijn voor de gebruiker van dat apparaat. De weigering van toegang tot resources op basis van bepaalde criteria is het hoofdthema van Zero Trust en Microsoft 365 Defender biedt informatie die nodig is om de criteria op vertrouwensniveau te bepalen. Zo kan Microsoft 365 Defender het softwareversieniveau van een apparaat bieden via de pagina Bedreigings- en beveiligingsprobleembeheer, terwijl beleidsregels voor voorwaardelijke toegang apparaten beperken die verouderde of kwetsbare versies hebben.

Automatisering is een essentieel onderdeel van het implementeren en onderhouden van een Zero Trust-omgeving, terwijl ook het aantal waarschuwingen wordt beperkt dat mogelijk tot incidenten kan leiden. Onderdelen van Microsoft 365 Defender kunnen worden geautomatiseerd, zoals herstelacties (ook wel onderzoeken voor een incident in het Microsoft 365-beveiligingscentrum genoemd), meldingsacties en zelfs het maken van ondersteuningstickets, zoals in [ServiceNow.](https://microsoft.service-now.com/sp/)

## <a name="step-2-determine-your-organizations-security-posture"></a>Stap 2. De beveiligingsstatus van uw organisatie bepalen

Vervolgens kunnen organisaties de [Microsoft Secure Score](microsoft-secure-score.md) in Microsoft 365 Defender gebruiken om uw huidige beveiligingsstatus te bepalen en aanbevelingen te overwegen voor het verbeteren van deze score. Hoe hoger de score is, hoe meer beveiligingsaanbevelingen en verbeteracties door de organisatie zijn genomen. Aanbevelingen voor veilige score kunnen worden gebruikt voor verschillende producten en organisaties in staat stellen hun scores nog hoger te maken. 

:::image type="content" source="../../media/first-incident-prepare/first-incident-secure-score.png" alt-text="Voorbeeld van Microsoft Secure Score in het Microsoft-beveiligingscentrum":::
 
## <a name="step-3-assess-your-organizations-vulnerability-exposure"></a>Stap 3. De kwetsbaarheidsblootstelling van uw organisatie beoordelen

Het voorkomen van incidenten kan helpen bij het stroomlijnen van de beveiligingsactiviteiten om zich te richten op aan de hand van kritieke en belangrijke beveiligingsincidenten. Softwareproblemen zijn vaak een preventief toegangspunt voor aanvallen die kunnen leiden tot gegevensdiefstal, gegevensverlies of verstoring van bedrijfsactiviteiten. Als er geen aanvallen worden uitgevoerd, moeten beveiligingsbewerkingen ernaar streven om een acceptabel niveau van blootstelling aan kwetsbaarheid [in](../defender-endpoint/tvm-exposure-score.md) hun organisatie te bereiken en te behouden.

Als u de voortgang van [](../defender-endpoint/next-gen-threat-and-vuln-mgt.md) de softwarepatching wilt controleren, gaat u naar de pagina Bedreigings- en kwetsbaarheidsbeheer in Defender voor Eindpunt, die u kunt openen vanuit Microsoft 365 Defender via het tabblad **Meer** bronnen.

:::image type="content" source="../../media/first-incident-prepare/first-incident-vulnerability.png" alt-text="Voorbeeld van de pagina Bedreiging en kwetsbaarheid in het Microsoft-beveiligingscentrum"::: 
 
## <a name="4-understand-emerging-threats"></a>4. Nieuwe bedreigingen begrijpen

Gebruik [bedreigingsanalyse](threat-analytics.md) in het Microsoft 365 beveiligingscentrum om up-to-date te blijven met het huidige landschap van beveiligingsrisico's. Deskundige beveiligingsonderzoekers van Microsoft maken rapporten waarin de meest recente cyberdreigingen gedetailleerd worden beschreven, zodat u kunt begrijpen hoe deze van invloed kunnen zijn op uw Microsoft 365-abonnement, apparaten en gebruikers. Deze rapporten kunnen bestaan uit:

- Actieve bedreigingsacteurs en hun campagnes
- Populaire en nieuwe aanvalstechnieken
- Kritieke beveiligingslekken
- Veelvoorkomende aanvalsoppervlakken
- Voorkomende malware

U kunt de aanbevelingen van een nieuwe bedreiging implementeren om uw beveiligingshouding te versterken en het oppervlak van de aanval te minimaliseren.

Maak tijd in uw planning om regelmatig de sectie [Bedreigingsanalyse](threat-analytics.md) van het Microsoft 365 te controleren.

## <a name="next-step"></a>Volgende stap

[![Stap 1: Informatie over het triagen en analyseren van incidenten](../../media/first-incident-overview/first-incident-path-step1.png)](first-incident-analyze.md)

Meer informatie over het [triagen en analyseren van incidenten.](first-incident-analyze.md)

## <a name="see-also"></a>Zie ook

- [Overzicht van incidenten](incidents-overview.md)
- [Incidenten analyseren](investigate-incidents.md)
- [Incidenten beheren](manage-incidents.md)
