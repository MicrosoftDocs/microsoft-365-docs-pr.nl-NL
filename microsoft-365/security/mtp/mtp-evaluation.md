---
title: Microsoft 365 Defender evalueren
description: Stel uw testtestomgeving of pilotomgeving van Microsoft 365 Defender in om de beveiligingsoplossing uit te proberen en te gebruiken die is ontworpen om apparaten, identiteit, gegevens en toepassingen in uw organisatie te beschermen.
keywords: Microsoft Threat Protection proefversie, probeer Microsoft Threat Protection, evalueer Microsoft Threat Protection, Microsoft Threat Protection evaluation lab, Microsoft Threat Protection pilot, cyber security, advanced persistent threat, enterprise security, devices, device, identity, users, data, applications, incidents, automated investigation and remediation, advanced hunting
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
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6735817a71f9fb50843acad3a13596ec247aa407
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930208"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Een testtest of pilotomgeving met Microsoft 365 Defender maken 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender


Deze handleiding helpt u bij het instellen van een testomgeving met gebruikers en groepen en begeleidt u vervolgens bij de configuratie van de mogelijkheden in Microsoft 365 Defender, zodat u een bedreigings-aanval kunt nabootsen en een zinvolle proefresultaat kunt verkrijgen. 

Het doel van het maken van deze testtestomgeving of pilotomgeving is het illustreren van de uitgebreide en geïntegreerde mogelijkheden van Microsoft 365 Defender. Ervaar hoe deze intelligente beveiligingsoplossing geavanceerde bedreigingen voor uw organisatie detecteert, voorkomt, automatisch onderzoek doet en reageert op geavanceerde bedreigingen. 


U wordt door de stappen begeleid bij het starten van uw evaluatie met Microsoft 365 Defender op basis van de aanbevolen implementatiepaden. Het doel is om de beveiligingsoplossing in te stellen in een testomgeving met een proefaccount of in een pilotomgeving waarin een volledige licentie wordt geproduceerd. Door uw testomgeving of pilotomgeving voor te bereiden, kunt u gebruiks zaken voor beveiligingsbewerkingen presenteren aan besluitvormers in uw organisatie. Wanneer u klaar bent met het uitvoeren van uw aanvalsen en tevreden bent met de resultaten, kunt u deze volledig implementeren en operationeel maken in uw organisatie met behulp van technische verkoopmedewerkers of experts van Microsoft in uw organisatie. 

Deze handleiding helpt u bij het volgende:
- De testserver en computers instellen
- Active Directory configureren met gebruikers en groepen
- Microsoft Defender voor identiteit, Microsoft Defender voor Office 365, Microsoft Defender voor eindpunt en Microsoft Cloud App-beveiliging instellen en configureren
- Lokaal beleid instellen voor uw server en computers
- Een bedreigings-aanval nabootsen om een test-incident of waarschuwing te genereren in Microsoft 365 Defender

>[!IMPORTANT]
>Voor optimale resultaten volgt u de instructies voor het testen van de test zo goed mogelijk.


## <a name="deployment-phases"></a>Implementatiefasen

Er zijn drie fasen bij het maken van een testomgeving met Microsoft 365 Defender.

![Implementatiefasen: voorbereiden, instellen, onboarden](../../media/evaluation-guide-phases.png)

|Fase | Beschrijving | 
|:-------|:-----|
|[Fase 1: Voorbereiden](prepare-mtpeval.md)| Informatie over waar u rekening mee moet houden bij het implementeren van Microsoft 365 Defender in een testtestomgeving of pilotomgeving: <br><br>- Belanghebbenden en sign-off <br> - Aandachtspunten voor de omgeving <br>- Access <br>- Azure Active Directory instellen <br> - Configuratieorder
|[Fase 2: Installatie](setup-mtpeval.md)|  Ga als eerste te werk om het Microsoft 365-beveiligingscentrum te openen voor het instellen van uw testomgeving of pilotomgeving met Microsoft 365 Defender. U wordt begeleid bij het volgende:<br><br>- Aanmelden voor de proefversie van Microsoft 365 E5 <br>  - Domein configureren<br>- Microsoft 365 E5-licenties toewijzen<br>- Voltooi de installatiewizard in de portal|
|[Fase 3: & onboard](config-mtpeval.md) | Configureer elke Microsoft 365 Defender- en onboard-eindpunten. U wordt begeleid bij het volgende:<br><br>- Microsoft Defender voor Office 365 configureren<br>- Microsoft Cloud App-beveiliging configureren<br>- Microsoft Defender configureren voor identiteit<br>- Microsoft Defender configureren voor eindpunt


Nadat u deze handleiding hebt voltooid, zou u de belanghebbenden hebben geïdentificeerd en de vereiste goedkeuringen hebben, de juiste toegangsrechten hebben, zich hebben aangemeld voor een proefabonnement, geconfigureerde domeinen en alle Microsoft 365 Defender-pilaren en worden uw eindpunten onboarded bij de service.

## <a name="key-capabilities"></a>Belangrijkste mogelijkheden

Hoewel Microsoft 365 Defender vele mogelijkheden biedt, is het primaire doel van deze implementatiehandleiding om u op weg te helpen met onboarding-apparaten. Naast onboarding krijgt u met deze richtlijnen de volgende mogelijkheden.


Mogelijkheid | Beschrijving 
:---|:---
Microsoft Defender voor Office 365 | Beschermt uw volledige Office 365-omgeving tegen de bedreigingen van vandaag
Microsoft Defender for Identity | Identificeert en detecteert bedreigingen op gekromde identiteiten en kwaadaardige Insider-acties.
Microsoft Cloud App Security | Biedt uitgebreide zichtbaarheid, controle over gegevensreizen en het detecteren van cyberaanvallen in cloudservices.
Microsoft Defender for Endpoint | Voorkomt, detecteert en biedt antwoordmogelijkheden voor geavanceerde bedreigingen met een uitgebreide eindpuntbeveiliging.


## <a name="in-scope"></a>Binnen het bereik

De volgende taken vallen binnen het kader van deze handleiding:
-   Azure Active Directory instellen
-   Microsoft 365 Defender instellen
    -   Meld u aan voor de proefversie van Microsoft 365 E5 of gebruik uw volledige licentie als u een testfase hebt
    -   Domein configureren
    -   Microsoft 365 E5-licenties toewijzen
    -   De installatiewizard in de portal voltooien
-   Alle Microsoft 365 Defender-pilaren configureren op basis van best practices
    -   Microsoft Defender voor Office 365
    -   Microsoft Defender for Identity
    -   Microsoft Cloud App Security
    -   Microsoft Defender for Endpoint

## <a name="out-of-scope"></a>Buiten het bereik

Deze implementatiehandleiding valt buiten het bereik:

-   Configuratie van oplossingen van derden die kunnen worden geïntegreerd met Microsoft 365 Defender
-   Proeftests in productieomgeving

## <a name="next-step"></a>Volgende stap
[Fase 1: Voorbereiden](prepare-mtpeval.md) 
<br> De testtest of testomgeving van Microsoft 365 Defender voorbereiden
