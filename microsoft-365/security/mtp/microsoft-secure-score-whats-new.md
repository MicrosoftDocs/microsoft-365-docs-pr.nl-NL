---
title: Nieuw in Microsoft Secure Score
description: Beschrijft welke nieuwe wijzigingen zijn doorgevoerd in Microsoft Secure Score in het Microsoft 365-Beveiligingscentrum.
keywords: beveiliging, malware, Microsoft 365, M365, Secure Score, Security Center, verbeterings acties
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
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 644e12d3b9dfecc0a31c8d464033e41670bc7b88
ms.sourcegitcommit: 22fd8517707ed3ab6ef996247ad2aa372535ee56
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/19/2020
ms.locfileid: "46815229"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Nieuw in Microsoft Secure Score

Als u Microsoft Secure Score een betere vertegenwoordiger van uw beveiligings Posture wilt maken, hebben we enkele wijzigingen aangebracht. Zie voor meer informatie over geplande wijzigingen wat er wordt weergegeven [in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md).

## <a name="july-2020"></a>Juli 2020

### <a name="adding-improvement-actions-for-azure-advanced-threat-protection"></a>Verbeterings acties toevoegen voor Azure Advanced Threat Protection

- Riskante verplaatsings paden
- Kenmerken van onbeveiligde accounts
- Beveiligingsfuncties inschakelen voor Active Directory-vertrouwensrelaties
- Kenmerken van onveilige SID-geschiedenis van entiteiten verwijderen

## <a name="june-2020"></a>Juni 2020

### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Actie voor verbetering verwijderd van Microsoft Defender Advanced Threat Protection

* Beperking voor oppervlakte-aanvals regels inschakelen

### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Extra verbeterings acties voor Microsoft Defender Advanced Threat Protection

* Voorkomen dat Adobe Reader onderliggende processen kan maken
* Geavanceerde beveiliging gebruiken voor Ransomware
* Alle Office-toepassingen blokkeren om onderliggende processen te maken
* Voorkomen dat Office-toepassingen uitvoerbare inhoud kunnen maken
* JavaScript of VBScript blokkeren voor het starten van downloadbare inhoud
* Het uitvoeren van mogelijk af te schrijven scripts blokkeren
* Uitvoerbare inhoud blokkeren van e-mailclient en webmail
* Voor het maken van onderliggende processen voor Office-communicatietoepassingen blokkeren
* Niet-vertrouwde en niet-ondertekende processen blokkeren die vanaf USB worden uitgevoerd
* Permanente hand stenen via een WMI-gebeurtenisabonnement
* Voorkomen dat Office-toepassingen code in andere processen invoegen
* Voorkomen dat uitvoerbare bestanden worden uitgevoerd, tenzij ze voldoen aan een invloed, ouderdom of vertrouwd lijst criterium
* Proces creatie blokkeren vanuit PSExec en WMI-opdrachten
* Referenties blokkeren van het subsysteem Windows Local Security Authority (lsass.exe)
* Win32 API-aanroepen blokkeren vanuit Office-macro's

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Incompatibiliteit met identificatie beveiligings Score en Graph-API

In de recente versie van Microsoft Secure Score is een verbeterd score model uitgebracht. Met deze wijzigingen kunt u een flexibele en nauwkeurige weergave van uw beveiligings posture. Deze updates hebben echter de Microsoft Secure Score tijdelijk niet compatibel gemaakt met identiteitsbeveiliging en de Graph API.

In tijd wordt de identiteitsbeveiliging Score en de Graph API het nieuwe score model. Vervolgens zien klanten verschillen in de scores die zijn gerapporteerd door Microsoft Secure Score, Identity Secure Score en Graph API. Onze excuses voor het ongemak, en werken om ervoor te zorgen dat deze functies in de toekomst verder compatibel zijn.

## <a name="updated-improvement-actions"></a>Gewijzigde acties voor verbetering

- Azure Active Directory-verbeterings acties toegevoegd
- Actie voor verbetering van Azure Advanced Threat Protection toegevoegd
- Ondersteuning voor de Microsoft Defender ATP- [& bedreiging](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) beveiligingsaanbevelingen van beveiligingsaanbevelingen
    - Alle vrijgegeven beveiligingsaanbevelingen van TVM zijn nu beschikbaar

## <a name="updated-interface-and-functionality"></a>Bijgewerkte interface en functionaliteit

* Alle nieuwe metrische en trends weergaven voor discussies voor CISO en potentiële klanten
* Nieuwe manieren om uw score bij te houden en te verenigen
* Betere tracking en uitleg voor Score regressies
* De acties voor verbetering filteren, markeren, zoeken en groeperen
* Uw toekomstige doelen beheren met behulp van Score projecties en geplande acties
* En nog veel meer.

## <a name="we-want-to-hear-from-you"></a>We horen graag van u

Als u problemen ondervindt, kunt u ons laten weten dat u de community [beveiliging, de Privacy & nalevings](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) Community moet posten. We volgen de community en bieden hulp.

## <a name="related-resources"></a>Verwante informatiebronnen

- [Uw beveiligingspositie vaststellen](microsoft-secure-score-improvement-actions.md)
- [De geschiedenis van uw Microsoft Secure Score bijhouden en bereiken](microsoft-secure-score-history-metrics-trends.md)
- [Binnenkort beschikbaar](microsoft-secure-score-whats-coming.md)
