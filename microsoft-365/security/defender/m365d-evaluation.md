---
title: Microsoft 365 Defender evalueren
description: Stel uw proeflaboratorium of testomgeving van Microsoft 365 Defender in om de beveiligingsoplossing uit te proberen en te ervaren die is ontworpen om apparaten, identiteit, gegevens en toepassingen in uw organisatie te beschermen.
keywords: Microsoft Threat Protection trial, try Microsoft Threat Protection, evaluate Microsoft Threat Protection, Microsoft Threat Protection evaluation lab, Microsoft Threat Protection pilot, cyber security, advanced persistent threat, enterprise security, devices, device, identity, users, data, applications, incidents, automated investigation and remediation, advanced hunting
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
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 2ea829e0e2697facd2522dbf16ced7d620662eee
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060570"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Een proeflaboratorium of testomgeving voor Microsoft 365 Defender maken 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender


Deze handleiding helpt u bij het instellen van een labomgeving met gebruikers en groepen en begeleidt u vervolgens bij de configuratie van de mogelijkheden in Microsoft 365 Defender, zodat u een bedreigingsaanval kunt nabootsen en een zinvol proefresultaat kunt verkrijgen. 

Het doel van het maken van dit proeflaboratorium of testomgeving is het illustreren van de uitgebreide en geïntegreerde Microsoft 365 Defender-mogelijkheden. Ervaar hoe deze intelligente beveiligingsoplossing geavanceerde bedreigingen in uw organisatie detecteert, voorkomt, automatisch onderzoekt en beantwoordt. 


U wordt begeleid bij de stappen voor het starten van de Evaluatie van Microsoft 365 Defender op basis van de aanbevolen implementatiepaden. Het doel is om u te helpen bij het instellen van de beveiligingsoplossing in een labomgeving met een proefaccount of in een testomgeving in productie met een volledige licentie. Als u uw proeflaboratorium of testomgeving voorbereidt, kunt u gebruiksgevallen voor beveiligingsbewerkingen presenteren aan besluitvormers in uw organisatie. Wanneer u klaar bent met het uitvoeren van uw aanvalssimulaties en tevreden bent over de resultaten, kunt u deze volledig implementeren en operationeel maken in uw organisatie met de hulp van Technische Verkoopmedewerkers of experts van Microsoft in uw organisatie. 

Deze handleiding helpt u:
- Uw labserver en -computers instellen
- Active Directory configureren met gebruikers en groepen
- Microsoft Defender voor identiteit instellen en configureren, Microsoft Defender voor Office 365, Microsoft Defender voor Eindpunt en Microsoft Cloud App-beveiliging
- Lokaal beleid instellen voor uw server en computers
- Een bedreigingsaanval nabootsen om een testincident of waarschuwing te genereren in Microsoft 365 Defender

>[!IMPORTANT]
>Voor optimale resultaten volgt u de instructies voor het instellen van het lab zo goed mogelijk.


## <a name="deployment-phases"></a>Implementatiefasen

Er zijn drie fasen in het maken van een proeflabomgeving van Microsoft 365 Defender.

![Implementatiefasen: voorbereiden, instellen, onboard](../../media/evaluation-guide-phases.png)

|Fase | Beschrijving | 
|:-------|:-----|
|[Fase 1: Voorbereiden](prepare-m365d-eval.md)| Lees waar u rekening mee moet houden bij de implementatie van Microsoft 365 Defender in een testlab of testomgeving: <br><br>- Belanghebbenden en aanmelding <br> - Milieuoverwegingen <br>- Access <br>- Configuratie van Azure Active Directory <br> - Configuratieorder
|[Fase 2: Setup](setup-m365deval.md)|  Neem de eerste stappen om toegang te krijgen tot het Microsoft 365-beveiligingscentrum om uw proeflaboratorium of testomgeving van Microsoft 365 Defender in te stellen. U wordt begeleid naar:<br><br>- Registreren voor proefversie van Microsoft 365 E5 <br>  - Domein configureren<br>- Microsoft 365 E5-licenties toewijzen<br>- De installatiewizard in de portal voltooien|
|[Fase 3: Configureren & Onboard](config-m365d-eval.md) | Configureer elke Microsoft 365 Defender-pijler en onboard-eindpunten. U wordt begeleid naar:<br><br>- Microsoft Defender configureren voor Office 365<br>- Microsoft Cloud App-beveiliging configureren<br>- Microsoft Defender configureren voor identiteit<br>- Microsoft Defender configureren voor eindpunt


Nadat u deze handleiding hebt voltooid, hebt u de betrokken belanghebbenden en de vereiste goedkeuringen geïdentificeerd, hebt u de juiste toegangsmachtigingen, hebt u zich aangemeld voor proefversies, geconfigureerde domeinen en elk van de Microsoft 365 Defender-pijlers, en worden uw eindpunten aan de service onboarded.

## <a name="key-capabilities"></a>Belangrijke mogelijkheden

Hoewel Microsoft 365 Defender veel mogelijkheden biedt, is het primaire doel van deze implementatiehandleiding om aan de slag te gaan met onboarding-apparaten. Naast onboarding kunt u met deze richtlijnen aan de slag met de volgende mogelijkheden.


Mogelijkheid | Beschrijving 
:---|:---
Microsoft Defender voor Office 365 | Helpt uw hele Office 365-envrionment te beschermen tegen de huidige bedreigingen
Microsoft Defender for Identity | Identificeert en detecteert bedreigingen op gecompromitteerde identiteiten en kwaadaardige insideracties.
Microsoft Cloud App Security | Biedt uitgebreide zichtbaarheid, beheer gegevensreizen en detecteer cyberthreats in cloudservices.
Microsoft Defender for Endpoint | Voorkomt, detecteert en biedt antwoordmogelijkheden voor geavanceerde bedreigingen met uitgebreide eindpuntbeveiliging.


## <a name="in-scope"></a>In bereik

De volgende taken vallen onder het bereik van deze handleiding:
-   Azure Active Directory instellen
-   Microsoft 365 Defender instellen
    -   Meld u aan voor microsoft 365 E5-proefversie of gebruik uw volledige licentie als u een pilot gebruikt
    -   Domein configureren
    -   Microsoft 365 E5-licenties toewijzen
    -   De installatiewizard in de portal voltooien
-   Alle Microsoft 365 Defender-pilaren configureren op basis van best practices
    -   Microsoft Defender voor Office 365
    -   Microsoft Defender for Identity
    -   Microsoft Cloud App Security
    -   Microsoft Defender for Endpoint

## <a name="out-of-scope"></a>Buiten bereik

De volgende opties vallen buiten het bereik van deze implementatiehandleiding:

-   Configuratie van oplossingen van derden die kunnen worden geïntegreerd met Microsoft 365 Defender
-   Penetratietests in de productieomgeving

## <a name="next-step"></a>Volgende stap
[Fase 1: Voorbereiden](prepare-m365d-eval.md) 
<br> Uw proeflaboratorium of testomgeving voor Microsoft 365 Defender voorbereiden
