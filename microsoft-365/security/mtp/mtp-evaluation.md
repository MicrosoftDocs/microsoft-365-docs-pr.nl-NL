---
title: Microsoft-dreigingsbeveiliging evalueren
description: Stel uw proefversie van Microsoft Threat Protection in om uit te proberen hoe de gecoördineerde oplossing voor bedreigingsbescherming die is ontworpen om apparaten, identiteit, gegevens en toepassingen te beschermen, uw organisatie kan helpen
keywords: Proefversie van Microsoft Threat Protection, probeer Microsoft Threat Protection, evalueer Microsoft Threat Protection, Microsoft Threat Protection evaluation lab, cyber security, advanced persistent threat, enterprise security, devices, device, identity, users, data, applications, incidents, automated investigation and remediation, advanced hunting
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
ms.openlocfilehash: f6ee8147965a29b87d84690535116f096e4c6006
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049637"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a>Een proefversie van Microsoft Threat Protection maken 

**Geldt voor:**
- Microsoft Threat Protection

Het doel van het maken van deze proeflabomgeving is het illustreren van de uitgebreide, geïntegreerde en intelligente mogelijkheden van Microsoft Threat Protection in detectie, preventie, onderzoek en respons die u in uw organisatie gebruiken. 

Deze handleiding neemt u mee door de stappen om uw Microsoft Threat Protection-evaluatie te starten op basis van de aanbevolen implementatiepaden. Het doel is om u te helpen bij het opzetten van de geïntegreerde Microsoft Threat Protection-services in een labomgeving of als proof of concept (POC) bij de presentatie aan besluitvormers van beveiligingsoplossingen in uw organisatie. Wanneer u klaar bent met het uitvoeren van uw aanvalssimulaties, geautomatiseerd onderzoek en reactie, en tevreden bent met de resultaten, u deze implementeren in uw productieomgeving met de hulp van Microsoft Technical Sales Professionals of experts in uw organisatie. 

Deze gids helpt u:
- Uw labserver en computers instellen
- Active Directory configureren met gebruikers en groepen
- Azure ATP, Office ATP, Microsoft Defender ATP en Microsoft Cloud App Security instellen en configureren
- Lokaal beleid instellen voor uw server en computers
- Een bedreigingsaanval nabootsen om een testincident of waarschuwing te genereren in Microsoft Threat Protection

>[!IMPORTANT]
>Volg voor optimale resultaten de instructies voor het opzetten van het lab zo goed mogelijk.


## <a name="deployment-phases"></a>Implementatiefasen

Er zijn drie fasen in het maken van een Microsoft Threat Protection trial lab omgeving en implementeren:

|Fase | Beschrijving | 
|:-------|:-----|
| ![Fase 1: Voorbereiden](../../media/prepare.png)<br>[Fase 1: Voorbereiden](prepare-mtpeval.md)| Lees waar u rekening mee moet houden bij het implementeren van Microsoft Threat Protection in een proeflabomgeving: <br><br>- Belanghebbenden en afmelding <br> - Milieuoverwegingen <br>- Toegang <br>- Azure Active Directory-instelling <br> - Configuratievolgorde
|  ![Fase 2: Setup](../../media/setup.png) <br>[Fase 2: Setup](setup-mtpeval.md)|  Neem de eerste stappen om toegang te krijgen tot Microsoft 365 Security Center om uw Microsoft Threat Protection trial lab-omgeving in te stellen. U wordt begeleid naar:<br><br>- Aanmelden voor Microsoft 365 E5-proefversie <br>  - Domein configureren<br>- Microsoft 365 E5-licenties toewijzen<br>- De wizard Setup voltooien in de portal|
|  ![Fase 3: & configureren](../../media/config-onboard.png) <br>[Fase 3: & configureren](config-mtpeval.md) | Configureer elke Microsoft Threat Protection-pijler en eindpunten aan boord. U wordt begeleid naar:<br><br>- Geavanceerde bedreigingsbeveiliging van Office 365 configureren<br>- Microsoft Cloud App-beveiliging configureren<br>- Azure Advanced Threat Protection configureren<br>- Microsoft Defender Advanced Threat Protection configureren 


## <a name="in-scope"></a>In werkingssfeer

Het volgende is in het kader van deze proef lab omgeving gids:
-   Azure Active Directory instellen
-   Microsoft-bedreigingsbeveiliging instellen
    -   Aanmelden voor Microsoft 365 E5-proefversie
    -   Domein configureren
    -   Microsoft 365 E5-licenties toewijzen
    -   De wizard instellen in de portal voltooien
-   Alle pijlers voor Microsoft-bedreigingsbeveiliging configureren op basis van best practices
    -   Office 365 Advanced Threat Protection
    -   Azure Advanced Threat Protection
    -   Microsoft Cloud App Security
    -   Microsoft Defender Advanced Threat Protection

## <a name="out-of-scope"></a>Buiten het toepassingsgebied

Deze implementatiehandleiding valt buiten het bereik van deze implementatiehandleiding:

-   Configuratie van oplossingen van derden die kunnen worden geïntegreerd met Microsoft Defender ATP
-   Penetratietesten in productieomgeving

## <a name="next-step"></a>Volgende stap
|||
|:-------|:-----|
|![Fase 1: Voorbereiden](../../media/prepare.png) <br>[Fase 1: Voorbereiden](prepare-mtpeval.md) | Uw Microsoft Threat Protection-evaluatielabomgeving voorbereiden
