---
title: Microsoft Secure Score
description: Beschrijft Microsoft Secure Score in het Microsoft 365-beveiligingscentrum, hoe u het beveiligingsbeleid verbetert en wat beveiligingsbeheerders kunnen verwachten.
keywords: microsoft secure score, secure score, office 365 secure score, microsoft-beveiligingsscore, Microsoft 365-beveiligingscentrum, acties voor verbetering
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
ms.openlocfilehash: a0f4307cc0ed42a8ed53cdeefdb0a7b32eb36d35
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930580"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft Secure Score is een meting van de beveiligingsrisico's van een organisatie, met een hoger getal dat aangeeft dat er meer acties zijn ondernomen. U vindt deze in https://security.microsoft.com/securescore het [Microsoft 365-beveiligingscentrum.](overview-security-center.md)

Als u de aanbevelingen van Secure Score volgt, kunt u uw organisatie beschermen tegen bedreigingen. Vanuit een centraal dashboard in het Microsoft 365-beveiligingscentrum kunnen organisaties de beveiliging van hun Microsoft 365-identiteiten, -apps en -apparaten controleren en er aan werken.

Secure Score helpt organisaties met het volgende:  

* Rapporteer over de huidige status van de beveiligingsrisico's van de organisatie.
* Verbeter de beveiligingsmogelijkheden door zichtbaarheid, zichtbaarheid, begeleiding en controle te bieden.  
* Vergelijk met benchmarks en stel KPI's (Key Performance Indicators) op.

Organisaties krijgen toegang tot krachtige visualisaties van meetwaarden en trends, integratie met andere Microsoft-producten, scorevergelijking met vergelijkbare organisaties en nog veel meer. De score kan ook worden weergegeven wanneer aanbevolen acties door externe oplossingen zijn aangepakt.

![Secure Score-startpagina](../../media/secure-score/secure-score-homepage-new.png)

## <a name="how-it-works"></a>Hoe het werkt

U krijgt punten voor de volgende acties:

- Aanbevolen beveiligingsfuncties configureren
- Beveiligingstaken uitvoeren
- Het aanpakken van de actie voor verbetering met een toepassing of software van derden, of een alternatieve risicobeperking

Sommige acties voor kwaliteitsverbetering geven alleen punten wanneer ze volledig zijn voltooid. Sommige geven gedeeltelijke punten als ze zijn voltooid voor sommige apparaten of gebruikers. Als u een van de acties ter verbetering niet of niet wilt uitvoeren, kunt u ervoor kiezen het risico of het resterende risico te accepteren.

Als u een licentie hebt voor een van de ondersteunde Microsoft-producten, ziet u aanbevelingen voor deze producten. U ziet alle mogelijke verbeteringen voor een product, ongeacht de licentie-versie, het abonnement of het abonnement. Op deze manier begrijpt u de beste beveiligingsprocedures en verbetert u uw score. Uw absolute beveiligingsrisico, vertegenwoordigd door Secure Score, blijft hetzelfde, ongeacht de licenties die uw organisatie bezit voor een specifiek product. Houd er rekening mee dat beveiliging moet worden gebalanceerd met bruikbaarheid en dat niet elke aanbeveling voor uw omgeving kan werken.

Uw score wordt in realtime bijgewerkt om de informatie weer te geven die wordt weergegeven op de visualisaties en actiepagina's voor verbetering. Secure Score synchroniseert ook dagelijks met systeemgegevens over uw bereikt punten voor elke actie.

### <a name="key-scenarios"></a>Belangrijke scenario's

