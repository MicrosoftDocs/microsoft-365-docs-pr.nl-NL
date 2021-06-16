---
title: Microsoft Secure Score
description: Beschrijft Microsoft Secure Score in het Microsoft 365 beveiligingscentrum, hoe u uw beveiligingsbeleid kunt verbeteren en wat beveiligingsbeheerders kunnen verwachten.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center, improvement actions
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: 1b03c2671939a3e8e3011b78b8f1484ef02979ea
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930185"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft Secure Score is een meting van de beveiligingsstatus van een organisatie, waarbij een hoger aantal aangeeft dat er meer verbeteracties zijn uitgevoerd. U vindt deze in https://security.microsoft.com/securescore het Microsoft 365 [beveiligingscentrum.](overview-security-center.md)

Als u de aanbevelingen voor secure score volgt, kunt u uw organisatie beschermen tegen bedreigingen. Vanuit een gecentraliseerd dashboard in Microsoft 365 beveiligingscentrum kunnen organisaties de beveiliging van hun Microsoft 365 identiteiten, apps en apparaten controleren en er aan werken.

Secure Score helpt organisaties:  

* Rapport over de huidige status van de beveiligingsstatus van de organisatie.
* Verbeter hun beveiligingshouding door vindbaarheid, zichtbaarheid, richtlijnen en controle te bieden.  
* Vergelijk dit met benchmarks en stel KPI's (Key Performance Indicators) vast.

Organisaties krijgen toegang tot krachtige visualisaties van meetgegevens en trends, integratie met andere Microsoft-producten, scorevergelijking met vergelijkbare organisaties en nog veel meer. De score kan ook worden weergegeven wanneer oplossingen van derden aanbevolen acties hebben aangepakt.

![Startpagina van Secure Score](../../media/secure-score/secure-score-home-page.png)

## <a name="how-it-works"></a>Hoe het werkt

U krijgt punten voor de volgende acties:

- Aanbevolen beveiligingsfuncties configureren
- Beveiligingsgerelateerde taken uitvoeren
- De verbeteringsactie aanpakken met een toepassing of software van derden, of een alternatieve beperking

Sommige verbeteracties geven alleen punten wanneer ze volledig zijn voltooid. Sommige geven gedeeltelijke punten als ze zijn voltooid voor sommige apparaten of gebruikers. Als u een van de verbeteracties niet of niet wilt uitvoeren, kunt u ervoor kiezen om het risico of het resterende risico te accepteren.

Als u een licentie hebt voor een van de ondersteunde Microsoft-producten, ziet u aanbevelingen voor deze producten. We tonen u de volledige reeks mogelijke verbeteringen voor een product, ongeacht de licentieeditie, het abonnement of het abonnement. Op deze manier kunt u de best practices voor beveiliging begrijpen en uw score verbeteren. Uw absolute beveiligingsstatus, vertegenwoordigd door Secure Score, blijft hetzelfde, ongeacht welke licenties uw organisatie bezit voor een bepaald product. Houd er rekening mee dat beveiliging in balans moet zijn met bruikbaarheid en dat niet elke aanbeveling kan werken voor uw omgeving.

Uw score wordt in realtime bijgewerkt om de informatie weer te geven die wordt weergegeven op de actiepagina's visualisaties en verbetering. Secure Score wordt ook dagelijks gesynchroniseerd om systeemgegevens over uw behaalde punten voor elke actie te ontvangen.

### <a name="key-scenarios"></a>Belangrijke scenario's

