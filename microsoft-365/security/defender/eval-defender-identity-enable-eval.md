---
title: Schakel de evaluatieomgeving voor Microsoft Defender voor identiteit in, stel het MDI-exemplaar in, installeer en configureer MDI-sensor, laat MDI-sensor lokale beheerders detecteren
description: Stel Microsoft Defender voor identiteit in Microsoft 365 Defender proeflaboratorium of testomgeving in door & sensor te installeren en lokale beheerders op andere computers te ontdekken.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: f739c9897c9c43831cb4ed23cabaa1705c75d712
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457779"
---
# <a name="enable-the-evaluation-environment-for-microsoft-defender-for-identity"></a>De evaluatieomgeving voor Microsoft Defender voor identiteit inschakelen

**Van toepassing op:**
- Microsoft 365 Defender

Dit artikel is [stap 2 van 2](eval-defender-identity-overview.md) in het proces van het instellen van de evaluatieomgeving voor Microsoft Defender voor identiteit. Zie het [overzichtsartikel](eval-defender-identity-overview.md)voor meer informatie over dit proces.

Gebruik de volgende stappen om uw Microsoft Defender voor identiteitsomgeving in te stellen. 

![Stappen voor het inschakelen van Microsoft Defender voor identiteit in de evaluatieomgeving van Microsoft Defender](../../media/defender/m365-defender-identity-eval-enable-steps.png)

- [Stap 1. Het exemplaar Defender voor identiteit instellen](#step-1-set-up-the-defender-for-identity-instance)
- [Stap 2. De sensor installeren en configureren](#step-2-install-and-configure-the-sensor)
- [Stap 3. Instellingen voor gebeurtenislogboek en proxy configureren op machines met de sensor](#step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor)
- [Stap 4. Toestaan dat Defender voor identiteit lokale beheerders op andere computers identificeert](#step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers)

## <a name="step-1-set-up-the-defender-for-identity-instance"></a>Stap 1. Het exemplaar Defender voor identiteit instellen

Meld u aan bij de Defender for Identity-portal om uw exemplaar te maken en verbind dit exemplaar vervolgens met uw Active Directory-omgeving. 

|  |Stap     |Meer informatie  |
|---------|---------|---------|
|1     | Het exemplaar Defender voor identiteit maken        | [Snelstart: Uw Exemplaar van Microsoft Defender voor identiteit maken](/defender-for-identity/install-step1)        |
|2     | Verbinding maken exemplaar Defender voor identiteit naar uw Active Directory-forest   | [Snelstart: Verbinding maken naar uw Active Directory-forest](/defender-for-identity/install-step2)  |
| | |

## <a name="step-2-install-and-configure-the-sensor"></a>Stap 2. De sensor installeren en configureren

Download, installeer en configureer vervolgens de Defender for Identity-sensor op de domeincontrollers en AD FS-servers in uw on-premises omgeving.

|  |Stap     |Meer informatie  |
|---------|---------|---------|
|1     | Bepaal hoeveel Microsoft Defender voor identiteitssensoren u nodig hebt.        | [Capaciteit plannen voor Microsoft Defender voor identiteit](/defender-for-identity/capacity-planning)   |
|2     | Het installatiepakket voor de sensor downloaden  |  [Snelstart: Het installatiepakket voor de Microsoft Defender voor identiteits sensor downloaden](/defender-for-identity/install-step3)   |
|3     | De Defender for Identity-sensor installeren    |  [Snelstart: De Microsoft Defender for Identity-sensor installeren](/defender-for-identity/install-step4)       |
|4     | De sensor configureren       |  [Instellingen voor De sensor van Microsoft Defender voor identiteit configureren ](/defender-for-identity/install-step5)   |
|   |         |         |

## <a name="step-3-configure-event-log-and-proxy-settings-on-machines-with-the-sensor"></a>Stap 3. Instellingen voor gebeurtenislogboek en proxy configureren op machines met de sensor

Op de machines waar u de sensor op hebt geïnstalleerd, configureert u Windows instellingen voor gebeurtenislogboekverzameling en internetproxy om detectiemogelijkheden in te stellen en te verbeteren.

|  |Stap     |Meer informatie  |
|---------|---------|---------|
|1     | De Windows gebeurtenislogboekverzameling configureren         | [De Windows gebeurtenisverzameling configureren](/defender-for-identity/configure-windows-event-collection)        |
|2     | Instellingen voor internetproxy configureren        | [Instellingen voor eindpuntproxy en internetverbinding configureren voor uw Microsoft Defender voor identiteits sensor](/defender-for-identity/configure-proxy)        |
|   |         |         |

## <a name="step-4-allow-defender-for-identity-to-identify-local-admins-on-other-computers"></a>Stap 4. Toestaan dat Defender voor identiteit lokale beheerders op andere computers identificeert

De detectie van het zijpad van Microsoft Defender for Identity is gebaseerd op query's die lokale beheerders op specifieke machines identificeren. Deze query's worden uitgevoerd met het SAM-R-protocol, met behulp van het Defender for Identity Service-account. 

Om ervoor te zorgen dat Windows clients en servers toestaan dat uw Defender for Identity-account SAM-R kan uitvoeren, moet er een wijziging worden aangebracht in groepsbeleid om het serviceaccount defender voor identiteit toe te voegen naast de geconfigureerde accounts die worden vermeld in het netwerktoegangsbeleid. Zorg ervoor dat u groepsbeleid op alle computers, **behalve domeincontrollers, kunt toepassen.**

Zie Microsoft Defender voor identiteit configureren voor externe oproepen naar SAM voor instructies over hoe u dit [doet.](/defender-for-identity/install-step8-samr) 

## <a name="next-steps"></a>Volgende stappen

Stap 3 van 3: [Pilot Microsoft Defender voor identiteit](eval-defender-identity-pilot.md)

Ga terug naar het overzicht voor [Microsoft Defender evalueren voor identiteit](eval-defender-identity-overview.md)

Ga terug naar het overzicht voor [Evalueren en Microsoft 365 Defender](eval-overview.md)