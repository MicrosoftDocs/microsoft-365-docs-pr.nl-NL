---
title: De evaluatieomgeving inschakelen voor Microsoft Cloud App Security
description: Leer de architectuur van MCAS in Microsoft Defender voor Office 365 en begrijp de interacties tussen de Microsoft 365 Defender producten.
keywords: Microsoft 365 Defender proefversie, probeer Microsoft 365 Defender, evalueer Microsoft 365 Defender, Microsoft 365 Defender evaluatielaboratorium, Microsoft 365 Defender-pilot, cyberbeveiliging, geavanceerde permanente bedreiging, bedrijfsbeveiliging, apparaten, apparaat, identiteit, gebruikers, gegevens, toepassingen, incidenten, geautomatiseerd onderzoek en herstel, geavanceerd zoeken
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 6ada9613f852e085158b7002cbbb9a9928d36d58
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457761"
---
# <a name="enable-the-evaluation-environment-for-microsoft-cloud-app-security"></a>De evaluatieomgeving inschakelen voor Microsoft Cloud App Security


**Van toepassing op:**

- Microsoft 365 Defender

Dit artikel is [stap 2 van 2](eval-defender-mcas-overview.md) in het proces van het instellen van de evaluatieomgeving voor Microsoft Cloud App Security. Zie het [overzichtsartikel](eval-defender-mcas-overview.md)voor meer informatie over dit proces.

In dit artikel wordt u beschreven hoe u toegang hebt tot de portal Cloud App Security en de benodigde integratie configureert voor het verzamelen van gegevens over het verkeer in cloud-apps.

Als u cloud-apps wilt ontdekken die in uw omgeving worden gebruikt, kunt u een of beide van de volgende dingen doen:

- Ga snel aan de weg met Cloud Discovery door te integreren met Microsoft Defender voor Eindpunt. Met deze native integratie kunt u direct beginnen met het verzamelen van gegevens over cloudverkeer op uw Windows 10 apparaten, in en uit uw netwerk.
- Als u alle cloud-apps wilt ontdekken die toegankelijk zijn voor alle apparaten die zijn verbonden met uw netwerk, implementeert u de Cloud App Security logboekverzamelaar op uw firewalls en andere proxies. Hiermee worden gegevens van uw eindpunten verzameld en naar Cloud App Security voor analyse. Cloud App Security inheems geïntegreerd met sommige proxies van derden voor nog meer mogelijkheden.

Dit artikel bevat richtlijnen voor beide methoden.

Gebruik de volgende stappen om een Microsoft Cloud App Security.

![Stappen om Microsoft-Microsoft Cloud App Security in te stellen in de evaluatieomgeving van Microsoft Defender](../../media/defender/m365-defender-mcas-eval-enable-steps.png)

- [Stap 1. Verbinding maken naar de Cloud App Security portal](#step-1-connect-to-the-cloud-app-security-portal)
- [Stap 2. Integreren met Microsoft Defender voor Eindpunt](#step-2-integrate-with-microsoft-defender-for-endpoint)
- [Stap 3. De logboekverzamelaar Cloud App Security uw firewalls en andere proxies implementeren](#step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies)
- [Stap 4. Bekijk het Cloud Discovery-dashboard om te zien welke apps worden gebruikt in uw organisatie](#step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization)

## <a name="step-1-connect-to-the-cloud-app-security-portal"></a>Stap 1. Verbinding maken naar de Cloud App Security portal

Zie Cloud App Security Snel [starten: Aan de](/cloud-app-security/getting-started-with-cloud-app-security)slag met Microsoft Cloud App Security. 

Als u niet direct verbinding kunt maken met de portal, moet u mogelijk het IP-adres toevoegen aan de lijst met toegestane firewalls. Zie [Basisinstelling voor Cloud App Security.](/cloud-app-security/general-setup)

Als u nog steeds problemen hebt, controleert u [netwerkvereisten.](/cloud-app-security/network-requirements)

## <a name="step-2-integrate-with-microsoft-defender-for-endpoint"></a>Stap 2. Integreren met Microsoft Defender voor Eindpunt

Microsoft Cloud App Security is inheems geïntegreerd met Microsoft Defender voor Endpoint. De integratie vereenvoudigt de implementatie van Cloud Discovery, breidt Cloud Discovery-mogelijkheden uit buiten uw bedrijfsnetwerk en maakt onderzoek op apparaatbasis mogelijk. Deze integratie laat zien dat cloud-apps en -services worden gebruikt vanaf it-beheerde Windows 10 apparaten. 

Als u Microsoft Defender voor Eindpunt al hebt ingesteld, is het configureren van integratie met Cloud App Security een schakelknop in Microsoft 365 Defender. Nadat integratie is ingeschakeld, kunt u terugkeren naar de Cloud App Security portal en uitgebreide gegevens weergeven in het Cloud Discovery Dashboard.

Zie Microsoft Defender voor [endpoint-integratie](/cloud-app-security/mde-integration)met Microsoft Cloud App Security. 

## <a name="step-3-deploy-the-cloud-app-security-log-collector-on-your-firewalls-and-other-proxies"></a>Stap 3. De logboekverzamelaar Cloud App Security uw firewalls en andere proxies implementeren

Voor dekking op alle apparaten die met uw netwerk zijn verbonden, implementeert u de Cloud App Security-logboekverzamelaar op uw firewalls en andere proxies om gegevens van uw eindpunten te verzamelen en deze te verzenden naar Cloud App Security voor analyse. 

Als u een van de volgende Secure Web Gateways (SWG) gebruikt, biedt Cloud App Security naadloze implementatie en integratie:
- Zscaler
- iboss
- Corrata
- Beveiliging van Menlo

Zie Clouddetectie instellen voor meer informatie over het integreren met deze [netwerkapparaten.](/cloud-app-security/set-up-cloud-discovery) 
## <a name="step-4-view-the-cloud-discovery-dashboard-to-see-what-apps-are-being-used-in-your-organization"></a>Stap 4. Bekijk het Cloud Discovery-dashboard om te zien welke apps worden gebruikt in uw organisatie

Het Cloud Discovery-dashboard is ontworpen om u meer inzicht te geven in de manier waarop cloud-apps in uw organisatie worden gebruikt. Het biedt in één oogopslag een overzicht van welke soorten apps worden gebruikt, uw geopende waarschuwingen en de risiconiveaus van apps in uw organisatie. 

Zie Werken met ontdekte apps om aan de slag te gaan met het Cloud [Discovery-dashboard.](/cloud-app-security/discovered-apps)

## <a name="next-steps"></a>Volgende stappen

Stap 3 van 3: [Pilot Microsoft Cloud App Security](eval-defender-mcas-pilot.md)

Ga terug naar het overzicht voor [Evalueren Microsoft Cloud App Security](eval-defender-mcas-overview.md)

Ga terug naar het overzicht voor [Evalueren en Microsoft 365 Defender](eval-overview.md)