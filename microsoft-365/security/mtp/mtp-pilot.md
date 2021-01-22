---
title: Uw testfase microsoft 365 Defender-project uitvoeren
description: Voer uw testfase microsoft 365 Defender-project uit in productie om zo effectief de voordelen en acceptatie van Microsoft 365 Defender te bepalen.
keywords: Microsoft Threat Protection-pilot, voer pilot Microsoft Threat Protection-project uit, evalueer Microsoft Threat Protection in productie, Microsoft Threat Protection-pilotproject, cyberbeveiliging, geavanceerde permanente bedreiging, bedrijfsbeveiliging, apparaten, apparaat, identiteit, gebruikers, gegevens, toepassingen, incidenten, geautomatiseerd onderzoek en herstel, geavanceerd zoeken
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 9c0635058539e464a76f1720f041c205a05fa9b2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933028"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>Uw testfase microsoft 365 Defender-project uitvoeren 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender


Deze handleiding helpt u bij het uitvoeren van een pilotproject door pointers te bieden om ervoor te zorgen dat u over een goed gestructureerd plan kunt beschikken, om u te begeleiden door de functie voor de aanvalsversleuteling te gebruiken en ten slotte de test af te sluiten met belangrijke take-aways om de resultaten te bekijken en vast te stellen.

![Fasen in een Microsoft 365 Defender-testfase](../../media/pilotphases.png)


Het uitvoeren van een testfase helpt u om effectief vast te stellen wat de voordelen zijn van het gebruik van Microsoft 365 Defender. Voordat u Microsoft 365 Defender inschakelen in uw productieomgeving en uw use cases start, kunt u het beste plannen welke taken u moet uitvoeren voor uw pilotproject en de criteria voor succes instellen. 


## <a name="how-to-use-this-pilot-playbook"></a>Dit playbook gebruiken in de testfase

Deze handleiding bevat een overzicht van Microsoft 365 Defender en stapsgewijste instructies voor het instellen van uw pilotproject. 

Microsoft 365 Defender is een geïntegreerde pre- en post-breach Enterprise Defense Suite die ingebouwde beveiliging, detectie, preventie, onderzoek en antwoorden voor eindpunten, identiteiten, e-mail en toepassingen coördineren om geïntegreerde beveiliging tegen geavanceerde aanvallen te bieden. Dit doet u door de volgende mogelijkheden te combineren en te verbeteren in één beveiligingsoplossing:
  - Microsoft Defender voor eindpunt, de nieuwe naam voor Microsoft Defender Advanced Threat Protection (eindpunten)
  - Microsoft Defender voor Office 365, de nieuwe naam voor Office 365 ATP (e-mail) 
  - Microsoft Defender for Identity, de nieuwe naam voor Azure ATP (identity) 
  - Beveiliging van Microsoft Cloud-apps (apps)

![Afbeelding of_Microsoft 365 Defender-oplossing voor gebruikers, Microsoft Defender for Identity, voor eindpunten Microsoft Defender voor eindpunt, voor cloud-apps, Microsoft Cloud App-beveiliging en voor gegevens, Microsoft Defender voor Office 365](../../media/mtp/m365pillars.png)

Met de geïntegreerde Microsoft 365 Defender-oplossing kunnen beveiligingsprofessionals samenwerken aan de bedreigingssignalen die Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365, Microsoft Defender voor identiteit en Microsoft Cloud App Security ontvangen, en bepalen wat het volledige bereik en de invloed van de bedreiging zijn, hoe de bedreiging is ingevoerd in de omgeving, wat de gevolgen zijn en hoe deze op dit moment van invloed is op de organisatie. Microsoft 365 Defender onderneemt automatische acties om de aanval en postvakken, eindpunten en gebruikersidentiteiten te voorkomen of te stoppen. Zie het [overzicht van Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) voor meer informatie.



De volgende voorbeeldtijdlijn varieert afhankelijk van de juiste resources in uw omgeving. Sommige detecties en werkstromen hebben mogelijk meer leertijd nodig dan de andere.

![Voorbeeldtijdlijn in een Microsoft 365 Defender-testfase](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>Voor optimale resultaten volgt u de instructies van de testfase zo goed mogelijk.


### <a name="pilot-playbook-phases"></a>Fases van playbook pilot 

Een Microsoft 365 Defender-testfase bestaat uit vier fasen:

|Fase | Beschrijving | 
|:-------|:-----|
| [Planning](mtp-pilot-plan.md)<br> ~ 1 dag| Lees waar u aan moet denken voordat u een Microsoft 365 Defender-testproject gaat uitvoeren: <br><br>- Bereik <br> - Use cases <br>- Vereisten <br>- Testplan <br> - Criteria voor succes <br> - Scorecard 
| [Voorbereiding](mtp-evaluation.md) <br>~2 dagen|  Krijg toegang tot het Microsoft 365-beveiligingscentrum om uw Microsoft 365 Defender-testomgeving in te stellen. U wordt begeleid bij het volgende:<br><br>- Identificeer belanghebbenden en zoek het aanmelden voor uw testfase <br> - Aandachtspunten voor de omgeving <br>- Access <br>- Azure Active Directory instellen <br> - Configuratieorder <br> - Aanmelden voor de proefversie van Microsoft 365 E5 <br> - Domein configureren <br>- Microsoft 365 E5-licenties toewijzen <br> - Voltooi de installatiewizard in de portal|
| [Aanvalssyrulatie](mtp-pilot-simulate.md) <br>~2 dagen| Als u een aanval wilt simuleren, kunt u het volgende doen:<br><br>- De vereisten voor de testomgeving controleren <br>- Deulatie uitvoeren <br>- Een incident onderzoeken <br>- het incident oplossen 
| [Afsluiting en samenvatting](mtp-pilot-close.md) <br>~ 1 dag| Wanneer u het einde van het proces hebt bereikt, kunt u het volgende doen:<br><br>- De uiteindelijke uitvoer door<br>- Presenteert uw uitvoer aan uw belanghebbenden <br>- Feedback geven <br>- Neem de volgende stappen 

## <a name="next-step"></a>Volgende stap
|[Planningsfase](mtp-pilot-plan.md) | Uw Microsoft 365 Defender-pilotproject plannen 
|:-------|:-----|
