---
title: Microsoft Threat Protection evalueren
description: Stel uw Microsoft Threat Protection-proef Lab of pilot omgeving in om de beveiligingsoplossing voor het beschermen van apparaten, identiteit, gegevens en toepassingen in uw organisatie uit te proberen.
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
ms.openlocfilehash: d3f63c8ac4ba82a80c365dce564bbd8d3dd4da4b
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447117"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a>Een Microsoft Threat Protection-proefversie Lab of pilot omgeving maken 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection

Het doel van het maken van deze proefversie of pilot omgeving is om de uitgebreide en geïntegreerde functies voor Microsoft Threat Protection te illustreren. Ervaar hoe deze intelligente beveiligingsoplossing detecteert, voorkomt automatisch onderzoek en reageert op geavanceerde bedreigingen voor uw organisatie. 

In deze handleiding vindt u de stappen voor het starten van de evaluatieversie van Microsoft Threat Protection op basis van de aanbevolen implementatie paden. Het doel is om u te helpen bij het instellen van de beveiligingsoplossing in een lab-omgeving met een proefaccount, of in een testomgeving in productie met een volledige licentie. Het voorbereiden van uw proefversie of pilot omgeving kan u helpen bij het presenteren van beveiligingsactiviteiten voor besluitvormings Programma's in uw organisatie. Wanneer u klaar bent met het uitvoeren van uw aanvals simulaties en tevreden bent over de resultaten, kunt u deze in uw organisatie volledig implementeren en operationalize met behulp van de Help van Microsoft Technical Sales professionals of experts in uw organisatie. 

Deze handleiding helpt u bij:
- Uw testserver en computers instellen
- Active Directory configureren met gebruikers en groepen
- Azure ATP, Office ATP, Microsoft Defender ATP en de beveiligingsinstellingen voor Microsoft Cloud apps instellen en configureren
- Lokale beleidsregels instellen voor uw server en computers
- Een bedreiging voor de bedreiging nabootsen voor het genereren van een test incident of waarschuwing in Microsoft Threat Protection

>[!IMPORTANT]
>Voor optimale resultaten volgt u de installatie-instructies voor Lab zo sterk mogelijk.


## <a name="deployment-phases"></a>Implementatiefasen

Er zijn drie fasen in het maken van een testomgeving voor Microsoft Threat Protection en de implementatie ervan:

|Fase | Beschrijving | 
|:-------|:-----|
| ![Fase 1: voorbereiding](../../media/prepare.png)<br>[Fase 1: voorbereiding](prepare-mtpeval.md)| Meer informatie over wat u moet doen wanneer u Microsoft Threat Protection implementeert in een proefversie van het lab of een testomgeving: <br><br>-Belanghebbenden en afmelden <br> -Aandachtspunten voor de omgeving <br>-Access <br>-Configuratie van Azure Active Directory <br> -De configuratie volgorde
|  ![Fase 2: instellen](../../media/setup.png) <br>[Fase 2: instellen](setup-mtpeval.md)|  Voer de volgende stappen uit om toegang te krijgen tot het Microsoft 365-Beveiligingscentrum voor het instellen van uw Microsoft Threat Protection-proefversie Lab of pilot omgeving. U wordt begeleid bij:<br><br>-Registreren voor Microsoft 365 E5-proefabonnement <br>  Domein configureren<br>-Microsoft 365 E5-licenties toewijzen<br>-De wizard Setup voltooien in de portal|
|  ![Fase 3: & onboard configureren](../../media/config-onboard.png) <br>[Fase 3: & onboard configureren](config-mtpeval.md) | Configureer elke Microsoft Threat Protection-pijler en de ingebouwde eindpunten. U wordt begeleid bij:<br><br>-Office 365 Advanced Threat Protection configureren<br>-Beveiliging van Microsoft Cloud-app configureren<br>-Beveiliging van Azure Advanced Threat configureren<br>-Microsoft Defender Advanced Threat Protection configureren 


## <a name="in-scope"></a>In bereik

De volgende taken bevinden zich in het bereik van deze handleiding:
-   Azure Active Directory instellen
-   Microsoft Threat Protection instellen
    -   Registreren voor Microsoft 365 E5-proefabonnement of de volledige licentie gebruiken als u een pilot uitvoert
    -   Domein configureren
    -   Microsoft 365 E5-licenties toewijzen
    -   De installatiewizard in de portal voltooien
-   Alle Microsoft Threat Protection-pijlers configureren op basis van aanbevolen procedures
    -   Office 365 Advanced Threat Protection
    -   Azure Advanced Threat Protection
    -   Microsoft Cloud App Security
    -   Microsoft Defender Advanced Threat Protection

## <a name="out-of-scope"></a>Buiten bereik

Het volgende is niet het bereik van deze Implementatiehandleiding:

-   Configuratie van oplossingen van derden die kunnen worden geïntegreerd met Microsoft Threat Protection
-   Penetratie tests in productieomgeving

## <a name="next-step"></a>Volgende stap
![Fase 1: voorbereiding](../../media/prepare.png) <br>[Fase 1: voorbereiding](prepare-mtpeval.md) 
<br> Uw proefabonnement voor Microsoft Threat Protection of een testomgeving voorbereiden