- [Uw huidige score controleren](microsoft-secure-score-improvement-actions.md#check-your-current-score)
- [Vergelijk uw score met organisaties zoals die van u](microsoft-secure-score-history-metrics-trends.md#compare-your-score-to-organizations-like-yours)
- [Acties voor verbetering weergeven en een plan van aanpak bepalen](microsoft-secure-score-improvement-actions.md#take-action-to-improve-your-score)
- [Werkstromen starten om dit te onderzoeken of te implementeren](microsoft-secure-score-improvement-actions.md#view-improvement-action-details)

### <a name="how-improvement-actions-are-scored"></a>Hoe acties voor kwaliteitsverbetering worden gescored

Elke verbeteringsactie is 10 punten of minder waard en de meeste worden op binaire wijze als scorescores genomen. Als u de actie voor verbetering implementeert, zoals een nieuw beleid maken of een specifieke instelling in schakelt, krijgt u 100% van de punten. Voor andere acties ter verbetering worden punten gegeven als een percentage van de totale configuratie.

Met een actie ter verbetering krijgt u bijvoorbeeld 10 punten door alle gebruikers te beschermen met meervoudige verificatie. U hebt in totaal slechts 50 van de 100 gebruikers beveiligd, dus krijgt u een gedeeltelijke score van 5 punten (50 beveiligde / 100 totaal * 10 max pts = 5 pts).

### <a name="products-included-in-secure-score"></a>Producten die zijn opgenomen in Secure Score

Momenteel zijn er aanbevelingen voor de volgende producten:

- Microsoft 365 (inclusief Exchange Online)
- Microsoft Azure Active Directory
- Microsoft Defender for Endpoint
- Microsoft Defender for Identity
- Cloud App Security

Aanbevelingen voor andere beveiligingsproducten komen binnenkort beschikbaar. De aanbevelingen hebben niet betrekking op alle aanvallen die aan elk product zijn gekoppeld, maar ze zijn wel een goede basislijn. U kunt de acties voor kwaliteitsverbetering ook markeren als gedekt door een derde partij of een alternatieve risicobeperking.

### <a name="security-defaults"></a>Standaardinstellingen voor beveiliging

Microsoft Secure Score heeft acties ter verbetering bijgewerkt ter ondersteuning van beveiligingsinstellingen [in Azure Active Directory,](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)waarmee het gemakkelijker wordt om uw organisatie te beschermen met vooraf geconfigureerde beveiligingsinstellingen voor algemene aanvallen.

Als u beveiligingsinstellingen in ingeschakeld, krijgt u volledige punten voor de volgende acties ter verbetering:

- Controleren of alle gebruikers meervoudige verificatie kunnen voltooien voor beveiligde toegang (9 punten)
- MFA vereisen voor beheerdersrollen (10 punten)
- Beleid inschakelen om verouderde verificatie te blokkeren (7 punten)

>[!IMPORTANT]
>Beveiligingsfuncties bevatten beveiligingsfuncties die vergelijkbaar zijn met de acties voor het 'aanmeldingsrisicobeleid' en 'gebruikersrisicobeleid'. In plaats van dit beleid boven op de beveiligingsinstellingen in te stellen, raden we u aan hun status bij te werken naar 'Opgelost door alternatieve risicobeperking'.

## <a name="required-permissions"></a>Vereiste machtigingen

Als u toegang wilt krijgen tot Microsoft Secure Score, moet u een van de volgende rollen in Azure Active Directory toegewezen krijgen.

### <a name="read-and-write-roles"></a>Rollen lezen en schrijven

Met lees- en schrijftoegang kunt u wijzigingen aanbrengen en rechtstreeks communiceren met Secure Score. U kunt ook alleen-lezentoegang toewijzen aan andere gebruikers.

* Globale beheerder
* Beveiligingsbeheerder
* Exchange-beheerder
* SharePoint-beheerder
* Accountbeheerder

### <a name="read-only-roles"></a>Alleen-lezen rollen

Met alleen-lezen toegang kunt u geen status of notities bewerken voor een verbeteringsactie, scorezones bewerken of aangepaste vergelijkingen bewerken.

* Helpdeskbeheerder
* Gebruikersbeheerder
* Servicebeheerder
* Beveiligingslezer
* Beveiligingsoperator
* Algemene lezer

## <a name="risk-awareness"></a>Risico-bekendheid

Microsoft Secure Score is een numeriek overzicht van uw beveiligingsrisico op basis van systeemconfiguraties, gebruikersgedrag en andere beveiligingsgerelateerde afmetingen. Het is geen absolute maateenheid voor de kans dat uw systeem of gegevens worden geschonden. Het vertegenwoordigt in plaats van de mate waarin u beveiligingscontroles hebt overgenomen in uw Microsoft-omgeving, waardoor het risico op inbreuk kan worden verschoven. Er is geen online service die te maken heeft met beveiligingsinbreuken en secure score mag niet worden geïnterpreteerd als een garantie tegen inbreuk op de beveiliging op welke manier dan ook.

## <a name="we-want-to-hear-from-you"></a>Wij horen graag van u

Als u problemen hebt, laat het ons dan weten door berichten te plaatsen in de community [over beveiliging, & compliance.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) We houden de community in de gaten en bieden hulp.

## <a name="related-resources"></a>Verwante informatiebronnen

- [Uw beveiligingspositie vaststellen](microsoft-secure-score-improvement-actions.md)
- [Uw geschiedenis van Microsoft Secure Score bijhouden en doelstellingen behalen](microsoft-secure-score-history-metrics-trends.md)
- [Binnenkort beschikbaar](microsoft-secure-score-whats-coming.md)
- [Wat is er nieuw](microsoft-secure-score-whats-new.md)
