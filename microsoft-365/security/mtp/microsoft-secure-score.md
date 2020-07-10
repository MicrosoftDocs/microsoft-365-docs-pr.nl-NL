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
ms.openlocfilehash: 212cefebfa3b4954f30d114419f82a5862e98a4f
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094796"
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

We laten u de volledige set van mogelijke verbeteringen zien, ongeacht de licentie, zodat u de best practices voor beveiliging begrijpen en uw score verbeteren. Uw absolute beveiligingshouding wordt vertegenwoordigd door Secure Score, dat hetzelfde blijft, ongeacht welk productlicentie uw organisatie bezit. Houd er rekening mee dat beveiliging moet worden afgewogen tegen bruikbaarheid, en niet elke aanbeveling kan werken voor uw omgeving.

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

## <a name="whats-new"></a>Wat is er nieuw? 

Om van Microsoft Secure Score een betere vertegenwoordiger van uw beveiligingshouding te maken, hebben we enkele wijzigingen aangebracht. Zie Wat komt er in Microsoft Secure Score voor meer informatie over geplande [wijzigingen?](microsoft-secure-score-whats-coming.md)

### <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Onverenigbaarheid met Identity Secure Score en Graph API

In de recente release van Microsoft Secure Score is een verbeterd scoremodel uitgebracht. Deze wijzigingen zorgen voor een flexibeler en nauwkeuriger beeld van uw beveiligingshouding. Deze updates hebben Microsoft Secure Score echter tijdelijk onverenigbaar gemaakt met Identity Secure Score en de Graph API.

Na verloop van tijd zullen Identity Secure Score en de Graph API het nieuwe scoremodel aannemen. Tot die tijd zien klanten verschillen in de scores die worden gerapporteerd door Microsoft Secure Score, Identity Secure Score en de Graph API. Onze excuses voor het ongemak dat dit veroorzaakt, en werken om ervoor te zorgen dat deze ervaringen meer compatibel zijn in de toekomst.

### <a name="updated-improvement-actions"></a>Bijgewerkte verbeteringsacties

- Azure Active Directory-verbeteringsacties toegevoegd
- Azure Advanced Threat Protection-verbeteringsacties toegevoegd
- Ondersteuning voor microsoft Defender ATP [Threat & Beveiligingsaanbevelingen voor kwetsbaarheidsbeheer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
    - Alle vrijgegeven beveiligingsaanbevelingen geleverd door TVM zijn nu beschikbaar

### <a name="updated-interface-and-functionality"></a>Bijgewerkte interface en functionaliteit

* Alle nieuwe statistieken en trends weergaven voor CISO en lead level discussies
* Nieuwe manieren om je score bij te houden en te benchmarken
* Beter volgen en begrijpen voor scoreregressies
* Uw verbeteracties filteren, taggen, zoeken en groeperen
* Beheer richting uw toekomstige doelen met behulp van scoreprojecties en geplande acties
* En nog veel meer!

### <a name="june-2020"></a>Juni 2020

#### <a name="removed-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Verwijderde verbeteringsactie voor Geavanceerde bedreigingsbeveiliging van Microsoft Defender

* Regels voor attack surface reduction inschakelen

#### <a name="added-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Verbeterde acties voor Microsoft Defender Advanced Threat Protection

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

## <a name="we-want-to-hear-from-you"></a>We willen graag van u horen

Als je problemen hebt, laat het ons weten door een bericht te plaatsen in de [community Beveiliging, privacy & Compliance.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) We houden de gemeenschap in de gaten en zullen hulp bieden.

## <a name="related-resources"></a>Verwante informatiebronnen

- [Krijg inzicht in uw beveiligingshouding](microsoft-secure-score-improvement-actions.md)
- [Uw Microsoft Secure Score-geschiedenis bijhouden en doelen bereiken](microsoft-secure-score-history-metrics-trends.md)
- [Binnenkort beschikbaar](microsoft-secure-score-whats-coming.md)
