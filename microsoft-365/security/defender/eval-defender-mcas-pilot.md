---
title: Test Microsoft Cloud App Security met Microsoft 365 Defender, maak testgroepen, configureer voorwaardelijke toegangscontrole, probeer mogelijkheden uit, stel de configuratie in als onderdeel van Microsoft 365 Defender
description: Stel uw testlaboratorium Microsoft 365 Defender testomgeving in om de beveiligingsoplossing te testen en te ervaren die is ontworpen om apparaten, identiteit, gegevens en toepassingen te beveiligen.
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
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: e061bf213ee929f91a48b03c71b9654a7ea76b8c
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457760"
---
# <a name="pilot-microsoft-cloud-app-security-with-microsoft-365-defender"></a>Pilot Microsoft Cloud App Security met Microsoft 365 Defender


**Van toepassing op:**
- Microsoft 365 Defender

Dit artikel is [stap 3 van 3](eval-defender-mcas-overview.md) in het proces van het instellen van de evaluatieomgeving voor Microsoft Cloud App Security. Zie het [overzichtsartikel](eval-defender-mcas-overview.md)voor meer informatie over dit proces.

Gebruik de volgende stappen om de pilot in te stellen en te configureren voor Microsoft Cloud App Security.


![Stappen voor het Microsoft Cloud App Security](../../media/defender/m365-defender-mcas-pilot-steps.png)

- Stap 1. [De testgroep maken: bereik uw pilotimplementatie naar bepaalde gebruikersgroepen](#step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups)
- [Stap 2. Beveiliging configureren: Voorwaardelijke toegang app-beheer](#step-2-configure-protection--conditional-access-app-control)
- [Stap 3. Mogelijkheden uitproberen: zelfstudies voor het beschermen van uw omgeving](#step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment) 


## <a name="step-1-create-the-pilot-group--scope-your-pilot-deployment-to-certain-user-groups"></a>Stap 1. De testgroep maken: bereik uw pilotimplementatie naar bepaalde gebruikersgroepen

Microsoft Cloud App Security stelt u in staat om uw implementatie te scopen. Met Scoping kunt u bepaalde gebruikersgroepen selecteren die moeten worden gecontroleerd op apps of worden uitgesloten van monitoring. U kunt gebruikersgroepen opnemen of uitsluiten. Zie Scoped Deployment (Scoped Deployment) voor een bereik van de [pilotimplementatie.](/cloud-app-security/scoped-deployment)


## <a name="step-2-configure-protection--conditional-access-app-control"></a>Stap 2. Beveiliging configureren: Voorwaardelijke toegang app-beheer

Een van de krachtigste beveiligingen die u kunt configureren, is Voorwaardelijke toegangsbeheer voor apps. Hiervoor is integratie met Azure Active Directory (Azure AD) vereist. Hiermee kunt u beleidsregels voor voorwaardelijke toegang toepassen, inclusief verwante beleidsregels (zoals het vereisen van gezonde apparaten) op cloud-apps die u hebt goedgekeurd. 

De eerste stap in het gebruik Microsoft Cloud App Security saaS-apps te beheren, is deze te ontdekken en vervolgens toe te voegen aan uw Azure AD-tenant. Zie [SaaS-apps](/cloud-app-security/tutorial-shadow-it)in uw netwerk ontdekken en beheren als u hulp nodig hebt bij detectie. Nadat u apps hebt gevonden, voegt [u deze toe aan uw Azure AD-tenant.](/azure/active-directory/manage-apps/add-application-portal)

U kunt beginnen deze te beheren door het volgende te doen:

- Maak eerst in Azure AD een nieuw beleid voor voorwaardelijke toegang en configureer dit in 'Voorwaardelijke toegang app-beheer gebruiken'. Hiermee wordt de aanvraag omgeleid naar Cloud App Security. U kunt één beleid maken en alle SaaS-apps aan dit beleid toevoegen.
- Maak vervolgens in Cloud App Security sessiebeleid. Maak één beleid voor elk besturingselement dat u wilt toepassen.

Zie Apps beveiligen met Microsoft Cloud App Security [Voorwaardelijke toegangsbeheer](/cloud-app-security/proxy-intro-aad)voor meer informatie, inclusief ondersteunde apps en clients. 

Zie Bijvoorbeeld beleidsregels, zie [Aanbevolen Microsoft Cloud App Security voor SaaS-apps.](../office-365-security/mcas-saas-access-policies.md) Dit beleid is gebaseerd op een reeks algemene beleidsregels voor [identiteits-](../office-365-security/microsoft-365-policies-configurations.md) en apparaattoegang die worden aanbevolen als uitgangspunt voor alle klanten. 

## <a name="step-3-try-out-capabilities--walk-through-tutorials-for-protecting-your-environment"></a>Stap 3. Mogelijkheden uitproberen: zelfstudies voor het beschermen van uw omgeving 

De Microsoft Cloud App Security bevat een reeks zelfstudies om u te helpen risico's te ontdekken en uw omgeving te beschermen. 

Probeer zelfstudies Cloud App Security:

- [Verdachte gebruikersactiviteit detecteren](/cloud-app-security/tutorial-suspicious-activity)
- [Risicovolle gebruikers onderzoeken](/cloud-app-security/tutorial-ueba)
- [Riskante OAuth-apps onderzoeken](/cloud-app-security/investigate-risky-oauth)
- [Gevoelige informatie ontdekken en beveiligen](/cloud-app-security/tutorial-dlp)
- [Elke app in uw organisatie in realtime beveiligen](/cloud-app-security/tutorial-proxy)
- [Downloads van gevoelige informatie blokkeren](/cloud-app-security/use-case-proxy-block-session-aad)
- [Uw bestanden beveiligen met beheerders quarantaine](/cloud-app-security/use-case-admin-quarantine)
- [Stapsgewijs verificatie vereisen bij riskante actie](/cloud-app-security/tutorial-step-up-authentication)

## <a name="next-steps"></a>Volgende stappen

[Onderzoeken en reageren met Microsoft 365 Defender in een testomgeving](eval-defender-investigate-respond.md)

Ga terug naar het overzicht voor [Evalueren Microsoft Cloud App Security](eval-defender-mcas-overview.md)

Ga terug naar het overzicht voor [Evalueren en Microsoft 365 Defender](eval-overview.md)