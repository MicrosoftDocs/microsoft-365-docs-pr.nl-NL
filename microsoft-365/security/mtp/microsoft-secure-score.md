---
title: Microsoft Secure Score (vorige iteratie)
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
ms.openlocfilehash: a7097bfc9fb4c15408672171b27d577ddfaa9bd5
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818565"
---
# <a name="microsoft-secure-score-previous-iteration"></a>Microsoft Secure Score (vorige iteratie)

>[!IMPORTANT]
>Deze iteratie van Microsoft Secure Score wordt de komende maanden vervangen door nieuwe ontwerpelementen en functies. Als je de nieuwste iteratie nog niet ziet, zul je dat snel doen.
>
>Als u een tabblad **Statistieken & trends** naast Geschiedenis ziet, bes betreft u de nieuwe iteratie. [Ga naar Microsoft Secure Score (nieuw)](microsoft-secure-score-new.md)

Microsoft Secure Score is een meting van de beveiligingshouding van een organisatie, waarbij een hoger aantal aangeeft dat er meer verbeteringsacties worden ondernomen. Als u de aanbevelingen voor de beveiligingsscore volgt, u uw organisatie beschermen tegen bedreigingen. Vanuit een gecentraliseerd dashboard in het Microsoft 365-beveiligingscentrum kunnen organisaties de beveiliging van hun Microsoft 365-identiteiten, gegevens, apps, apparaten en infrastructuur bewaken en werken.

Secure Score helpt organisaties:

