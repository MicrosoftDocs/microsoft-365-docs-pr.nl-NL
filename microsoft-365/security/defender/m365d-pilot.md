---
title: Uw testproject voor Microsoft 365 Defender uitvoeren
description: Voer uw testproject Microsoft 365 Defender in productie uit om de voordelen en acceptatie van Microsoft 365 Defender effectief te bepalen.
keywords: Microsoft Threat Protection pilot, run pilot Microsoft Threat Protection project, evaluate Microsoft Threat Protection in production, Microsoft Threat Protection pilot project, cyber security, advanced persistent threat, enterprise security, devices, device, identity, users, data, applications, incidents, automated investigation and remediation, advanced hunting
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1dd310d962cbce2b339cf09d5be6317c227d3f13
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060386"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>Uw testproject voor Microsoft 365 Defender uitvoeren 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender


Deze handleiding helpt u bij het uitvoeren van een pilotproject door aanwijzers te geven om ervoor te zorgen dat u een goed gestructureerd plan hebt, u begeleidt bij het gebruik van de functie aanvalssimulatie en de pilot ten slotte afsluit met belangrijke take-aways om na te denken over en de resultaten te documenteren.

![Fasen in het uitvoeren van een Microsoft 365 Defender-pilot](../../media/pilotphases.png)


Met een pilot kunt u effectief bepalen wat het voordeel is van het gebruik van Microsoft 365 Defender. Voordat u Microsoft 365 Defender in uw productieomgeving inschakelen en uw gebruiksgevallen start, kunt u het beste plannen om de taken voor uw testproject te bepalen en de succescriteria in te stellen. 


## <a name="how-to-use-this-pilot-playbook"></a>Deze test playbook gebruiken

Deze handleiding bevat een overzicht van Microsoft 365 Defender en stapsgewijs instructies over het instellen van uw pilotproject. 

Microsoft 365 Defender is een geïntegreerde suite voor bedrijfsdefensie vóór en na inbreuk die inheems bescherming, detectie, preventie, onderzoek en antwoord coördineert in eindpunten, identiteiten, e-mail en toepassingen om geïntegreerde bescherming tegen geavanceerde aanvallen te bieden. Dit doet het door de volgende mogelijkheden te combineren en te orveren tot één beveiligingsoplossing:
  - Microsoft Defender voor Eindpunt, de nieuwe naam voor Microsoft Defender Advanced Threat Protection (eindpunten)
  - Microsoft Defender voor Office 365, de nieuwe naam voor Office 365 ATP (e-mail) 
  - Microsoft Defender voor identiteit, de nieuwe naam voor Azure ATP (identiteit) 
  - Microsoft Cloud App Security (apps)

![Image of_Microsoft 365 Defender solution for users, Microsoft Defender for Identity, for endpoints Microsoft Defender for Endpoint, for cloud apps, Microsoft Cloud App Security, and for data, Microsoft Defender for Office 365](../../media/mtp/m365pillars.png)

Met de geïntegreerde Microsoft 365 Defender-oplossing kunnen beveiligingsprofessionals de bedreigingssignalen die Microsoft Defender voor Eindpunt, Microsoft Defender voor Office 365, Microsoft Defender voor identiteit en Microsoft Cloud App Security ontvangen, samensmelten en bepalen wat het volledige bereik en de impact van de bedreiging is, hoe de bedreiging in de omgeving is ingevoerd, wat de gevolgen zijn en wat de gevolgen zijn voor de organisatie. Microsoft 365 Defender voert automatisch actie om de aanval te voorkomen of te stoppen en getroffen postvakken, eindpunten en gebruikersidentiteiten te voorkomen of te herstellen. Zie het [Microsoft 365 Defender-overzicht voor](microsoft-365-defender.md) meer informatie.



De volgende voorbeeldtijdlijn is afhankelijk van de juiste resources in uw omgeving. Sommige detecties en werkstromen hebben mogelijk meer leertijd nodig dan de andere.

![Voorbeeldtijdlijn bij het uitvoeren van een Microsoft 365 Defender-pilot](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>Volg de testinstructies zo nauwkeurig mogelijk voor optimale resultaten.


### <a name="pilot-playbook-phases"></a>Testfasen van een playbook 

Er zijn vier fasen in het uitvoeren van een Microsoft 365 Defender-pilot:

|Fase | Beschrijving | 
|:-------|:-----|
| [Planning](m365d-pilot-plan.md)<br> ~ 1 dag| Lees waar u rekening mee moet houden voordat u uw Microsoft 365 Defender-testproject gaat uitvoeren: <br><br>- Bereik <br> - Use cases <br>- Vereisten <br>- Testplan <br> - Succescriteria <br> - Scorecard 
| [Voorbereiding](m365d-evaluation.md) <br>~2 dagen|  Access Microsoft 365 Security Center to set up your Microsoft 365 Defender pilot environment. U wordt begeleid naar:<br><br>- Identificeer belanghebbenden en zoek aanmelding voor uw pilot <br> - Milieuoverwegingen <br>- Access <br>- Configuratie van Azure Active Directory <br> - Configuratieorder <br> - Registreren voor proefversie van Microsoft 365 E5 <br> - Domein configureren <br>- Microsoft 365 E5-licenties toewijzen <br> - De installatiewizard in de portal voltooien|
| [Aanvalssimulatie](m365d-pilot-simulate.md) <br>~2 dagen| Als u een aanval wilt simuleren, wordt u begeleid naar:<br><br>- Controleer de vereisten voor de testomgeving <br>- Voer de simulatie uit <br>- Een incident onderzoeken <br>- het incident oplossen 
| [Sluiten en samenvatting](m365d-pilot-close.md) <br>~ 1 dag| Wanneer u het einde van het proces hebt bereikt, wordt u begeleid naar:<br><br>- Ga door de uiteindelijke uitvoer<br>- Presenteert uw uitvoer aan uw belanghebbenden <br>- Feedback geven <br>- Volgende stappen ondernemen 

## <a name="next-step"></a>Volgende stap
|[Planningsfase](m365d-pilot-plan.md) | Uw Microsoft 365 Defender-testproject plannen 
|:-------|:-----|
