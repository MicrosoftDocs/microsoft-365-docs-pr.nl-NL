---
title: Microsoft Secure Score
description: Beschrijft Microsoft Secure Score in het Microsoft 365-beveiligingscentrum, hoe u uw beveiligingshouding verbeteren en wat beveiligingsbeheerders kunnen verwachten.
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
ms.openlocfilehash: 862a25eddda6048349df937641914377cb25874f
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200036"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

Microsoft Secure Score is een meting van de beveiligingshouding van een organisatie, waarbij een hoger aantal aangeeft dat er meer verbeteringsacties worden ondernomen. Het kan worden gevonden op https://security.microsoft.com/securescore in de [Microsoft 365 security center](overview-security-center.md).

Als u de aanbevelingen voor de securescore volgt, u uw organisatie beschermen tegen bedreigingen. Vanuit een gecentraliseerd dashboard in het Microsoft 365-beveiligingscentrum kunnen organisaties de beveiliging van hun Microsoft 365-identiteiten, gegevens, apps, apparaten en infrastructuur bewaken en werken.

Secure Score helpt organisaties:  

* Rapporteer over de huidige status van de beveiligingshouding van de organisatie.
* Verbeter hun beveiligingshouding door vindbaarheid, zichtbaarheid, begeleiding en controle te bieden.  
* Vergelijk met benchmarks en stel key performance indicators (KPI's) vast.

Organisaties krijgen toegang tot robuuste visualisaties van statistieken en trends, integratie met andere Microsoft-producten, scorevergelijking met vergelijkbare organisaties en nog veel meer. De score kan ook reflecteren wanneer oplossingen van derden aanbevolen acties hebben aangepakt.

![Startpagina beveiligde score](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>Hoe het werkt

U krijgt punten voor het configureren van aanbevolen beveiligingsfuncties, het uitvoeren van beveiligingstaken of het aanpakken van de verbeteringsactie met een toepassing of software van derden, of een alternatieve beperking. Sommige verbeteringsacties geven alleen punten wanneer deze volledig zijn voltooid en sommige geven gedeeltelijke punten als ze voor sommige apparaten of gebruikers zijn voltooid. Als u een van de verbeteracties niet of wilt uitvoeren, u ervoor kiezen om het risico of het resterende risico te accepteren.

Als u een licentie hebt voor een van de ondersteunde Microsoft-producten, ziet u aanbevelingen voor deze producten. We laten u de volledige set mogelijke verbeteringen voor een product zien, ongeacht de licentie-editie, het abonnement of het abonnement, zodat u de best practices voor beveiliging begrijpen en uw score verbeteren. Uw absolute beveiligingshouding wordt vertegenwoordigd door Secure Score, dat hetzelfde blijft, ongeacht welke licenties uw organisatie bezit voor een specifiek product. Houd er rekening mee dat beveiliging moet worden afgewogen tegen bruikbaarheid, en niet elke aanbeveling kan werken voor uw omgeving.

Uw score wordt in realtime bijgewerkt om de informatie weer te geven die wordt weergegeven in de visualisaties en actiepagina's voor verbetering. Secure Score synchroniseert ook dagelijks om systeemgegevens te ontvangen over uw behaalde punten voor elke actie.

### <a name="key-scenarios"></a>Belangrijkste scenario's

- [Uw huidige score controleren](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Vergelijk uw score met organisaties als de uwe](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Verbeteracties bekijken en een actieplan bepalen](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Werkstromen initiëren om te onderzoeken of te implementeren](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [Microsoft 365-beveiligingscentrum en ServiceNow-integratie](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a>Hoe verbeteracties worden beoordeeld

Elke verbeteringsactie is 10 punten of minder waard. De meeste worden op een binaire manier gescoord - als u de verbeteringsactie implementeert, zoals het maken van een nieuw beleid of een specifieke instelling inschakelen, krijgt u 100% van de punten. Voor andere verbeteringsacties worden punten gegeven als een percentage van de totale configuratie. Bijvoorbeeld, als de verbetering actie staten krijg je 10 punten door het beschermen van al uw gebruikers met multi-factor authenticatie en je hebt slechts 50 van de 100 totale gebruikers beschermd, zou je een gedeeltelijke score van 5 punten (50 beschermd / 100 totaal * 10 max ptn = 5 pts gedeeltelijke score).

### <a name="products-included-in-secure-score"></a>Producten die zijn opgenomen in Secure Score

Momenteel zijn er aanbevelingen voor Microsoft 365 (inclusief Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP en Cloud App Security. Aanbevelingen voor andere beveiligingsproducten komen binnenkort. De aanbevelingen hebben niet betrekking op alle aanvalsoppervlakken die aan elk product zijn gekoppeld, maar ze zijn een goede basislijn. U de verbeteringsacties ook markeren als gedekt door een derde partij of alternatieve mitigatie.

### <a name="security-defaults"></a>Standaardinstellingen voor beveiliging

Microsoft Secure Score heeft [verbeteringsacties](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)bijgewerkt om beveiligingsstandaarden in Azure Active Directory te ondersteunen, waardoor het eenvoudiger wordt om uw organisatie te beschermen met vooraf geconfigureerde beveiligingsinstellingen voor veelvoorkomende aanvallen.

Als u beveiligingsstandaarden inschakelt, krijgt u volledige punten voor de volgende verbeteringsacties:

- Zorg ervoor dat alle gebruikers meervoudige verificatie kunnen voltooien voor beveiligde toegang (9 punten)
- MFA vereisen voor administratieve rollen (10 punten)
- Beleid inschakelen om verouderde verificatie te blokkeren (7 punten)

>[!IMPORTANT]
>Beveiligingsstandaarden bevatten beveiligingsfuncties die vergelijkbare beveiliging bieden als de verbeteringsacties 'aanmeldingsrisicobeleid' en 'gebruikersrisicobeleid'. In plaats van dit beleid naast de beveiligingsstandaarden in te stellen, raden we u aan hun statussen bij te werken naar 'Opgelost via alternatieve mitigatie'.

## <a name="required-permissions"></a>Vereiste machtigingen

Als u toestemming wilt hebben voor toegang tot Microsoft Secure Score, moet u een van de volgende rollen in Azure Active Directory toegewezen krijgen.

### <a name="read-and-write-roles"></a>Rollen lezen en schrijven

Met lees- en schrijftoegang u wijzigingen aanbrengen en direct communiceren met Secure Score. U ook alleen-lezen toegang toewijzen aan andere gebruikers.

* Globale beheerder
* Beveiligingsbeheerder
* Exchange-beheerder
* SharePoint-beheerder
* Accountbeheerder

### <a name="read-only-roles"></a>Alleen-lezen rollen

Met alleen-lezen toegang u geen status of notities bewerken voor een verbeteringsactie, scorezones bewerken of aangepaste vergelijkingen bewerken.

* Helpdeskbeheerder
* Gebruikersbeheerder
* Servicebeheerder
* Beveiligingslezer
* Beveiligingsoperator
* Algemene lezer

## <a name="risk-awareness"></a>Risicobewustzijn

Microsoft Secure Score is een numeriek overzicht van uw beveiligingshouding op basis van systeemconfiguraties, gebruikersgedrag en andere beveiligingsgerelateerde metingen; het is geen absolute meting van hoe waarschijnlijk uw systeem of gegevens zullen worden geschonden. Integendeel, het vertegenwoordigt de mate waarin u beveiligingscontroles hebt aangenomen in uw Microsoft-omgeving die kunnen helpen het risico van inbreuk te compenseren. Geen enkele online service is volledig immuun voor inbreuken op de beveiliging, en een veilige score mag niet worden geïnterpreteerd als een garantie tegen inbreuk op de beveiliging op enigerlei wijze.

## <a name="we-want-to-hear-from-you"></a>We willen graag van u horen

Als je problemen hebt, laat het ons weten door een bericht te plaatsen in de [community Beveiliging, privacy & Compliance.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) We houden de gemeenschap in de gaten en zullen hulp bieden.

## <a name="related-resources"></a>Verwante informatiebronnen

- [Beoordeel uw beveiligingshouding](microsoft-secure-score-improvement-actions.md)
- [Uw Microsoft Secure Score-geschiedenis bijhouden en doelen bereiken](microsoft-secure-score-history-metrics-trends.md)
- [Binnenkort beschikbaar](microsoft-secure-score-whats-coming.md)
- [Wat is er nieuw](microsoft-secure-score-whats-new.md)
