---
title: Wat komt er in Microsoft Secure Score?
description: Beschrijft de Microsoft Secure Score in het Microsoft 365-beveiligingscentrum, hoe details worden berekend en wat beveiligingsbeheerders kunnen verwachten.
keywords: beveiliging, malware, Microsoft 365, M365, beveiligde score, beveiligingscentrum, verbeteringsacties
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 1a5c5ae702f16bbf47be83837cf244cdd64278cd
ms.sourcegitcommit: 4988934836eee45c890b9bdd5ef73590656c78ba
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2020
ms.locfileid: "43541105"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Wat komt er in Microsoft Secure Score?

Om van Microsoft Secure Score een betere vertegenwoordiger te maken van uw beveiligingshouding en de bruikbaarheid te verbeteren, brengen we in de nabije toekomst enkele wijzigingen door. Je score en de hoogst mogelijke score veranderen. Dit impliceert echter geen verandering in uw beveiligingshouding.

Zie Nieuwe wijzigingen in Microsoft Secure Score voor meer informatie over recente [wijzigingen?](microsoft-secure-score.md#whats-new)

## <a name="april-21st-2020"></a>21 april 2020

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Het verwijderen van verbeteringsacties die niet voldoen aan de verwachtingen voor betrouwbare metingen of geen nuttige weergave van de beveiligingshouding bieden

Om ervoor te zorgen dat de Microsoft Secure Score zinvol is en dat elke verbeteringsactie meetbaar en betrouwbaar is, verwijderen we de volgende verbeteringsacties.

- IRM-beveiligingen toepassen op documenten
- Beleid ter voorkoming van gegevensverlies toepassen

### <a name="adding-azure-ad-improvement-action-in-the-preview-version"></a>Azure AD-verbeteringsactie toevoegen in de voorbeeldversie

- Geef gebruikers geen toestemming voor onbeheerde toepassingen (momenteel beschikbaar in een vrijgegeven versie)

### <a name="adding-azure-atp-improvement-actions-in-the-preview-version"></a>Azure ATP-verbeteringsacties toevoegen in de preview-versie

- Afdrukspoolerservice uitschakelen op domeincontrollers
- Onveilige Kerberos-delegaties wijzigen om imitatie te voorkomen
- Lokale beheerderswachtwoorden beveiligen en beheren met Microsoft LAPS
- Risico op zijwaarts e-bewegens bewegingspad voor gevoelige entiteiten verminderen
- Slapende accounts verwijderen uit gevoelige groepen
- Onveilige SID-geschiedeniskenmerken verwijderen uit entiteiten
- Onveilige accountkenmerken oplossen
- De belichting met wissen van tekstreferenties stoppen
- Verouderde protocollen communicatie stoppen
- Stop zwak versleutelingsgebruik

### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations-in-the-preview-version"></a>Ondersteuning voor beveiligingsaanbevelingen van Microsoft Defender ATP-& Vulnerability Management (TVM) in de preview-versie

- Alle vrijgegeven beveiligingsaanbevelingen van TVM zijn nu ook beschikbaar in Microsoft Secure Score
