---
title: Microsoft Secure Score (preview)
description: Beschrijft Microsoft Secure Score in het Microsoft 365-beveiligingscentrum, hoe details worden berekend en wat beveiligingsbeheerders kunnen verwachten.
keywords: beveiliging, malware, Microsoft 365, M365, secure score, security center, verbeteracties
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
ms.openlocfilehash: 4305d97d33439383989cf8c300522268727b1ae7
ms.sourcegitcommit: a4926e98b6594bbee68bfca90438c9c764499255
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/09/2020
ms.locfileid: "45092937"
---
# <a name="microsoft-secure-score-preview"></a>Microsoft Secure Score (preview)

>[!IMPORTANT]
>Sommige informatie heeft betrekking op vooraf uitgebrachte producten die aanzienlijk kunnen worden gewijzigd voordat het commercieel wordt vrijgegeven. Microsoft geeft geen garanties, uitdrukkelijk of impliciet, met betrekking tot de hier verstrekte informatie.

Microsoft Secure Score is een meting van de beveiligingshouding van een organisatie, waarbij een hoger aantal aangeeft dat er meer verbeteringsacties worden ondernomen. Het kan worden gevonden op https://security.microsoft.com/securescore in de [Microsoft 365 security center](overview-security-center.md).

Als u de aanbevelingen voor de beveiligingsscore volgt, u uw organisatie beschermen tegen bedreigingen. Vanuit een gecentraliseerd dashboard in het Microsoft 365-beveiligingscentrum kunnen organisaties de beveiliging van hun Microsoft 365-identiteiten, gegevens, apps, apparaten en infrastructuur bewaken en werken.

Secure Score helpt organisaties:  

