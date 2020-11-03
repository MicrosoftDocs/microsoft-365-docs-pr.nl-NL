---
title: Evalueer Microsoft 365 Defender
description: Stel uw proefabonnement voor Microsoft 365 Defender of pilot omgeving in om de beveiligingsoplossing voor het beschermen van apparaten, identiteit, gegevens en toepassingen in uw organisatie uit te proberen.
keywords: Microsoft Threat Protection-proefversie, Microsoft Threat Protection, Microsoft Threat Protection, Microsoft Threat Protection evaluatie lab, Microsoft Threat Protection pilot, Cyber beveiliging, geavanceerde, permanente bedreiging, Enterprise-gebruikers, gegevens, toepassingen, incidenten, automatisch onderzoek en herstel, geavanceerde jacht
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: d6c96f7720344721bb2786dc130c490a5a8ea657
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846482"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Een Microsoft 365 Defender-proef Lab of pilot omgeving maken 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Het doel van het maken van deze proefversie of pilot omgeving is het illustreren van de allesomvattende en geïntegreerde Microsoft 365 Defender-mogelijkheden. Ervaar hoe deze intelligente beveiligingsoplossing detecteert, voorkomt automatisch onderzoek en reageert op geavanceerde bedreigingen voor uw organisatie. 

In deze handleiding vindt u de stappen voor het starten van uw Microsoft 365-evaluatieversie op basis van de aanbevolen distributie paden. Het doel is om u te helpen bij het instellen van de beveiligingsoplossing in een lab-omgeving met een proefaccount, of in een testomgeving in productie met een volledige licentie. Het voorbereiden van uw proefversie of pilot omgeving kan u helpen bij het presenteren van beveiligingsactiviteiten voor besluitvormings Programma's in uw organisatie. Wanneer u klaar bent met het uitvoeren van uw aanvals simulaties en tevreden bent over de resultaten, kunt u deze in uw organisatie volledig implementeren en operationalize met behulp van de Help van Microsoft Technical Sales professionals of experts in uw organisatie. 

Deze handleiding helpt u bij:
- Uw testserver en computers instellen
- Active Directory configureren met gebruikers en groepen
- Microsoft Defender voor identiteit instellen en configureren, Microsoft Defender voor Office 365, Microsoft Defender voor eindpunt en beveiliging van de Cloud-app
- Lokale beleidsregels instellen voor uw server en computers
- Een aanval in de bedreiging nabootsen voor het genereren van een test incident of waarschuwing in Microsoft 365 Defender

>[!IMPORTANT]
>Voor optimale resultaten volgt u de installatie-instructies voor Lab zo sterk mogelijk.


## <a name="deployment-phases"></a>Implementatiefasen

Er zijn drie fasen in het maken van een proefversie van Microsoft voor Microsoft 365 Defender met proef omgevingen en de implementatie ervan:

|Fase | Beschrijving | 
|:-------|:-----|
| ![Fase 1: voorbereiding](../../media/prepare.png)<br>[Fase 1: voorbereiding](prepare-mtpeval.md)| Meer informatie over wat u moet doen wanneer u Microsoft 365 Defender implementeert in een proefversie van het lab of een testomgeving: <br><br>-Belanghebbenden en afmelden <br> -Aandachtspunten voor de omgeving <br>-Access <br>-Configuratie van Azure Active Directory <br> -De configuratie volgorde
|  ![Fase 2: instellen](../../media/setup.png) <br>[Fase 2: instellen](setup-mtpeval.md)|  Voer de volgende stappen uit om toegang te krijgen tot het Microsoft 365-Beveiligingscentrum voor het instellen van uw proefversie van Microsoft 365 Defender of prototype. U wordt begeleid bij:<br><br>-Registreren voor Microsoft 365 E5-proefabonnement <br>  Domein configureren<br>-Microsoft 365 E5-licenties toewijzen<br>-De wizard Setup voltooien in de portal|
|  ![Fase 3: & onboard configureren](../../media/config-onboard.png) <br>[Fase 3: & onboard configureren](config-mtpeval.md) | Configureer elke Microsoft 365 Defender-pijler pijler en de ingebouwde eindpunten. U wordt begeleid bij:<br><br>-Microsoft Defender voor Office 365 configureren<br>-Beveiliging van Microsoft Cloud-app configureren<br>-Microsoft Defender configureren voor identiteit<br>-Microsoft Defender voor eindpunt configureren


## <a name="in-scope"></a>In bereik

De volgende taken bevinden zich in het bereik van deze handleiding:
-   Azure Active Directory instellen
-   Microsoft 365 Defender instellen
    -   Registreren voor Microsoft 365 E5-proefabonnement of de volledige licentie gebruiken als u een pilot uitvoert
    -   Domein configureren
    -   Microsoft 365 E5-licenties toewijzen
    -   De installatiewizard in de portal voltooien
-   Alle Microsoft 365 Defender-pijlers configureren op basis van aanbevolen procedures
    -   Microsoft Defender voor Office 365
    -   Microsoft Defender voor identiteit
    -   Microsoft Cloud App Security
    -   Microsoft Defender voor eindpunt

## <a name="out-of-scope"></a>Buiten bereik

Het volgende is niet het bereik van deze Implementatiehandleiding:

-   Configuratie van oplossingen van derden die kunnen worden geïntegreerd met Microsoft 365 Defender
-   Penetratie tests in productieomgeving

## <a name="next-step"></a>Volgende stap
![Fase 1: voorbereiding](../../media/prepare.png) <br>[Fase 1: voorbereiding](prepare-mtpeval.md) 
<br> Uw proefabonnement voor Microsoft 365 Defender of pilot omgeving voorbereiden
