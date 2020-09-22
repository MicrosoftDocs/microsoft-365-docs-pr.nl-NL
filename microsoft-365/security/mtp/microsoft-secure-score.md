---
title: Microsoft Secure Score
description: Beschrijving van Microsoft Secure Score in het Microsoft 365-Beveiligingscentrum, hoe u uw beveiligings Posture kunt verbeteren en welke beveiligingsbeheerders kunnen verwachten.
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
ms.openlocfilehash: b378288637baa5b51f74fb63d8c8da33ac5e148f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196189"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Secure Score van Microsoft is een afmeting van de beveiligings Posture van een organisatie, met een hoger nummer voor het uitvoeren van extra verbeterings acties. U vindt het https://security.microsoft.com/securescore in [microsoft 365 Beveiligingscentrum](overview-security-center.md).

Door de aanbevelingen van de Secure score te volgen, kunt u uw organisatie beschermen tegen bedreigingen. Vanuit een gecentraliseerd dashboard in het Microsoft 365-Beveiligingscentrum kunnen organisaties de beveiliging van hun identiteit, gegevens, apps, apparaten en infrastructuur van Microsoft 365 volgen en gebruiken.

Secure Score helpt organisaties:  

* Rapport over de huidige status van de beveiligings Posture van de organisatie.
* Verbeter hun beveiliging Posture door te zorgen voor detectie, inzicht, richtlijnen en beheer.  
* Vergelijken met benchenen en Key Performance Indicators (Kpi's) instellen.

Organisaties hebben toegang tot krachtige visualisaties van metrische gegevens en trends, integratie met andere Microsoft-producten, vergelijking van Score overeenkomsten met vergelijkbare organisaties en nog veel meer. De score kan ook worden weergegeven wanneer oplossingen van derden een aanbevolen actie hebben aangegaan.

![Startpagina beveiligde Score](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>Hoe het werkt

U krijgt punten voor de volgende acties:

- Aanbevolen beveiligingsfuncties configureren
- Beveiligingstaken uitvoeren
- De actie voor verbetering met een toepassing of software van derden of een afwisselend beperking

Bij sommige verbeterings acties worden alleen punten gegeven wanneer u klaar bent. Sommige bieden gedeeltelijke punten als ze voor sommige apparaten of gebruikers zijn voltooid. Als u een van de verbeterings acties niet of niet wilt aannemen, kunt u het risico of het resterende risico accepteren.

Als u een licentie hebt voor een van de ondersteunde Microsoft-producten, ziet u aanbevelingen voor die producten. We laten u de volledige set mogelijke verbeteringen voor een product tonen, ongeacht of u licentie-editie, abonnement of abonnement hebt. Op deze manier kunt u de aanbevolen procedures voor beveiliging en de Score verhogen. Uw absolute beveiligings Posture, weergegeven door een veilige Score, blijft gelijk, ongeacht welke licenties uw organisatie bezit voor een specifiek product. Houd er rekening mee dat beveiliging moet worden verantwoord met behulp van bruikbaarheid, en niet elk aanbeveling kan werken met uw omgeving.

Uw score wordt in realtime bijgewerkt om de informatie weer te geven die wordt weergegeven in de actie pagina's voor visualisaties en verbetering. Met Secure score wordt ook dagelijks een synchronisatie uitgevoerd voor het ontvangen van systeemgegevens over de bereikte punten voor elke actie.

### <a name="key-scenarios"></a>Belangrijke scenario's

- [De huidige Score controleren](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Uw score vergelijken met organisaties zoals u](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Verbeterings acties weergeven en een actieplan kiezen](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Een werkstroom initiëren om te onderzoeken of te implementeren](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)
    - [Microsoft 365 Beveiligingscentrum en ServiceNow-integratie](tickets-security-center.md)

### <a name="how-improvement-actions-are-scored"></a>Hoe verbeterings acties worden beoordeeld

Elke vergelijkings actie is 10 punten of minder, en de meeste wordt op een binaire manier gescoord. Als u de actie voor verbetering implementeert, zoals een nieuw beleid maken of een bepaalde instelling inschakelt, ontvangt u 100% van de punten. Voor andere verbeterings acties worden de punten uitgedrukt als percentage van de totale configuratie.

Met een verbeterings actie wordt u bijvoorbeeld 10 punten vrijmaken door al uw gebruikers te beschermen met meervoudige verificatie. U hebt maar 50 van 100 totale gebruikers, dus u krijgt een deel van 5 punten met een uitgaand bedrag (50/100 totale * 10 Max pts = 5 pts).

### <a name="products-included-in-secure-score"></a>Producten die deel uitmaken van Secure Score

Er zijn momenteel aanbevelingen voor Microsoft 365 (waaronder Exchange Online), Azure Active Directory, Microsoft Defender ATP, Azure ATP en beveiliging van Cloud apps. Aanbevelingen voor andere beveiligingsproducten zijn binnenkort beschikbaar. De aanbevelingen bedekken geen enkele aanvals vlakken die zijn gekoppeld aan elk product, maar ze zijn een goede basislijn. U kunt ook de verduidelijkings acties markeren als bedoeld bij een derde persoon of een andere beperking.

### <a name="security-defaults"></a>Standaardinstellingen voor beveiliging

Secure Score van Microsoft heeft bijgewerkte stappen voor het oplossen van [beveiligingsstandaarden in azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), zodat u uw organisatie eenvoudiger kunt beschermen met vooraf geconfigureerde beveiligingsinstellingen voor algemene aanvallen.

Als u de standaardwaarden voor beveiliging uitschakelt, ontvangt u volledige punten voor de volgende verbeterings acties:

- Ervoor zorgen dat alle gebruikers meervoudige verificatie kunnen uitvoeren voor beveiligde toegang (9 punten)
- MFA vereisen voor beheerdersrollen (10 punten)
- Beleid inschakelen voor het blokkeren van oudere verificatie (7 punten)

>[!IMPORTANT]
>Beveiligingsinstellingen omvatten beveiligingsfuncties die soortgelijke beveiliging biedt voor de verbeteringen van het aanmeldings risico en de verbeteringen van gebruikers risico beleid. In plaats van deze beleidsregels boven de standaardinstellingen voor de beveiliging in te stellen, wordt u aangeraden hun status bij te werken met een afwijkende beperking.

## <a name="required-permissions"></a>Vereiste machtigingen

Als u gemachtigd bent om toegang te krijgen tot Microsoft Secure Score, moet u beschikken over een van de volgende rollen in azure Active Directory.

### <a name="read-and-write-roles"></a>Rollen lezen en schrijven

Met lees-en schrijftoegang kunt u wijzigingen aanbrengen en rechtstreeks werken met Secure Score. U kunt ook alleen-lezen toegang toewijzen aan andere gebruikers.

* Globale beheerder
* Beveiligingsbeheerder
* Exchange-beheerder
* SharePoint-beheerder
* Account beheerder

### <a name="read-only-roles"></a>Alleen-lezen rollen

Met alleen-lezen toegang kunt u niet de status of notities voor een actie voor verbetering bewerken, Score zones bewerken of aangepaste vergelijkingen bewerken.

* Helpdesk beheerder
* Gebruikersbeheerder
* Service beheerder
* Beveiligingslezer
* Beveiligingsoperator
* Algemene lezer

## <a name="risk-awareness"></a>Risico detectie

Secure Score van Microsoft is een numerieke samenvatting van uw beveiligings Posture op basis van systeemconfiguraties, gebruikersgedrag en andere beveiligings maten. Het maakt niet uit hoe waarschijnlijk uw systeem of gegevens worden geschonden. In plaats daarvan wordt aangegeven in welke mate u beveiligings besturing in uw Microsoft-omgeving hebt aangenomen waarmee u het risico van schending kunt compenseren. Geen enkele online dienst is volledig gekraakt tegen beveiligingsproblemen en de Secure Score mag niet worden geïnterpreteerd als garantie tegen schending van de beveiliging.

## <a name="we-want-to-hear-from-you"></a>We horen graag van u

Als u problemen ondervindt, kunt u het ons laten weten dat u de community [beveiliging, Privacy & naleving](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) . We volgen de community en bieden hulp.

## <a name="related-resources"></a>Verwante informatiebronnen

- [Uw beveiligingspositie vaststellen](microsoft-secure-score-improvement-actions.md)
- [De geschiedenis van uw Microsoft Secure Score bijhouden en bereiken](microsoft-secure-score-history-metrics-trends.md)
- [Binnenkort beschikbaar](microsoft-secure-score-whats-coming.md)
- [Wat is er nieuw](microsoft-secure-score-whats-new.md)
