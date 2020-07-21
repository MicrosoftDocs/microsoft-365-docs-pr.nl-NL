---
title: Nieuwe gegevens in Microsoft Secure Score
description: Beschrijft welke nieuwe wijzigingen er zijn gebeurd met Microsoft Secure Score in het Microsoft 365-beveiligingscentrum.
keywords: beveiliging, malware, Microsoft 365, M365, secure score, security center, verbeteracties
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
ms.openlocfilehash: 4f9f4f40b9cd88cad1676417d467d04367eaa0be
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200119"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Nieuwe gegevens in Microsoft Secure Score

Om van Microsoft Secure Score een betere vertegenwoordiger van uw beveiligingshouding te maken, hebben we enkele wijzigingen aangebracht. Zie Wat komt er in Microsoft Secure Score voor meer informatie over geplande [wijzigingen?](microsoft-secure-score-whats-coming.md)

## <a name="june-2020"></a>Juni 2020

### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Verwijderde verbeteringsactie voor Geavanceerde bedreigingsbeveiliging van Microsoft Defender

* Regels voor attack surface reduction inschakelen

### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Verbeterde acties voor Microsoft Defender Advanced Threat Protection

* Adobe Reader blokkeren voor het maken van onderliggende processen
* Gebruik geavanceerde bescherming tegen ransomware
* Alle Office-toepassingen blokkeren bij het maken van onderliggende processen
* Office-toepassingen blokkeren bij het maken van uitvoerbare inhoud
* JavaScript of VBScript blokkeren bij het starten van gedownloade uitvoerbare inhoud
* De uitvoering van mogelijk versluierde scripts blokkeren
* Uitvoerbare inhoud blokkeren van e-mailclient en webmail
* Office-communicatietoepassing blokkeren bij het maken van onderliggende processen
* Niet-vertrouwde en niet-ondertekende processen blokkeren die worden uitgevoerd vanaf USB
* Persistentie blokkeren via WMI-evenementabonnement
* Office-toepassingen blokkeren om code in andere processen te injecteren
* Uitvoerbare bestanden blokkeren voor het uitvoeren van bestanden, tenzij ze voldoen aan een prevalentie-, leeftijds- of vertrouwde lijstcriterium
* Procescreaties blokkeren die afkomstig zijn van OPDRACHTEN PSExec en WMI
* Het stelen van referenties blokkeren van het subsysteem van de windows-lokale beveiligingsautoriteit (lsass.exe)
* Win32 API-aanroepen blokkeren vanuit Office-macro's

## <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Onverenigbaarheid met Identity Secure Score en Graph API

In de recente release van Microsoft Secure Score is een verbeterd scoremodel uitgebracht. Deze wijzigingen zorgen voor een flexibeler en nauwkeuriger beeld van uw beveiligingshouding. Deze updates hebben Microsoft Secure Score echter tijdelijk onverenigbaar gemaakt met Identity Secure Score en de Graph API.

Na verloop van tijd zullen Identity Secure Score en de Graph API het nieuwe scoremodel aannemen. Tot die tijd zien klanten verschillen in de scores die worden gerapporteerd door Microsoft Secure Score, Identity Secure Score en de Graph API. Onze excuses voor het ongemak dat dit veroorzaakt, en werken om ervoor te zorgen dat deze ervaringen meer compatibel zijn in de toekomst.

## <a name="updated-improvement-actions"></a>Bijgewerkte verbeteringsacties

- Azure Active Directory-verbeteringsacties toegevoegd
- Azure Advanced Threat Protection-verbeteringsacties toegevoegd
- Ondersteuning voor microsoft Defender ATP [Threat & Beveiligingsaanbevelingen voor kwetsbaarheidsbeheer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
    - Alle vrijgegeven beveiligingsaanbevelingen geleverd door TVM zijn nu beschikbaar

## <a name="updated-interface-and-functionality"></a>Bijgewerkte interface en functionaliteit

* Alle nieuwe statistieken en trends weergaven voor CISO en lead level discussies
* Nieuwe manieren om je score bij te houden en te benchmarken
* Beter volgen en begrijpen voor scoreregressies
* Uw verbeteracties filteren, taggen, zoeken en groeperen
* Beheer richting uw toekomstige doelen met behulp van scoreprojecties en geplande acties
* En nog veel meer!

## <a name="we-want-to-hear-from-you"></a>We willen graag van u horen

Als je problemen hebt, laat het ons weten door een bericht te plaatsen in de [community Beveiliging, privacy & Compliance.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) We houden de gemeenschap in de gaten en zullen hulp bieden.

## <a name="related-resources"></a>Verwante informatiebronnen

- [Beoordeel uw beveiligingshouding](microsoft-secure-score-improvement-actions.md)
- [Uw Microsoft Secure Score-geschiedenis bijhouden en doelen bereiken](microsoft-secure-score-history-metrics-trends.md)
- [Binnenkort beschikbaar](microsoft-secure-score-whats-coming.md)
