---
title: Microsoft Secure Score (voorbeeld)
description: Beschrijft de Microsoft Secure Score in het Microsoft 365-beveiligingscentrum, hoe details worden berekend en wat beveiligingsbeheerders kunnen verwachten.
keywords: beveiliging, malware, Microsoft 365, M365, beveiligde score, beveiligingscentrum, verbeteringsacties
ms.prod: w10
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
ms.openlocfilehash: 8277549c683da19dbbf915a7cf673fc731cb8803
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141413"
---
# <a name="microsoft-secure-score-preview"></a>Microsoft Secure Score (voorbeeld)

>[!IMPORTANT]
>Sommige informatie heeft betrekking op vooraf uitgebrachte product dat aanzienlijk kan worden gewijzigd voordat het commercieel wordt vrijgegeven. Microsoft doet geen garanties, uitdrukkelijk of impliciet, met betrekking tot de hier verstrekte informatie.

Microsoft Secure Score is een meting van de beveiligingshouding van een organisatie, met een hoger aantal dat aangeeft dat er meer verbeteracties zijn uitgevoerd. Het kan worden https://security.microsoft.com/securescore gevonden op in de [Microsoft 365 security center](overview-security-center.md).

Het volgen van de aanbevelingen voor beveiligingsscore kan uw organisatie beschermen tegen bedreigingen. Vanuit een gecentraliseerd dashboard in het Microsoft 365-beveiligingscentrum kunnen organisaties de beveiliging van hun Microsoft 365-identiteiten, gegevens, apps, apparaten en infrastructuur bewaken en eraan werken.

Secure Score helpt organisaties:  