* Rapporteer over de huidige status van de beveiligingshouding van de organisatie.
* Verbeter hun beveiligingshouding door vindbaarheid, zichtbaarheid, begeleiding en controle te bieden.  
* Vergelijk met benchmarks en stel key performance indicators (KPI's) vast.

Organisaties krijgen toegang tot robuuste visualisaties van statistieken en trends, integratie met andere Microsoft-producten, scorevergelijking met vergelijkbare organisaties en nog veel meer. De score kan ook reflecteren wanneer oplossingen van derden aanbevolen acties hebben aangepakt.

Daarnaast hebt u toegang tot uw aanbevelingen en u scoren via de [Microsoft Graph API.](https://www.microsoft.com/security/partnerships/graph-security-api) Meer informatie over het [type Secure Score-bron](https://go.microsoft.com/fwlink/?linkid=2092996).

## <a name="how-it-works"></a>Hoe het werkt

U krijgt punten voor het configureren van aanbevolen beveiligingsfuncties, het uitvoeren van beveiligingstaken of het aanpakken van de verbeteringsactie met een toepassing of software van derden, of een alternatieve beperking. Sommige verbeteringsacties geven alleen punten wanneer deze volledig zijn voltooid en sommige geven gedeeltelijke punten als ze voor sommige apparaten of gebruikers zijn voltooid. Als u een van de verbeteracties niet of wilt uitvoeren, u ervoor kiezen om het risico of het resterende risico te accepteren.

We laten u de volledige set van mogelijke verbeteringen zien, ongeacht de licentie, zodat u de best practices voor beveiliging begrijpen en uw score verbeteren. Uw absolute beveiligingshouding wordt vertegenwoordigd door Secure Score, dat hetzelfde blijft, ongeacht welk productlicentie uw organisatie bezit. Houd er rekening mee dat beveiliging moet worden afgewogen tegen bruikbaarheid, en niet elke aanbeveling kan werken voor uw omgeving.

Uw score wordt in realtime bijgewerkt om de informatie weer te geven die wordt weergegeven in de visualisaties en actiepagina's voor verbetering. Secure Score synchroniseert ook dagelijks om systeemgegevens te ontvangen over uw behaalde punten voor elke actie.

### <a name="how-improvement-actions-are-scored"></a>Hoe verbeteracties worden beoordeeld

Elke verbeteringsactie is 10 punten of minder waard. De meeste worden op een binaire manier gescoord - als u de verbeteringsactie implementeert, zoals het maken van een nieuw beleid of een specifieke instelling inschakelen, krijgt u 100% van de punten. Voor andere verbeteringsacties worden punten gegeven als een percentage van de totale configuratie. Bijvoorbeeld, als de verbetering actie staten krijg je 30 punten door het beschermen van al uw gebruikers met multi-factor authenticatie en je hebt slechts 5 van de 100 totale gebruikers beschermd, zou je een gedeeltelijke score van ongeveer 2 punten (5 beschermd / 100 totaal * 30 max ptn = 2 pts gedeeltelijke score).

### <a name="products-included-in-secure-score"></a>Producten die zijn opgenomen in Secure Score

Momenteel zijn er aanbevelingen voor Microsoft 365 (inclusief Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP en Cloud App Security. Aanbevelingen voor andere beveiligingsproducten komen binnenkort. De aanbevelingen hebben niet betrekking op alle aanvalsoppervlakken die aan elk product zijn gekoppeld, maar ze zijn een goede basislijn. U de verbeteringsacties ook markeren als gedekt door een derde partij of alternatieve mitigatie.

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

### <a name="graph-api"></a>Grafiek-API

Als u toegang wilt krijgen tot de Graph API, moet u naast een rol een van de volgende scopes hebben:

* SecurityEvents.Read.All (voor alleen-lezen rollen)
* SecurityEvents.ReadWrite.All (voor lees- en schrijfrollen)

## <a name="gain-visibility-into-your-security-posture"></a>Krijg inzicht in uw beveiligingshouding

Om u sneller te helpen met de informatie die u nodig hebt, worden de verbeteracties van Microsoft in groepen georganiseerd:

* Identiteit (Azure AD-accounts & rollen)
* Gegevens (Microsoft Information Protection)
* Apparaat (Microsoft Defender ATP)
* App (e-mail- en cloud-apps, waaronder Office 365 en Microsoft Cloud App Security)
* Infrastructuur (voorlopig geen verbeteringsacties)

>[!NOTE]
>In de recente release van Microsoft Secure Score is een verbeterd scoremodel uitgebracht waardoor Microsoft Secure Score tijdelijk niet compatibel is met Identity Secure Score en de Graph API. [Details weergeven](microsoft-secure-score-preview.md#incompatibility-with-identity-secure-score-and-graph-api)

Op de overzichtspagina van Microsoft Secure Score u zien hoe punten worden verdeeld tussen deze groepen en welke punten beschikbaar zijn. De overzichtspagina is ook de plek om een all-up weergave te krijgen van de totale score, historische trend van uw veilige score met benchmarkvergelijkingen en geprioriteerde verbeteracties die kunnen worden genomen om uw score te verbeteren.

![Secure Score homepage ](../../media/secure-score/secure-score-homepage.png)
 *Figuur 1: Microsoft Secure Score overzicht pagina*

## <a name="take-action-to-improve-your-score"></a>Onderneem actie om je score te verbeteren

Op het tabblad **Verbeteracties** worden de beveiligingsaanbevelingen weergegeven die mogelijke aanvalsoppervlakken aanpakken, samen met hun status (om aan te pakken, gepland, risico geaccepteerd, opgelost via derden, opgelost door alternatieve mitigatie en voltooid). U alle verbeteracties zoeken, filteren en groeperen.  

### <a name="ranking"></a>Ranking

Ranking is gebaseerd op het aantal resterende punten dat nog moet worden bereikt, implementatieproblemen, gebruikersimpact en complexiteit. De hoogst gerangschikte verbeteringsacties hebben een groot aantal punten die met lage moeilijkheidsgraad, gebruikerseffect, en ingewikkeldheid blijven.

### <a name="view-improvement-action-details"></a>Details van de verbeteringsactie weergeven

Wanneer u een specifieke verbeteringsactie selecteert, wordt een flyout voor de volledige pagina weergegeven.  

![Voorbeeld van flyout van de actie voor verbetering ](../../media/secure-score/secure-score-improvement-action-details.png)
 *figuur 2: Flyout voor de actie verbetering*

Als u de actie wilt voltooien, hebt u een aantal opties:

* Selecteer **Beheren** om het configuratiescherm te gaan en de wijziging aan te brengen. U krijgt dan de punten die de actie waard is, zichtbaar in de fly out. Punten duren over het algemeen ongeveer 24 uur om te updaten.

* Selecteer **Delen** om de directe koppeling naar de verbeteringsactie te kopiëren of kies het platform om de koppeling te delen, zoals e-mail, Microsoft Teams, Microsoft Planner of ServiceNow. Als u ServiceNow selecteert, u een wijzigingsticket maken dat zichtbaar is in ServiceNow en het microsoft 365-beveiligingscentrum thuis. Zie [Microsoft 365 Security Center en ServiceNow-integratie](tickets.md)voor meer informatie.

### <a name="choose-an-improvement-action-status"></a>Een status voor verbeteringsactie kiezen

Kies statussen en nota's die specifiek zijn voor de verbeteringsactie. De beelden die u selecteren zijn de volgende:

* **Aan te pakken** - U erkent dat de verbetering actie nodig is en van plan om het aan te pakken op een bepaald punt in de toekomst. Deze status is ook van toepassing op acties die gedeeltelijk worden gedetecteerd, maar niet volledig zijn voltooid.
* **Gepland** — Er zijn concrete plannen om de verbeteractie af te ronden.
* **Geaccepteerde risico's** — Beveiliging moet altijd in evenwicht zijn met bruikbaarheid, en niet elke aanbeveling zal werken voor uw omgeving. Wanneer dat het geval is, u ervoor kiezen om het risico, of het resterende risico te accepteren, en niet de verbetering actie uit te voeren. U krijgt geen punten, maar de actie is niet langer zichtbaar in de lijst met verbeteracties. U deze actie in de geschiedenis bekijken of op elk gewenst moment ongedaan maken.
* **Opgelost via derden** en **opgelost door alternatieve mitigatie** - De verbeteringsactie is al verholpen door een toepassing of software van derden of een intern hulpmiddel. U krijgt de punten die de actie waard is, zodat uw score beter weerspiegelt uw algehele veiligheid houding. Als een derde partij of intern gereedschap het besturingselement niet meer dekt, u een andere status kiezen. Houd er rekening mee dat Microsoft geen inzicht heeft in de volledigheid van de implementatie als de verbeteringsactie is gemarkeerd als een van deze statussen.

#### <a name="threat--vulnerability-management-improvement-actions"></a>Verbeteracties voor & vulnerability management

Voor verbeteracties in de categorie 'Apparaat' u geen statussen kiezen. In plaats daarvan wordt u doorverwezen naar de bijbehorende [beveiligingsaanbeveling voor Threat & Vulnerability Management (TVM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/tvm-security-recommendation) in het [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use) om actie te ondernemen. De uitzondering die u kiest en rechtvaardiging die u schrijft, is specifiek voor die portal en is niet aanwezig in de Microsoft Secure Score-portal.

#### <a name="completed-improvement-actions"></a>Voltooide verbeteringsacties

Verbeteringsacties hebben een "voltooide" status zodra alle mogelijke punten voor de verbeteringsactie zijn bereikt. Voltooide verbeteringsacties worden bevestigd met Microsoft-gegevens en u de status niet wijzigen.

### <a name="assess-information-and-review-user-impact"></a>Informatie beoordelen en de impact van de gebruiker beoordelen

De **in één oogopslag** sectie vertelt u de categorie, aanvallen die het kan beschermen tegen, en het product.

De **impact van** de gebruiker laat zien wat de gebruikers zullen ervaren als de verbeteringsactie wordt uitgevoerd en gebruikers die er last **van** hebben, laat zien wie deze zal ervaren.

### <a name="implement-the-improvement-action"></a>De verbeteringsactie uitvoeren

In de sectie **Implementatie** worden alle vereisten weergegeven, stap voor stap volgende stappen om de verbeteringsactie te voltooien, de huidige implementatiestatus van de verbeteringsactie en meer koppelingen.

Voorwaarde is dat er licenties moeten worden verkregen of acties die moeten worden voltooid voordat de verbeteringsactie wordt aangepakt. Zorg ervoor dat u voldoende plaatsen in uw licentie hebt om de verbeteringsactie te voltooien en dat deze licenties worden toegepast op de benodigde gebruikers.  

## <a name="track-your-score-history-and-meet-goals"></a>Houd je scoregeschiedenis bij en voldoe doelen

U een grafiek van de score van uw organisatie in de loop van de tijd bekijken op het tabblad **Geschiedenis.** Hieronder vindt u een lijst met alle acties die zijn uitgevoerd in het geselecteerde tijdbereik en de bijbehorende kenmerken, zoals de resulterende punten en categorie. U een datumbereik aanpassen en filteren op categorie.

Op het tabblad **Statistieken & trends** zijn er verschillende grafieken en grafieken om u meer inzicht te geven in trends en doelen te stellen. U het datumbereik instellen voor de hele pagina met visualisaties. De visualisaties omvatten:

* **Uw Secure Score-zone** - Aangepast op basis van de doelen en definities van goede, oke- en slechte scorebereiken van uw organisatie.
* **Regressietrend** : een tijdlijn van punten die zijn achteruitgegaan als gevolg van configuratie-, gebruikers- of apparaatwijzigingen.  
* **Vergelijkingstrend** : hoe de Secure Score van uw organisatie zich verhoudt tot de tijd van anderen. Deze weergave kan regels bevatten die het scoregemiddelde vertegenwoordigen van organisaties met een vergelijkbaar aantal zitplaatsen en een aangepaste vergelijkingsweergave die u instellen.
* Trend naar acceptatie van **risico's** — Tijdlijn van verbeteracties gemarkeerd als 'geaccepteerd risico'.
* **Scorewijzigingen** — Het aantal behaalde punten, punten, samen met de daaropvolgende scorewijziging, in het opgegeven datumbereik.

## <a name="risk-awareness"></a>Risicobewustzijn

Microsoft Secure Score is een numeriek overzicht van uw beveiligingshouding op basis van systeemconfiguraties, gebruikersgedrag en andere beveiligingsgerelateerde metingen; het is geen absolute meting van hoe waarschijnlijk uw systeem of gegevens zullen worden geschonden. Integendeel, het vertegenwoordigt de mate waarin u beveiligingscontroles hebt aangenomen in uw Microsoft-omgeving die kunnen helpen het risico van inbreuk te compenseren. Geen enkele online service is volledig immuun voor inbreuken op de beveiliging, en een veilige score mag niet worden geïnterpreteerd als een garantie tegen inbreuk op de beveiliging op enigerlei wijze.

## <a name="whats-new"></a>Wat is er nieuw? 

Om van Microsoft Secure Score een betere vertegenwoordiger van uw beveiligingshouding te maken, hebben we enkele wijzigingen aangebracht. Zie Wat komt er in Microsoft Secure Score voor meer informatie over geplande [wijzigingen?](microsoft-secure-score-whats-coming.md)

### <a name="incompatibility-with-identity-secure-score-and-graph-api"></a>Onverenigbaarheid met Identity Secure Score en Graph API

In de recente release van Microsoft Secure Score is een verbeterd scoremodel uitgebracht. Deze wijzigingen zorgen voor een flexibeler en nauwkeuriger beeld van uw beveiligingshouding. Deze updates hebben Microsoft Secure Score echter tijdelijk onverenigbaar gemaakt met Identity Secure Score en de Graph API.

Na verloop van tijd zullen Identity Secure Score en de Graph API het nieuwe scoremodel aannemen. Tot die tijd zien klanten verschillen in de scores die worden gerapporteerd door Microsoft Secure Score, Identity Secure Score en de Graph API. Onze excuses voor het ongemak dat dit veroorzaakt, en werken om ervoor te zorgen dat deze ervaringen meer compatibel zijn in de toekomst.

### <a name="april-2020"></a>April 2020

#### <a name="added-azure-active-directory-improvement-action"></a>Verbeterdeactie voor Azure Active Directory toegevoegd

- Sta gebruikers niet toe toestemming te verlenen voor onbeheerde toepassingen (momenteel beschikbaar in de versie die is vrijgegeven)

#### <a name="added-azure-advanced-threat-protection-improvement-actions"></a>Azure Advanced Threat Protection-verbeteringsacties toegevoegd

- Afdrukspoolerservice uitschakelen op domeincontrollers
- Onveilige Kerberos-delegaties wijzigen om imitatie te voorkomen
- Lokale beheerderswachtwoorden beveiligen en beheren met Microsoft LAPS
- Risico's voor zijdelingse verplaatsingspaden voor gevoelige entiteiten verminderen
- Slapende accounts uit gevoelige groepen verwijderen
- Onveilige SID-geschiedeniskenmerken verwijderen uit entiteiten
- Onbeveiligde accountkenmerken oplossen
- Blootstelling aan duidelijke tekstreferenties stoppen
- Communicatie met legacy-protocollen stoppen
- Stop zwak cijfergebruik

#### <a name="support-for-microsoft-defender-atp-threat--vulnerability-management-tvm-security-recommendations"></a>Ondersteuning voor beveiligingsaanbevelingen voor Microsoft Defender ATP Threat & Vulnerability Management (TVM)

Alle vrijgegeven beveiligingsaanbevelingen geleverd door TVM zijn nu beschikbaar.

### <a name="january---march-2020"></a>Januari - maart 2020

#### <a name="updated-interface-and-functionality"></a>Bijgewerkte interface en functionaliteit

* Alle nieuwe statistieken en trends weergaven voor CISO en lead level discussies
* Nieuwe manieren om je score bij te houden en te benchmarken
* Beter volgen en begrijpen voor scoreregressies
* Uw verbeteracties filteren, taggen, zoeken en groeperen
* Beheer richting uw toekomstige doelen met behulp van scoreprojecties en geplande acties
* En nog veel meer!

#### <a name="removed-not-scored-and-review-improvement-actions"></a>Verwijderde verbeteracties 'niet gescoord' en 'beoordelen'

Een van de principes van Secure Score is dat de score moet worden gestandaardiseerd en gemakkelijk te relateren aan. Het hebben van verbeteracties die niet meetbaar of bruikbaar zijn, heeft verwarring veroorzaakt. Eén Microsoft Secure Score heeft alleen zin wanneer elke aanbeveling een duidelijk effect kan hebben op de score. Niet-beoordeelde verbeteringsacties zijn niet meetbaar en verbeteracties worden niet gemeten volgens dezelfde standaard als andere verbeteringsacties.

Om deze redenen zijn alle verbeteracties die niet zijn gescoord of waarvoor een beoordelingscadans vereist is, tijdelijk verwijderd. Er is geen actie nodig van uw kant.

#### <a name="simplification-of-the-point-system"></a>Vereenvoudiging van het puntensysteem

Om punten te standaardiseren voor meerdere ervaringen, is elk actiepunttotaal voor secure score-verbetering bijgewerkt om 10 punten of minder waard te zijn. Het is noodzakelijk meer consistent te zijn in de brede adem van veiligheidscontroles die we vandaag hebben en degenen die we in de toekomst zullen toevoegen. Hoewel dit een belangrijke verandering is en je een daling van punttotalen zult zien, zal er geen verandering zijn in je beveiligingshouding.

## <a name="we-want-to-hear-from-you"></a>We willen graag van u horen

Als je problemen hebt, laat het ons weten door een bericht te plaatsen in de [community Beveiliging, privacy & Compliance.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) We houden de gemeenschap in de gaten en zullen hulp bieden.