* Rapporteer over de huidige status van de beveiligingshouding van de organisatie.
* Verbeter hun beveiligingshouding door vindbaarheid, zichtbaarheid, begeleiding en controle te bieden.  
* Vergelijk met benchmarks en stel key performance indicators (KPI's) vast.

Organisaties krijgen toegang tot robuuste visualisaties van statistieken en trends, integratie met andere Microsoft-producten, scorevergelijking met vergelijkbare organisaties en nog veel meer. De score kan ook reflecteren wanneer oplossingen van derden aanbevolen acties hebben aangepakt.

Daarnaast hebt u toegang tot uw aanbevelingen en u scoren via de [Microsoft Graph API.](https://www.microsoft.com/security/partnerships/graph-security-api) Meer informatie over het [type Secure Score-bron](https://go.microsoft.com/fwlink/?linkid=2092996).

## <a name="how-your-secure-score-is-calculated"></a>Hoe uw veilige score wordt berekend

U krijgt punten voor het configureren van aanbevolen beveiligingsfuncties, het uitvoeren van beveiligingstaken (zoals het bekijken van rapporten) of het aanpakken van de verbeteringsactie met een toepassing of software van derden. Sommige verbeteringsacties geven alleen punten wanneer deze volledig zijn voltooid en sommige geven gedeeltelijke punten als ze voor sommige apparaten of gebruikers zijn voltooid.

We laten u de volledige set van mogelijke verbeteringen zien, ongeacht de licentie, zodat u de best practices voor beveiliging begrijpen en uw score verbeteren. Uw absolute beveiligingshouding wordt vertegenwoordigd door Secure Score, dat hetzelfde blijft, ongeacht welk productlicentie uw organisatie bezit. Houd er rekening mee dat beveiliging moet worden afgewogen tegen bruikbaarheid, en niet elke aanbeveling kan werken voor uw omgeving.

Uw score wordt in realtime bijgewerkt om de informatie weer te geven die wordt weergegeven in de visualisaties en actiepagina's voor verbetering. Secure Score synchroniseert ook dagelijks om systeemgegevens te ontvangen over uw behaalde punten voor elke actie.

### <a name="how-improvement-actions-are-scored"></a>Hoe verbeteracties worden beoordeeld

De meeste worden op een binaire manier gescoord - als u de verbeteringsactie implementeert, zoals het maken van een nieuw beleid of een specifieke instelling inschakelen, krijgt u 100% van de punten. Voor andere verbeteringsacties worden punten gegeven als een percentage van de totale configuratie. Bijvoorbeeld, als de verbetering actie staten krijg je 30 punten door het beschermen van al uw gebruikers met multi-factor authenticatie en je hebt slechts 5 van de 100 totale gebruikers beschermd, zou je een gedeeltelijke score van ongeveer 2 punten (5 beschermd / 100 totaal * 30 max ptn = 2 pts gedeeltelijke score).

### <a name="products-included-in-secure-score"></a>Producten die zijn opgenomen in Secure Score

Momenteel zijn er aanbevelingen voor Microsoft 365 (inclusief Exchange Online), Azure AD, Microsoft Defender ATP, Azure ATP en Cloud App Security. Aanbevelingen voor andere beveiligingsproducten komen binnenkort. De aanbevelingen hebben niet betrekking op alle aanvalsoppervlakken die aan elk product zijn gekoppeld, maar ze zijn een goede basislijn. U de verbeteringsacties ook markeren als gedekt door een derde partij.

## <a name="required-permissions"></a>Vereiste machtigingen

Als u toestemming wilt hebben voor toegang tot Microsoft Secure Score, moet u een van de volgende rollen in Azure Active Directory toegewezen krijgen.

### <a name="read-and-write-roles"></a>Rollen lezen en schrijven

Met lees- en schrijftoegang u wijzigingen aanbrengen en direct communiceren met Secure Score. U ook alleen-lezen toegang toewijzen aan andere gebruikers.

* Globale beheerder
* Beveiligingsbeheerder
* Exchange-beheerder
* SharePoint-beheerder

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

* SecurityEvents.Read.All (voor alleen-lezen rol)
* SecurityEvents.ReadWrite.All (voor lees- en schrijfrol)

## <a name="gain-visibility-into-your-security-posture"></a>Krijg inzicht in uw beveiligingshouding

Om u sneller te helpen met de informatie die u nodig hebt, worden de verbeteracties van Microsoft in groepen georganiseerd:

* Identiteit (Azure AD-accounts & rollen)
* Gegevens (Microsoft Information Protection)
* Apparaat (voorlopig geen verbeteringsacties)
* App (e-mail- en cloud-apps, waaronder Office 365 en Microsoft Cloud App Security)
* Infrastructuur (voorlopig geen verbeteringsacties)

Op de overzichtspagina van Microsoft Secure Score u zien hoe punten worden verdeeld tussen deze groepen en welke punten beschikbaar zijn. De overzichtspagina is ook de plek om een all-up weergave te krijgen van de totale score, historische trend van uw veilige score met benchmarkvergelijkingen en geprioriteerde verbeteracties die kunnen worden genomen om uw score te verbeteren.

![Secure Score homepage ](../../media/secure-score/homepage-original.png)
 *Figuur 1: Microsoft Secure Score overzicht pagina*

## <a name="take-action-to-improve-your-score"></a>Onderneem actie om je score te verbeteren

Op het tabblad Verbeteringsacties worden de beveiligingsaanbevelingen weergegeven die mogelijke aanvalsoppervlakken aanpakken, samen met hun status (voltooid, niet voltooid, opgelost via derden en genegeerd). U alle verbeteracties zoeken, filteren en groeperen.

### <a name="ranking"></a>Ranking

Ranking is gebaseerd op het aantal resterende punten dat nog moet worden bereikt, implementatieproblemen, gebruikersimpact en complexiteit. De hoogst gerangschikte verbeteringsacties hebben een groot aantal punten die met lage moeilijkheidsgraad, gebruikerseffect, en ingewikkeldheid blijven.

### <a name="actions"></a>Acties

Wanneer u een specifieke verbeteringsactie selecteert, wordt er een fly out weergegeven. Als u de actie wilt voltooien, hebt u een aantal opties:

1. Selecteer **Instellingen weergeven** om het configuratiescherm te bekijken en de wijziging door te voeren. U krijgt dan de punten die de actie waard is, zichtbaar aan de bovenkant van de vlieg uit. Het kan tot 24 uur duren voordat punten zijn bijgewerkt.

2. Selecteer **Oplossen via derden** omdat de verbeteringsactie al is aangepakt door een toepassing of software van derden. U krijgt de punten die de actie waard is, zodat uw veilige score beter uw algehele beveiligingshouding weerspiegelt. Als een derde partij het besturingselement niet meer dekt, u de verbeteringsactie als niet voltooid markeren. Houd er rekening mee dat Microsoft geen inzicht heeft in de vraag of aan de scorevereisten is voldaan als de verbeteringsactie is gemarkeerd als opgelost via derden.

3. Selecteer **Negeren** omdat u hebt besloten het risico te accepteren en de verbeteringsactie niet uit te voeren. Zodra u een verbeteringsactie negeert, wordt het totale aantal veilige scorepunten dat u bereiken verminderd. U deze actie in de geschiedenis bekijken of op elk gewenst moment ongedaan maken.

![Actievoorbeeld veilige scoreverbetering](../../media/secure-score/secure-score1x450.png)

*Cijfers 2: De flyout van de actie van de verbetering*

## <a name="monitor-improvements-over-time"></a>Verbeteringen in de loop van de tijd controleren

U een grafiek van de score van uw organisatie in de loop van de tijd bekijken op het tabblad **Geschiedenis.** Hieronder vindt u een lijst met alle acties die zijn uitgevoerd in het geselecteerde tijdbereik en de bijbehorende kenmerken, zoals de resulterende punten en categorie. U een datumbereik aanpassen en filteren op categorie.

## <a name="risk-awareness"></a>Risicobewustzijn

Microsoft Secure Score is een numeriek overzicht van uw beveiligingshouding op basis van systeemconfiguraties, gebruikersgedrag en andere beveiligingsgerelateerde metingen; het is geen absolute meting van hoe waarschijnlijk uw systeem of gegevens zullen worden geschonden. Integendeel, het vertegenwoordigt de mate waarin u beveiligingscontroles hebt aangenomen in uw Microsoft-omgeving die kunnen helpen het risico van inbreuk te compenseren. Geen enkele online service is volledig immuun voor inbreuken op de beveiliging, en een veilige score mag niet worden geïnterpreteerd als een garantie tegen inbreuk op de beveiliging op enigerlei wijze.

## <a name="whats-new"></a>Wat is er nieuw?

Om van Microsoft Secure Score een betere vertegenwoordiger van uw beveiligingshouding te maken, hebben we enkele wijzigingen aangebracht. Zie Wat komt er in Microsoft Secure Score voor meer informatie over geplande [wijzigingen?](microsoft-secure-score-whats-coming.md)

### <a name="april-21st-2020"></a>21 april 2020

#### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Verbeteringsacties verwijderen die niet voldoen aan de verwachtingen voor betrouwbare metingen of geen nuttige weergave van beveiligingshouding bieden

Om ervoor te zorgen dat de Microsoft Secure Score zinvol is en dat elke verbeteringsactie meetbaar en betrouwbaar is, verwijderen we de volgende verbeteringsacties.

- IRM-beveiligingen toepassen op documenten
- Beleid voor preventie van gegevensverlies toepassen

### <a name="january---march-2020"></a>Januari - maart 2020

#### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>Ondersteuning voor beveiligingsstandaarden voor Azure AD-verbeteringsacties

Microsoft Secure Score werkt verbeteracties bij ter ondersteuning van [beveiligingsstandaarden in Azure AD,](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)waardoor het eenvoudiger wordt om uw organisatie te beschermen met vooraf geconfigureerde beveiligingsinstellingen voor veelvoorkomende aanvallen.

Het heeft invloed op de volgende verbeteracties:

- Zorg ervoor dat alle gebruikers meervoudige verificatie kunnen voltooien voor veilige toegang
- MFA vereisen voor administratieve rollen
- Beleid inschakelen om verouderde verificatie te blokkeren

#### <a name="removed-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Verwijderde verbeteringsacties die niet voldoen aan de verwachtingen voor betrouwbare metingen of geen nuttige weergave van beveiligingshouding bieden

Om ervoor te zorgen dat de Microsoft Secure Score zinvol is en dat elke verbeteringsactie meetbaar en betrouwbaar is, verwijderen we de volgende verbeteringsacties.

- Gebruikersdocumenten opslaan in OneDrive voor Bedrijven
- Office 365 ATP-beleid voor veilige bijlagen instellen
- Veilige koppelingen voor Office 365 instellen om URL's te verifiëren
- Postvakdelegatie niet toestaan
- Anonieme koppelingen voor het delen van gasten toestaan voor sites en documenten
- Cloud App Security Console inschakelen
- Verlooptijd configureren voor externe koppelingen voor delen
- Controlegegevens opnemen inschakelen
- Ontdek riskante en niet-conforme schaduw-IT-toepassingen
- Machtigingen bekijken & risicovolle OAuth-toepassingen blokkeren die zijn verbonden met uw omgeving
- Versiebeheer instellen in SharePoint online documentbibliotheken
- Accounts verwijderen/blokkeren die de afgelopen 30 dagen niet zijn gebruikt
- Minder dan 5 globale beheerders aanwijzen

#### <a name="removed-not-scored-improvement-actions"></a>Verwijderde "niet gescoorde" verbeteracties

Een van de principes van Secure Score is dat de score moet worden gestandaardiseerd en gemakkelijk te relateren aan. Het hebben van verbeteracties die niet meetbaar of bruikbaar zijn, heeft verwarring veroorzaakt. Microsoft Secure Score heeft alleen zin als elke aanbeveling een duidelijk effect kan hebben op de score. Niet gescoorde verbeteracties zijn niet meetbaar.  

Om deze redenen zijn alle verbeteracties die niet zijn gescoord, verwijderd. Er is geen actie nodig van uw kant.

#### <a name="removed-device-improvement-actions"></a>Acties voor apparaatverbetering verwijderd

Na een evaluatie van de categorie microsoft secure score-apparaat van verbeteringsacties, werd vastgesteld dat deze acties momenteel de beleidsstatus beoordelen en niet de configuratiestatus van apparaten. Aangezien de configuratie direct is gekoppeld aan de beveiligingshouding, werden de bestaande apparaatacties bepaald om de organisatiehouding niet volledig weer te geven.  We zullen de huidige acties in de apparaatcategorie verwijderen terwijl we werken aan een reeks aanbevelingen die diagnostische gegevens rechtstreeks gebruiken om de beveiligingshouding van het apparaat beter weer te geven.

De volgende verbeteracties zijn verwijderd:

- Microsoft Intune Mobile Device Management inschakelen
- Een Microsoft Intune Compliance Policy voor Android maken
- Een Microsoft Intune Compliance Policy voor Android for Work maken
- Een Microsoft Intune-app-beveiligingsbeleid voor Android maken
- Een Microsoft Intune-app-beveiligingsbeleid voor iOS maken
- Apparaten markeren zonder Microsoft Intune-nalevingsbeleid dat is toegewezen als niet-compatibel
- Een Microsoft Intune Compliance Policy voor iOS maken
- Een Microsoft Intune Compliance Policy voor macOS maken
- Een Microsoft Intune Compliance Policy voor Windows maken
- Een Microsoft Intune-configuratieprofiel voor Android maken
- Een Microsoft Intune-configuratieprofiel voor Android voor werk maken
- Een Microsoft Intune-configuratieprofiel voor macOS maken
- Een Microsoft Intune-configuratieprofiel voor iOS maken
- Een Microsoft Intune-configuratieprofiel voor Windows maken
- Verbeterde jailbreakdetectie inschakelen in Microsoft Intune
- Vereisen dat alle apparaten worden gepatcht, anti-virus en firewalls zijn ingeschakeld
- Windows Defender ATP-integratie inschakelen in Microsoft Intune
- Een Microsoft Intune Windows Information Protection Policy maken
- Alle apparaten vereisen dat ze geavanceerde beveiligingsconfiguraties hebben
- Wekelijks rapport over geblokkeerde apparaten bekijken

#### <a name="mfa-improvement-action-updates"></a>MFA-actie-updates voor verbetering

Om de noodzaak voor bedrijven om de meest beveiliging te garanderen tijdens het toepassen van beleid dat werkt met hun bedrijf, Microsoft Secure Score heeft verwijderd drie verbetering acties gecentreerd rond multi-factor authenticatie, en twee toegevoegd.

Verwijderde verbeteringsacties:

- Alle gebruikers registreren voor meervoudige verificatie
- MFA vereisen voor alle gebruikers
- MFA vereisen voor azure AD-geprivilegieerde rollen

Toegevoegde verbeteringsacties:

- Zorg ervoor dat alle gebruikers meervoudige verificatie kunnen voltooien voor veilige toegang
- MFA vereisen voor administratieve rollen

 Deze nieuwe verbeteringsacties vereisen het registreren van uw gebruikers of beheerders voor multi-factor authenticatie (MFA) in uw directory en het vaststellen van de juiste set beleidsregels die passen bij uw organisatiebehoeften. Het belangrijkste doel is flexibiliteit te hebben, terwijl ervoor wordt gezorgd dat al uw gebruikers en beheerders zich kunnen verifiëren met meerdere factoren of op risico's gebaseerde identiteitsverificatieprompts. Dat kan de vorm aannemen van het hebben van meerdere beleidsregels die scoped-beslissingen toepassen, of het instellen van beveiligingsstandaarden (komende 16 maart) waarmee Microsoft kan beslissen wanneer u gebruikers voor MFA moet uitdagen.

#### <a name="removed-review-improvement-actions"></a>Verwijderde "review" verbeteracties

Een van de principes van Secure Score is dat de score moet worden gestandaardiseerd en gemakkelijk te relateren aan. Het hebben van verbeteracties die niet meetbaar of bruikbaar zijn, heeft verwarring veroorzaakt. Eén Microsoft Secure Score heeft alleen zin wanneer elke aanbeveling een duidelijk effect kan hebben op de score. Verbetermaatregelen worden niet gemeten volgens dezelfde standaard als andere verbeteringsacties.  

Om deze redenen zijn alle verbeteringsacties waarvoor een beoordelingscadans nodig was, tijdelijk verwijderd. Er is geen actie nodig van uw kant.

### <a name="preview-features"></a>Voorbeeldfuncties

De volgende functies worden opgenomen in de [preview-release:](microsoft-secure-score-preview.md)

* Alle nieuwe statistieken en trends weergaven voor CISO en lead level discussies
* Nieuwe manieren om je score bij te houden en te benchmarken
* Betere tracking en monitoring voor score regressies
* Uw verbeteracties filteren, taggen, zoeken en groeperen
* Beheer richting uw toekomstige doelen met behulp van scoreprojecties en geplande acties
* Vereenvoudiging van het puntensysteem
* En nog veel meer!

## <a name="we-want-to-hear-from-you"></a>We willen graag van u horen

Als je problemen hebt, laat het ons weten door een bericht te plaatsen in de [community Beveiliging, privacy & Compliance.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) We houden de gemeenschap in de gaten en zullen hulp bieden.
