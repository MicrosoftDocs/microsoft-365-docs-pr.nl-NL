---
title: Test Microsoft Defender voor identiteit, stel configuratiebenchmarks, standaarden, richtlijnen in en maak zelfstudies over het detecteren en herstellen van verschillende identiteitsbedreigingen, zoals verkenning, gecompromitteerde referenties, laterale beweging, domeindominantie en exfiltratiewaarschuwingen, het uitvoeren van gebruikers-, computer-, entiteits- en zijbewegingspaden.
description: Test Microsoft Defender voor identiteit, stel benchmarks in, maak zelfstudies over verkenning, gecompromitteerde referenties, zijbewegingen, domeindominantie en exfiltrationwaarschuwingen, onder andere.
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
ms.openlocfilehash: 14c5b9252e980d1f693139393d26b9405cb1b812
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457766"
---
# <a name="pilot-microsoft-defender-for-identity"></a>Test Microsoft Defender voor identiteit


**Van toepassing op:**
- Microsoft 365 Defender

Dit artikel is [stap 3 van 3](eval-defender-identity-overview.md) in het proces van het instellen van de evaluatieomgeving voor Microsoft Defender voor identiteit. Zie het [overzichtsartikel](eval-defender-identity-overview.md)voor meer informatie over dit proces.

Gebruik de volgende stappen om de pilot voor Microsoft Defender voor identiteit in te stellen en te configureren. Houd er rekening mee dat de aanbevelingen geen pilotgroep bevatten. De beste manier is om door te gaan en de sensor te installeren op al uw servers waarop Active Directory Domain Services (AD DS) en Active Directory Federated Services (AD FS) worden uitgevoerd.

![Stappen voor het toevoegen van Microsoft Defender voor identiteit aan de evaluatieomgeving van Defender](../../media/defender/m365-defender-identity-pilot-steps.png)

In de volgende tabel worden de stappen in de afbeelding beschreven.

- [Stap 1: Benchmarkaanbevelingen configureren voor uw identiteitsomgeving](#step-1-configure-benchmark-recommendations-for-your-identity-environment)
- [Stap 2: Mogelijkheden uitproberen: zelfstudies voor het identificeren en herstellen van verschillende aanvalstypen ](#step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types)

## <a name="step-1-configure-benchmark-recommendations-for-your-identity-environment"></a>Stap 1. Aanbevelingen voor benchmarks configureren voor uw identiteitsomgeving

Microsoft biedt aanbevelingen voor beveiligingsbenchmarks voor klanten die Microsoft Cloud-services gebruiken. De [Azure Security Benchmark](/security/benchmark/azure/overview) (ASB) bevat beschrijvende aanbevolen procedures en aanbevelingen om de beveiliging van werkbelastingen, gegevens en services in Azure te verbeteren.

Deze benchmarkaanbevelingen omvatten [Azure-beveiligingslijn voor Microsoft Defender voor identiteit.](/security/benchmark/azure/baselines/defender-for-identity-security-baseline) Het kan enige tijd duren om deze aanbevelingen te implementeren. Hoewel hiermee de beveiliging van uw identiteitsomgeving sterk wordt vergroot, mogen ze niet verhinderen dat u Microsoft Defender voor identiteit blijft evalueren en implementeren. Deze zijn hier beschikbaar voor uw aandacht.

## <a name="step-2-try-out-capabilities--walk-through-tutorials-for-identifying-and-remediating-different-attack-types"></a>Stap 2. Mogelijkheden uitproberen: zelfstudies voor het identificeren en herstellen van verschillende aanvalstypen

De documentatie van Microsoft Defender voor identiteit bevat een reeks zelfstudies die het proces van het identificeren en herstellen van verschillende aanvalstypen doorlopen.

Zelfstudies voor Defender voor identiteit uitproberen:
- [Verkenningswaarschuwingen](/defender-for-identity/reconnaissance-alerts)
- [Waarschuwingen voor gecompromitteerde referenties](/defender-for-identity/compromised-credentials-alerts)
- [Waarschuwingen voor zijbewegingen](/defender-for-identity/lateral-movement-alerts)
- [Waarschuwingen voor domeindominantie](/defender-for-identity/domain-dominance-alerts)
- [Exfiltrationwaarschuwingen](/defender-for-identity/exfiltration-alerts)
- [Een gebruiker onderzoeken](/defender-for-identity/investigate-a-user)
- [Een computer onderzoeken](/defender-for-identity/investigate-a-computer)
- [Zijbewegingspaden onderzoeken](/defender-for-identity/investigate-lateral-movement-path)
- [Entiteiten onderzoeken](/defender-for-identity/investigate-entity)

## <a name="next-steps"></a>Volgende stappen

[Microsoft Defender evalueren voor Office 365](eval-defender-office-365-overview.md)

Ga terug naar het overzicht voor [Microsoft Defender evalueren voor Office 365](eval-defender-office-365-overview.md)

Ga terug naar het overzicht voor [Evalueren en Microsoft 365 Defender](eval-overview.md)