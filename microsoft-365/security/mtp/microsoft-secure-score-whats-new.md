---
title: Nieuw in Microsoft Secure Score
description: Hier wordt beschreven welke nieuwe wijzigingen zijn aangebracht in Microsoft Secure Score in het Microsoft 365-beveiligingscentrum.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft-beveiligingsscore, microsoft 365-beveiligingscentrum
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 520a5627d2cd280f28c4e2c3db0e565640a1eace
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289159"
---
# <a name="whats-new-in-microsoft-secure-score"></a>Nieuw in Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Om Microsoft Secure Score een beter beeld te geven van uw beveiligingsrisico, hebben we enkele wijzigingen aangebracht. Als u meer wilt weten over geplande wijzigingen, bekijkt u wat er [in Microsoft Secure Score komt?](microsoft-secure-score-whats-coming.md)

U vindt Microsoft Secure Score https://security.microsoft.com/securescore in het [Microsoft 365-beveiligingscentrum.](overview-security-center.md)
    
## <a name="february-2021"></a>Februari 2021

### <a name="compatibility-with-graph-api"></a>Compatibiliteit met Graph API

Aanbevelingen van Microsoft Secure Score die via Graph API worden geleverd, zien er hetzelfde uit en worden gewogen als de aanbevelingen die u momenteel in het Microsoft 365-beveiligingscentrum ziet.

## <a name="january-2021"></a>Januari 2021

### <a name="added-our-first-security-recommendation-for-microsoft-teams"></a>We hebben onze eerste beveiligingsaanbeveling voor Microsoft Teams toegevoegd

Klanten van Microsoft Teams zien 'Anonieme gebruikers beperken voor deelname aan vergaderingen' als een nieuwe actie ter verbetering van Secure Score.

## <a name="december-2020"></a>December 2020

### <a name="added-six-accounts-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Er zijn zes acties toegevoegd voor het verbeteren van accounts voor Microsoft Defender voor eindpunt (voorheen Microsoft Defender ATP):

- Stel 'Minimale wachtwoordlengte' in op '14 of meer tekens'
- Wachtwoordgeschiedenis afdwingen instellen op 24 of meer wachtwoorden
- Stel 'Maximale wachtwoordleeftijd' in op '60 of minder dagen, maar niet 0'
- Stel Minimale wachtwoordleeftijd in op '1 of meer dag(en)'
- Het ingebouwde Administrator-account uitschakelen
- Het ingebouwde Gastaccount uitschakelen

## <a name="november-2020"></a>November 2020

### <a name="removed-the-ability-to-create-servicenow-tickets-through-secure-score"></a>De mogelijkheid verwijderd om ServiceNow-tickets te maken via Secure Score 

De mogelijkheid om ServiceNow-tickets te maken via Secure Score door naar **> ServiceNow** te gaan, is niet meer beschikbaar. Bedankt voor uw feedback en verdere ondersteuning bij het bepalen van de volgende stappen.

### <a name="added-three-services-related-improvement-actions-for-microsoft-defender-for-endpoint-previously-microsoft-defender-atp"></a>Er zijn drie acties voor kwaliteitsverbetering voor Microsoft Defender voor eindpunt toegevoegd (voorheen Microsoft Defender ATP):

- Niet-aangeslagen servicepad voor Windows-services herstellen
- Uitvoerbaar pad van de service wijzigen naar een gemeenschappelijke beveiligde locatie
- Serviceaccount wijzigen om te voorkomen dat het wachtwoord in de cache wordt opgeslagen in het Windows-register

## <a name="october-2020"></a>Oktober 2020

### <a name="remove-improvement-action-related-to-microsoft-defender-for-endpoint"></a>Actie voor verbetering van Microsoft Defender voor eindpunt verwijderen

- Webinhoud controleren op Microsoft Defender SmartScreen-app instellen om te waarschuwen

## <a name="august-2020"></a>Augustus 2020

### <a name="updated-improvement-action-for-azure-active-directory"></a>Actie voor verbetering van Azure Active Directory bijgewerkt

- Beleid inschakelen om verouderde verificatie te blokkeren

## <a name="incompatibility-with-identity-secure-score"></a>Incompatibiliteit met Identity Secure Score

In de recente release van Microsoft Secure Score is een verbeterd scoremodel uitgebracht. Deze wijzigingen zorgen voor een flexibelere en nauwkeurige weergave van uw beveiligingsrisico. Dankzij deze updates is Microsoft Secure Score echter tijdelijk niet compatibel met Identity Secure Score.

Na een tijd zal Identity Secure Score het nieuwe scoremodel gaan gebruiken. Tot die tijd zien klanten verschillen in de scores die door Microsoft Secure Score en de Identity Secure Score zijn gerapporteerd. Onze excuses voor het ongemak, en we zorgen ervoor dat deze ervaringen in de toekomst compatibeler zijn.

## <a name="updated-improvement-actions"></a>Bijgewerkte acties voor kwaliteitsverbetering

- Acties voor verbetering van Azure Active Directory toegevoegd
- Acties voor verbetering van de identiteit van Microsoft Defender toegevoegd
- Ondersteuning voor Microsoft Defender for Endpoint [Threat & beveiligingsaanbevelingen voor](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) beveiligingsrisicobeheer
    - Alle uitgebrachte beveiligingsaanbevelingen die door TVM worden geleverd, zijn nu beschikbaar

## <a name="updated-interface-and-functionality"></a>Bijgewerkte interface en functionaliteit

* Alle nieuwe meetwaarden en trendsweergaven voor discussies op het SO en het niveau van het leiden
* Nieuwe manieren om uw score bij te houden en te vergelijken
* Beter bijhouden en begrijpen van score regressies
* Acties voor kwaliteitsverbetering filteren, taggen, zoeken en groeperen
* Beheer uw toekomstige doelstellingen met behulp van scoreprojecties en geplande acties
* En meer!

## <a name="we-want-to-hear-from-you"></a>Wij horen graag van u

Als u problemen hebt, laat het ons dan weten door berichten te plaatsen in de community over [beveiliging, & compliance.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) We houden de community in de gaten en bieden hulp.

## <a name="related-resources"></a>Verwante informatiebronnen

- [Uw beveiligingspositie vaststellen](microsoft-secure-score-improvement-actions.md)
- [Uw geschiedenis van Microsoft Secure Score bijhouden en doelstellingen behalen](microsoft-secure-score-history-metrics-trends.md)
- [Binnenkort beschikbaar](microsoft-secure-score-whats-coming.md)