- [Uw huidige score controleren](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Uw score vergelijken met organisaties zoals die van u](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Verbeteracties bekijken en een actieplan bepalen](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Werkstromen starten om te onderzoeken of te implementeren](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a>Hoe verbeteracties worden gescored

Elke verbeteringsactie is 10 punten of minder waard en de meeste worden op een binaire manier gescored. Als u de verbeteringsactie implementeert, zoals een nieuw beleid maken of een specifieke instelling in te stellen, krijgt u 100% van de punten. Voor andere verbeteracties worden punten gegeven als een percentage van de totale configuratie.

Een verbeteringsactie geeft bijvoorbeeld aan dat u 10 punten krijgt door al uw gebruikers te beschermen met meervoudige verificatie. U hebt slechts 50 van de 100 totale gebruikers beveiligd, dus u krijgt een gedeeltelijke score van 5 punten (50 beveiligde / 100 totaal * 10 max pts = 5 pts).

### <a name="products-included-in-secure-score"></a>Producten die zijn opgenomen in Secure Score

Momenteel zijn er aanbevelingen voor de volgende producten:

- Microsoft 365 (inclusief Exchange Online)
- Microsoft Azure Active Directory
- Microsoft Defender voor Eindpunt
- Microsoft Defender for Identity
- Cloud App Security
- Microsoft Teams

Aanbevelingen voor andere beveiligingsproducten zijn binnenkort beschikbaar. De aanbevelingen hebben niet betrekking op alle aanvalsoppervlakken die aan elk product zijn gekoppeld, maar ze zijn wel een goede basislijn. U kunt de verbeteracties ook markeren als gedekt door een derde partij of alternatieve mitigatie.

### <a name="security-defaults"></a>Standaardinstellingen voor beveiliging

Microsoft Secure Score heeft verbeteracties bijgewerkt ter ondersteuning van beveiligingsinstellingen [in Azure Active Directory,](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)waardoor u uw organisatie gemakkelijker kunt beschermen met vooraf geconfigureerde beveiligingsinstellingen voor veelvoorkomende aanvallen.

Als u beveiligings defaults in ingeschakeld, krijgt u volledige punten voor de volgende verbeteringsacties:

- Zorg ervoor dat alle gebruikers meervoudige verificatie kunnen voltooien voor veilige toegang (9 punten)
- MFA vereisen voor beheerdersrollen (10 punten)
- Beleid inschakelen om oudere verificatie te blokkeren (7 punten)

>[!IMPORTANT]
>Beveiligings defaults omvatten beveiligingsfuncties die vergelijkbare beveiliging bieden als het 'aanmeldingsbeleid' en 'user risk policy' verbeteracties. In plaats van dit beleid in te stellen boven op de beveiligings defaults, raden we aan hun statussen bij te werken naar 'Opgelost via alternatieve beperking'.

## <a name="required-permissions"></a>Vereiste machtigingen

Als u toestemming wilt hebben voor toegang tot Microsoft Secure Score, moet u een van de volgende rollen in de Azure Active Directory.

### <a name="read-and-write-roles"></a>Rollen lezen en schrijven

Met lees- en schrijftoegang kunt u wijzigingen aanbrengen en rechtstreeks werken met Secure Score. U kunt ook alleen-lezen toegang toewijzen aan andere gebruikers.

* Globale beheerder
* Beveiligingsbeheerder
* Exchange-beheerder
* SharePoint-beheerder

### <a name="read-only-roles"></a>Alleen-lezen rollen

Met alleen-lezen toegang kunt u de status of notities niet bewerken voor een verbeteringsactie, scorezones bewerken of aangepaste vergelijkingen bewerken.

* Helpdeskbeheerder
* Gebruikersbeheerder
* Serviceondersteuningsbeheerder
* Beveiligingslezer
* Beveiligingsoperator
* Algemene lezer

## <a name="risk-awareness"></a>Risicobewustzijn

Microsoft Secure Score is een numerieke samenvatting van uw beveiligingsstatus op basis van systeemconfiguraties, gebruikersgedrag en andere beveiligingsgerelateerde metingen. Het is geen absolute meting van de kans dat uw systeem of gegevens worden geschonden. In plaats van de mate waarin u beveiligingsbesturingselementen hebt aangenomen in uw Microsoft-omgeving, kan dit helpen het risico op inbreuken te compenseren. Geen enkele onlineservice is niet gevrijwaard van beveiligingsinbreuken en een veilige score mag niet worden geïnterpreteerd als een garantie tegen inbreuk op de beveiliging op welke manier dan ook.

## <a name="we-want-to-hear-from-you"></a>Wij horen graag van u

Als u problemen hebt, laat het ons weten door een bericht te plaatsen in de [beveiligings-, privacy- & Compliance-community.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) We houden de community in de gaten en bieden hulp.

## <a name="related-resources"></a>Verwante informatiebronnen

- [Uw beveiligingspositie vaststellen](microsoft-secure-score-improvement-actions.md)
- [Uw Microsoft Secure Score-geschiedenis bijhouden en doelstellingen behalen](microsoft-secure-score-history-metrics-trends.md)
- [Binnenkort beschikbaar](microsoft-secure-score-whats-coming.md)
- [Wat is er nieuw](microsoft-secure-score-whats-new.md)