* Rapport over de huidige status van de beveiligingshouding van de organisatie.
* Verbeter hun beveiligingshouding door vindbaarheid, zichtbaarheid, begeleiding en controle te bieden.  
* Vergelijk met benchmarks en stel key performance indicators (KPI's) vast.

Organisaties krijgen toegang tot robuuste visualisaties van statistieken en trends, integratie met andere Microsoft-producten, scorevergelijking met vergelijkbare organisaties en nog veel meer. De score kan ook worden weergegeven wanneer oplossingen van derden aanbevolen acties hebben aangepakt.

Bovendien u toegang krijgen tot uw aanbevelingen en score via de [Microsoft Graph API.](https://www.microsoft.com/security/partnerships/graph-security-api) Meer informatie over het [resourcetype Beveiligde score](https://go.microsoft.com/fwlink/?linkid=2092996).

## <a name="how-it-works"></a>Hoe het werkt

U krijgt punten voor het configureren van aanbevolen beveiligingsfuncties, het uitvoeren van beveiligingsgerelateerde taken of het aanpakken van de verbeteringsactie met een toepassing of software van derden. Sommige verbeteringsacties geven alleen punten wanneer ze volledig zijn voltooid, en sommige geven gedeeltelijke punten als ze zijn voltooid voor sommige apparaten of gebruikers. Als u een van de verbeteracties niet of wilt uitvoeren, u ervoor kiezen om het risico of het resterende risico te accepteren.

We laten u de volledige set mogelijke verbeteringen zien, ongeacht de licentie, zodat u de beste beveiligingsprocedures begrijpen en uw score verbeteren. Uw absolute beveiligingshouding wordt vertegenwoordigd door Secure Score, die hetzelfde blijft, ongeacht de productlicenties die uw organisatie bezit. Houd er rekening mee dat beveiliging moet worden afgewogen tegen bruikbaarheid, en niet elke aanbeveling kan werken voor uw omgeving.

Uw score wordt in realtime bijgewerkt om de informatie weer te geven die wordt gepresenteerd in de actiepagina's voor visualisaties en verbeteringen. Secure Score synchroniseert ook dagelijks om systeemgegevens over uw behaalde punten voor elke actie te ontvangen.

### <a name="how-improvement-actions-are-scored"></a>Hoe verbeteracties worden beoordeeld

Elke verbeteringsactie is 10 punten of minder waard. De meeste worden op een binaire manier gescoord - als u de verbeteringsactie implementeert, zoals een nieuw beleid maken of een specifieke instelling inschakelen, krijgt u 100% van de punten. Voor andere verbeteringsacties worden punten gegeven als percentage van de totale configuratie. Bijvoorbeeld, als de verbetering actie staat krijg je 30 punten door het beschermen van al uw gebruikers met multi-factor authenticatie en je hebt slechts 5 van de 100 totale gebruikers beschermd, zou je een gedeeltelijke score van ongeveer 2 punten (5 beschermd / 100 totaal * 30 max pts = 2 pts partiële score).

### <a name="products-included-in-secure-score"></a>Producten opgenomen in Secure Score

Momenteel zijn er aanbevelingen voor Microsoft 365 (waaronder Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP en Cloud App Security. Aanbevelingen voor andere beveiligingsproducten komen binnenkort. De aanbevelingen hebben niet betrekking op alle aanvalsoppervlakken die aan elk product zijn gekoppeld, maar ze zijn een goede basislijn. U de verbeteringsacties ook markeren als gedekt door een derde partij.

## <a name="required-permissions"></a>Vereiste machtigingen

Als u toestemming wilt hebben om toegang te krijgen tot Microsoft Secure Score, moet u een van de volgende rollen in Azure Active Directory toegewezen krijgen.

### <a name="read-and-write-roles"></a>Rollen lezen en schrijven

Met lees- en schrijftoegang u wijzigingen aanbrengen en rechtstreeks communiceren met Secure Score. U ook alleen-lezen toegang toewijzen aan andere gebruikers.

* Globale beheerder
* Beveiligingsbeheerder
* Exchange-beheerder
* SharePoint-beheerder
* Accountbeheerder

### <a name="read-only-roles"></a>Alleen-lezen rollen

Met alleen-lezen toegang u de status of notities niet bewerken voor een verbeteringsactie, scorezones bewerken of aangepaste vergelijkingen bewerken.

* Helpdeskbeheerder
* Gebruikersbeheerder
* Servicebeheerder
* Beveiligingslezer
* Beveiligingsoperator
* Algemene lezer

### <a name="graph-api"></a>Grafische API

Als u toegang wilt krijgen tot de Graph API, moet u naast een rol ook een van de volgende scopes hebben:

* SecurityEvents.Read.All (voor alleen-lezen rollen)
* SecurityEvents.ReadWrite.All (voor lees- en schrijfrollen)

## <a name="gain-visibility-into-your-security-posture"></a>Krijg inzicht in uw beveiligingshouding

Om u te helpen sneller de informatie te verzamelen die u nodig hebt, worden microsoft-verbeteringsacties in groepen georganiseerd:

* Identiteit (Azure AD-accounts & rollen)
* Gegevens (Microsoft-informatiebeveiliging)
* Apparaat (Microsoft Defender ATP)
* App (e-mail- en cloud-apps, waaronder Office 365 en Microsoft Cloud App Security)
* Infrastructuur (voorlopig geen verbeteracties)

Op de overzichtspagina van Microsoft Secure Score u zien hoe punten worden verdeeld over deze groepen en welke punten beschikbaar zijn. De overzichtspagina is ook de plek om een totaalbeeld te krijgen van de totale score, historische trend van uw beveiligde score met benchmarkvergelijkingen en geprioritteerde verbeteringsacties die kunnen worden ondernomen om uw score te verbeteren.

![Overzichtspagina](../../media/secure-score/secure-score-homepage.png)
van de beveiligde score*homepage figuur 1: Microsoft Secure Score*

## <a name="take-action-to-improve-your-score"></a>Onderneem actie om je score te verbeteren

Op het tabblad **Verbeteringsacties** worden de beveiligingsaanbevelingen weergegeven die mogelijke aanvalsoppervlakken aanpakken, samen met hun status (om aan te pakken, gepland, risico's geaccepteerd, opgelost door derden, opgelost door alternatieve beperking en voltooid). U alle verbeteringsacties zoeken, filteren en groeperen.  

### <a name="ranking"></a>Ranking

Ranking is gebaseerd op het aantal resterende punten te bereiken, implementatie moeilijkheid, impact van de gebruiker, en complexiteit. De hoogst gerangschikte verbeteringsacties hebben een groot aantal resterende punten met lage moeilijkheidsgraad, impact van de gebruiker en complexiteit.

### <a name="view-improvement-action-details"></a>Details van de verbeteringsactie weergeven

Wanneer u een specifieke verbeteringsactie selecteert, wordt een flyout van de volledige pagina weergegeven.  

![Voorbeeld van voorbeeld](../../media/secure-score/secure-score-improvement-action-details.png)
van de flyout van de verbeteringsactie*Figuur 2: Voorbeeld van de actie van de verbetering*

Als u de actie wilt voltooien, hebt u een aantal opties:

* Selecteer **Beheren** om naar het configuratiescherm te gaan en de wijziging aan te brengen. U krijgt dan de punten die de actie waard is, zichtbaar in de fly out. Punten duren over het algemeen ongeveer 24 uur om bij te werken.

* Selecteer **Delen** om de directe koppeling naar de verbeteringsactie te kopiëren of kies het platform om de koppeling te delen, zoals e-mail, Microsoft Teams, Microsoft Planner of ServiceNow. Als u ServiceNow selecteert, u een wijzigingsticket maken dat zichtbaar is in ServiceNow en het microsoft 365-beveiligingscentrum thuis. Zie [Microsoft 365 Security Center en ServiceNow-integratie voor](tickets.md)meer informatie.

### <a name="choose-an-improvement-action-status"></a>Kies een status van verbeteringsactie

Kies statussen en neem notities op die specifiek zijn voor de verbeteringsactie. De beelden die u selecteren zijn de volgende:

* **Aan te pakken** - U erkent dat de verbetering actie nodig is en van plan om het aan te pakken op een bepaald punt in de toekomst. Deze status is ook van toepassing op acties die als gedeeltelijk, maar niet volledig voltooid, worden gedetecteerd.
* **Gepland** — Er zijn concrete plannen om de verbeteringsactie af te ronden.
* **Geaccepteerd risico** - Veiligheid moet altijd in evenwicht zijn met bruikbaarheid, en niet elke aanbeveling werkt voor uw omgeving. Wanneer dat het geval is, u ervoor kiezen om het risico of het resterende risico te accepteren en de verbeteringsactie niet uit te voeren. U krijgt geen punten, maar de actie zal niet langer zichtbaar zijn in de lijst met verbeteringsacties. U deze actie in de geschiedenis bekijken of op elk gewenst moment ongedaan maken.
* **Opgelost via derden** en **opgelost door middel van alternatieve mitigatie** - De verbeteringactie is al aangepakt door een toepassing of software van derden of een intern hulpprogramma. U krijgt de punten die de actie waard is, zodat uw score beter weerspiegelt uw algehele veiligheid houding. Als een derde partij of intern gereedschap het besturingselement niet meer dekt, u een andere status kiezen. Houd er rekening mee dat Microsoft geen inzicht heeft in de volledigheid van de implementatie als de verbeteringsactie is gemarkeerd als een van deze statussen.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Verbeteringsacties voor bedreiging & kwetsbaarheidsbeheer

Voor verbeteringsacties in de categorie Apparaat u geen statussen kiezen. In plaats daarvan wordt u doorverwezen naar de bijbehorende [beveiligingsaanbeveling threat & Vulnerability Management (TVM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in het [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) om actie te ondernemen. De uitzondering die u kiest en de rechtvaardiging die u schrijft, is specifiek voor die portal en is niet aanwezig in de Microsoft Secure Score-portal.

#### <a name="completed-improvement-actions"></a>Voltooide verbeteringsacties

Verbeteringsacties hebben een "voltooide" status zodra alle mogelijke punten voor de verbeteringsactie zijn bereikt. Voltooide verbeteringsacties worden bevestigd via Microsoft-gegevens en u de status niet wijzigen.

### <a name="assess-information-and-review-user-impact"></a>Informatie beoordelen en de impact van de gebruiker beoordelen

De **sectie In één oogopslag** vertelt u de categorie, aanvallen die het kan beschermen tegen, en het product.

De **impact van de gebruiker** laat zien wat de gebruikers zullen ervaren als de verbeteringsactie wordt uitgevoerd en gebruikers die worden **beïnvloed,** laat zien wie het zal ervaren.

### <a name="implement-the-improvement-action"></a>De verbeteringsactie implementeren

De **sectie Implementatie** toont alle vereisten, stap voor stap volgende stappen om de verbeteringsactie, de huidige implementatiestatus van de verbeteringsactie en alle koppelingen te voltooien.

Voorwaarde is alle licenties die moeten worden verkregen of acties die moeten worden voltooid voordat de verbeteringactie wordt aangepakt. Zorg ervoor dat u voldoende plaatsen in uw licentie hebt om de verbeteringsactie te voltooien en dat deze licenties worden toegepast op de benodigde gebruikers.  

## <a name="track-your-score-history-and-meet-goals"></a>Houd je scoregeschiedenis bij en bereik doelen

U een grafiek van de score van uw organisatie in de loop van de tijd bekijken op het tabblad **Historie.** U een datumbereik aanpassen en filteren op categorie.

In het tabblad **Statistieken & trends** zijn er verschillende grafieken en grafieken om u meer inzicht te geven in trends en doelen te stellen. U het datumbereik instellen voor de hele pagina met visualisaties. De visualisaties omvatten:

* **Uw beveiligde scorezone** — Aangepast op basis van de doelen en definities van goede, okés en slechte scorebereiken van uw organisatie.
* **Regressietrend** : een tijdlijn van punten die zijn teruggevallen als gevolg van wijzigingen in de configuratie, gebruiker of apparaat.  
* **Vergelijkingstrend** : hoe de beveiligde score van uw organisatie zich in de loop van de tijd verhoudt tot die van anderen. Deze weergave kan regels bevatten die het scoregemiddelde van organisaties met een vergelijkbaar aantal zitplaatsen vertegenwoordigen en een aangepaste vergelijkingsweergave die u instellen.
* **Trend voor risicoacceptatie** — Tijdlijn van verbeteringsacties die zijn gemarkeerd als 'geaccepteerd risico'.
* **Scorewijzigingen** : het aantal behaalde punten, punten dat achteruit gaat, samen met de daaropvolgende scorewijziging, in het opgegeven datumbereik.

## <a name="risk-awareness"></a>Risicobewustzijn

Microsoft Secure Score is een numerieke samenvatting van uw beveiligingshouding op basis van systeemconfiguraties, gebruikersgedrag en andere beveiligingsgerelateerde metingen; het is geen absolute meting van hoe waarschijnlijk uw systeem of gegevens zullen worden geschonden. Het vertegenwoordigt in plaats daarvan de mate waarin u beveiligingscontroles hebt aangenomen in uw Microsoft-omgeving, wat kan helpen het risico op schending te compenseren. Geen enkele online service is volledig immuun voor inbreuken op de beveiliging, en veilige score mag op geen enkele manier worden geïnterpreteerd als een garantie tegen inbreuk op de beveiliging.

## <a name="whats-new"></a>Wat is er nieuw? 

Om van Microsoft Secure Score een betere vertegenwoordiger van uw beveiligingshouding te maken, hebben we enkele wijzigingen aangebracht. Zie [Wat komt er in Microsoft Secure Score?](microsoft-secure-score-whats-coming.md)

### <a name="april-2020"></a>April 2020

#### <a name="added-azure-active-directory-improvement-action"></a>Added Azure Active Directory improvement action Added Azure Active Directory improvement action Added Azure Active Directory improvement action Added Azure

- Geef gebruikers geen toestemming voor onbeheerde toepassingen (momenteel beschikbaar in een vrijgegeven versie)

#### <a name="added-azure-advanced-threat-protection-improvement-actions"></a>Azure Advanced Threat Protection-verbeteringsacties toegevoegd

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

#### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations"></a>Ondersteuning voor beveiligingsaanbevelingen voor Microsoft Defender ATP Threat & Vulnerability Management (TVM)

Alle vrijgegeven beveiligingsaanbevelingen van TVM zijn nu beschikbaar.

### <a name="january---march-2020"></a>Januari - maart 2020

#### <a name="updated-interface-and-functionality"></a>Bijgewerkte interface en functionaliteit

* Alle nieuwe statistieken en trends weergaven voor CISO en lead level discussies
* Nieuwe manieren om je score bij te houden en te benchmarken
* Betere tracking en begrip voor scoreregressies
* Uw verbeteringsacties filteren, taggen, zoeken en groeperen
* Beheren naar uw toekomstige doelen met behulp van scoreprojecties en geplande acties
* En meer!

#### <a name="removed-not-scored-and-review-improvement-actions"></a>Verwijderd "not scored" en "review" verbeteringsacties

Een van de principes van Secure Score is dat de score gestandaardiseerd en gemakkelijk te relateren aan. Het hebben van verbeteringsacties die niet meetbaar of uitvoerbaar zijn, heeft verwarring veroorzaakt. Eén Microsoft Secure Score heeft alleen zin als elke aanbeveling een duidelijk effect op de score kan hebben. Niet-gescoorde verbeteringsacties zijn niet meetbaar en beoordelingsverbeteringsacties worden niet gemeten volgens dezelfde standaard als andere verbeteringsacties.

Om deze redenen zijn alle verbeteringsacties die niet zijn gescoord of waarvoor een beoordelingscadans nodig was, tijdelijk verwijderd. Er is geen actie nodig van uw kant.

#### <a name="simplification-of-the-point-system"></a>Vereenvoudiging van het puntensysteem

Om punten te standaardiseren voor meerdere ervaringen, is elk actiepunt voor verbetering van de beveiligde score bijgewerkt om 10 punten of minder waard te zijn. Het is noodzakelijk om consistenter te zijn in de brede adempauze van veiligheidscontroles die we vandaag hebben en die we in de toekomst zullen toevoegen. Hoewel dit een belangrijke verandering is en u een daling van punttotalen zult zien, zal er geen verandering in uw veiligheidshouding zijn.

## <a name="we-want-to-hear-from-you"></a>We willen graag van je horen

Als je problemen hebt, laat het ons dan weten door te posten in de [community Beveiliging, Privacy & Compliance.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) We houden de gemeenschap in de gaten en zullen hulp bieden.
