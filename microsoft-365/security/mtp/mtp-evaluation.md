---
title: Microsoft Threat Protection evalueren
description: Uw Microsoft Threat Protection proef lab-omgeving instellen voor meer informatie over hoe de gecoördineerde oplossing voor beveiliging van apparaten, identiteiten, gegevens en toepassingen uw organisatie kan helpen
keywords: Microsoft Threat Protection-proefversie, Microsoft Threat Protection, Microsoft Threat Protection, Microsoft Threat Protection evaluatie lab, Cyber beveiliging, Geavanceerd permanent risico, beveiliging van ondernemingen, apparaten, apparaat, identiteit, gebruikers, gegevens, toepassingen, incidenten, automatisch onderzoek en herstel, geavanceerde jacht
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: a9d7b514aac8d1a769c0dabf6dcdb54f4bcb447b
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/14/2020
ms.locfileid: "47649959"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a>Een testomgeving voor Microsoft Threat Protection maken 

**Van toepassing op:**
- Microsoft Threat Protection

Het doel van het maken van deze proefversie van de proefversie is het illustreren van de veelomvattende, geïntegreerde en intelligente mogelijkheden van Microsoft Threat Protection ter detectie, preventie, onderzoek en antwoorden die u kunt gebruiken in uw organisatie. 

In deze handleiding vindt u de stappen voor het starten van de evaluatieversie van Microsoft Threat Protection op basis van de aanbevolen implementatie paden. Het doel is om u te helpen bij het instellen van de geïntegreerde Microsoft Threat Protection-Services in een laboratorium omgeving of als concept van een HAALBAARHEIDstest Wanneer u klaar bent met het uitvoeren van uw aanvals simulaties, een geautomatiseerd onderzoek en antwoord, en als u tevreden bent over de resultaten, kunt u deze implementeren in uw productieomgeving met behulp van de hulp van Microsoft technische verkoopmedewerkers of experts binnen uw organisatie. 

Deze handleiding helpt u bij:
- Uw testserver en computers instellen
- Active Directory configureren met gebruikers en groepen
- Azure ATP, Office ATP, Microsoft Defender ATP en de beveiligingsinstellingen voor Microsoft Cloud apps instellen en configureren
- Lokaal beleid instellen voor uw server en computers
- Een bedreiging voor de bedreiging nabootsen voor het genereren van een test incident of waarschuwing in Microsoft Threat Protection

>[!IMPORTANT]
>Voor optimale resultaten volgt u de installatie-instructies voor Lab zo sterk mogelijk.


## <a name="deployment-phases"></a>Implementatiefasen

Er zijn drie fasen in het maken van een testomgeving voor Microsoft Threat Protection en de implementatie ervan:

|Fase | Beschrijving | 
|:-------|:-----|
| ![Fase 1: voorbereiding](../../media/prepare.png)<br>[Fase 1: voorbereiding](prepare-mtpeval.md)| Meer informatie over wat u moet doen als u Microsoft Threat Protection implementeert in een proefversie van het Lab: <br><br>-Belanghebbenden en afmelden <br> -Aandachtspunten voor de omgeving <br>-Access <br>-Configuratie van Azure Active Directory <br> -De configuratie volgorde
|  ![Fase 2: instellen](../../media/setup.png) <br>[Fase 2: instellen](setup-mtpeval.md)|  Voer de stappen uit voor het instellen van uw Microsoft 365-Beveiligingscentrum voor het instellen van uw Microsoft Threat Protection-proef omgeving. U wordt begeleid bij:<br><br>-Registreren voor Microsoft 365 E5-proefabonnement <br>  Domein configureren<br>-Microsoft 365 E5-licenties toewijzen<br>-De wizard Setup voltooien in de portal|
|  ![Fase 3: & onboard configureren](../../media/config-onboard.png) <br>[Fase 3: & onboard configureren](config-mtpeval.md) | Configureer elke Microsoft Threat Protection-pijler en de ingebouwde eindpunten. U wordt begeleid bij:<br><br>-Office 365 Advanced Threat Protection configureren<br>-Beveiliging van Microsoft Cloud-app configureren<br>-Beveiliging van Azure Advanced Threat configureren<br>-Microsoft Defender Advanced Threat Protection configureren 


## <a name="in-scope"></a>In bereik

Het volgende is in het bereik voor de omgevings handleiding voor de proefversie van Lab:
-   Azure Active Directory instellen
-   Microsoft Threat Protection instellen
    -   Registreren voor Microsoft 365 E5-proefabonnement
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

-   Configuratie van oplossingen van derden die kunnen worden geïntegreerd met Microsoft Defender ATP
-   Penetratie tests in productieomgeving

## <a name="next-step"></a>Volgende stap
![Fase 1: voorbereiding](../../media/prepare.png) <br>[Fase 1: voorbereiding](prepare-mtpeval.md) 
<br> Uw Microsoft Threat Protection evaluatie lab-omgeving voorbereiden
