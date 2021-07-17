---
title: Uw evaluatieomgeving Microsoft 365 Defender naar productie, Microsoft 365 Defender evaluatie, een evaluatie proberen, een evaluatie houden, productie-evaluatie houden
description: Gebruik dit artikel om uw evals van MDI, MDO, MDE en MCAS te promoten in uw live omgeving in Microsoft 365 Defender of M365D.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b67f0f493c97b900fa08b10e3eb7a5967560dcfd
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457907"
---
# <a name="promote-your-microsoft-365-defender-evaluation-environment-to-production"></a>Uw evaluatieomgeving Microsoft 365 Defender naar de productie

**Van toepassing op:**
- Microsoft 365 Defender

Koop eerst de benodigde licentie om Microsoft 365 Defender evaluatieomgeving te promoten naar de productie. Volg de stappen in [De eval-omgeving maken](eval-create-eval-environment.md) en koop de Office 365 E5 licentie (in plaats van gratis proefversie starten te selecteren).

Voltooi vervolgens een extra configuratie en vouw uw testgroepen uit totdat deze volledige productie hebben bereikt. 

## <a name="microsoft-defender-for-identity"></a>Microsoft Defender for Identity
Voor Defender voor identiteit is geen extra configuratie vereist. Zorg ervoor dat u de benodigde licenties hebt gekocht en de sensor hebt geïnstalleerd op al uw Active Directory-domeincontrollers en AD FS-servers (Active Directory Federation Services). 

## <a name="microsoft-defender-for-office-365"></a>Microsoft Defender voor Office 365
Na het evalueren of piloten van MDO, kan deze worden gepromoveerd naar uw hele productieomgeving.
1. Koop en inrichten van de benodigde licenties en wijs deze toe aan uw productiegebruikers.
2. Voer aanbevolen basislijnbeleidsconfiguraties (Standaard of Strikt) opnieuw uit op uw productie-e-maildomein of specifieke groepen gebruikers.
3. U kunt desgewenst aangepaste MDO-beleidsregels maken en configureren voor uw productie-e-maildomein of groepen gebruikers.  Houd er echter rekening mee dat toegewezen basislijnbeleid altijd voorrang heeft op aangepast beleid.
4. Werk de openbare MX-record voor uw productie-e-maildomein bij om rechtstreeks naar EOP op te lossen.
5. Schakel SMTP-gateways van derden uit en schakel ALLE EXO-connectors die aan dit relais zijn gekoppeld uit of verwijder deze uit.

## <a name="microsoft-defender-for-endpoint"></a>Microsoft Defender voor Eindpunt
Als u de evaluatieomgeving van Microsoft Defender voor eindpunt wilt bevorderen van een pilot naar de productie, hoeft u alleen maar meer eindpunten aan te nemen bij de service met behulp van een van de ondersteunde [hulpprogramma's en methoden.](/defender-endpoint/onboard-configure)

Gebruik de volgende algemene richtlijnen om meer apparaten aan te nemen bij Microsoft Defender voor Eindpunt. 

1. Controleer of het apparaat aan de [minimumvereisten voldoet.](/defender-endpoint/minimum-requirements)
2. Volg, afhankelijk van het apparaat, de configuratiestappen in de onboarding-sectie van de Defender for Endpoint-portal.
3. Gebruik het juiste beheerprogramma en de implementatiemethode voor uw apparaten.
4.  Voer een detectietest uit om te controleren of de apparaten correct zijn onboarded en rapporteren aan de service.

## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security
Microsoft Cloud App Security vereist geen extra configuratie. Zorg ervoor dat u de benodigde licenties hebt gekocht. Als u de implementatie hebt gebereikt naar bepaalde gebruikersgroepen, vergroot u het bereik van deze groepen totdat u de productieschaal hebt bereikt. 

