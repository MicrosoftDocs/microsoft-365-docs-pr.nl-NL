---
title: Microsoft Secure Score
description: Beschrijft Microsoft Secure Score in het Microsoft 365-beveiligingscentrum, hoe details worden berekend en wat beveiligingsbeheerders kunnen verwachten.
keywords: beveiliging, malware, Microsoft 365, M365, beveiligde score, beveiligingscentrum, verbeteracties
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
ms.openlocfilehash: ea91fc29a0fa768113ff3ca8d8129a0ee56ab5f5
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42810956"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

Microsoft Secure Score is een meting van de beveiligingshouding van een organisatie, met een hoger getal dat aangeeft dat er meer verbeteracties zijn ondernomen. Als u de aanbevelingen voor beveiligingsscore volgt, u uw organisatie beschermen tegen bedreigingen. Vanuit een gecentraliseerd dashboard in het Microsoft 365-beveiligingscentrum kunnen organisaties de beveiliging van hun Microsoft 365-identiteiten, gegevens, apps, apparaten en infrastructuur bewaken en eraan werken.

Secure Score helpt organisaties:

* Verslag over de huidige stand van zaken in de beveiligingshouding van de organisatie.
* Verbeter hun beveiligingshouding door vindbaarheid, zichtbaarheid, begeleiding en controle te bieden.  
* Vergelijk met benchmarks en stel key performance indicators (KPI's) vast.

Organisaties krijgen toegang tot robuuste visualisaties van statistieken en trends, integratie met andere Microsoft-producten, scorevergelijking met vergelijkbare organisaties en nog veel meer. De score kan ook weerspiegelen wanneer oplossingen van derden aanbevolen acties hebben aangepakt.

Bovendien u toegang krijgen tot uw aanbevelingen en score via de [Microsoft Graph API](https://www.microsoft.com/security/partnerships/graph-security-api). Meer informatie over het [resourcetype Secure Score](https://go.microsoft.com/fwlink/?linkid=2092996).

## <a name="how-it-works"></a>Hoe het werkt

U krijgt punten voor het configureren van aanbevolen beveiligingsfuncties, het uitvoeren van beveiligingsgerelateerde taken (zoals het bekijken van rapporten) of het aanpakken van de verbeteringsactie met een toepassing of software van derden. Sommige verbeteringsacties geven alleen punten wanneer ze volledig zijn voltooid, en sommige geven gedeeltelijke punten als ze zijn voltooid voor sommige apparaten of gebruikers.

We tonen u de volledige set mogelijke verbeteringen, ongeacht de licentie, zodat u de beste praktijken op het gebied van beveiliging begrijpen en uw score verbeteren. Uw absolute beveiligingshouding wordt vertegenwoordigd door Secure Score, die hetzelfde blijft, ongeacht welke productlicenties uw organisatie bezit. Houd er rekening mee dat beveiliging moet worden afgewogen tegen bruikbaarheid, en niet elke aanbeveling kan werken voor uw omgeving.

Uw score wordt in realtime bijgewerkt om de informatie weer te geven die wordt weergegeven in de visualisaties en actiepagina's voor verbeteringen. Secure Score synchroniseert ook dagelijks om systeemgegevens te ontvangen over uw behaalde punten voor elke actie.

### <a name="how-improvement-actions-are-scored"></a>Hoe verbeteracties worden beoordeeld

De meeste worden op binaire wijze gescoord - als u de verbeteringsactie implementeert, zoals een nieuw beleid maken of een specifieke instelling inschakelen, krijgt u 100% van de punten. Voor andere verbeteringsacties worden punten opgegeven als percentage van de totale configuratie. Bijvoorbeeld, als de verbetering actie stelt dat je 30 punten door het beschermen van al uw gebruikers met multi-factor authenticatie en je hebt slechts 5 van de 100 totale gebruikers beschermd, zou je een gedeeltelijke score van ongeveer 2 punten (5 beschermd / 100 totaal * 30 max pts = 2 pts gedeeltelijke score).

### <a name="products-included-in-secure-score"></a>Producten die zijn opgenomen in Secure Score

Momenteel zijn er aanbevelingen voor Office 365 (waaronder SharePoint Online, Exchange Online, OneDrive voor Bedrijven, Microsoft Information Protection en meer), Azure AD en Cloud App Security. Aanbevelingen voor andere beveiligingsproducten, zoals Azure ATP en Microsoft Defender ATP, komen binnenkort. De aanbevelingen hebben geen betrekking op alle aanvalsoppervlakken die aan elk product zijn gekoppeld, maar ze zijn een goede basislijn. U de verbeteringsacties ook markeren als gedekt door een derde partij.

## <a name="required-permissions"></a>Vereiste machtigingen

Als u toestemming wilt hebben voor toegang tot Microsoft Secure Score, moet u een van de volgende rollen in Azure Active Directory toegewezen krijgen.

### <a name="read-and-write-roles"></a>Rollen lezen en schrijven

Met lees- en schrijftoegang u wijzigingen aanbrengen en direct communiceren met Secure Score. U ook alleen-lezen toegang toewijzen aan andere gebruikers.

* Globale beheerder
* Beveiligingsbeheerder
* Exchange-beheerder
* SharePoint-beheerder

### <a name="read-only-roles"></a>Alleen-lezen rollen

Met alleen-lezen toegang u de status of notities niet bewerken voor een verbeteringsactie, scorezones bewerken of aangepaste vergelijkingen bewerken.

* Helpdeskbeheerder
* Gebruikersbeheerder
* Servicebeheerder
* Beveiligingslezer
* Beveiligingsoperator
* Algemene lezer

### <a name="graph-api"></a>Grafiek-API

Als u toegang wilt krijgen tot de Graph API, moet u naast een rol ook een van de volgende scopes hebben:

* SecurityEvents.Read.All (voor alleen-lezen rol)
* SecurityEvents.ReadWrite.All (voor lees- en schrijffunctie)

## <a name="gain-visibility-into-your-security-posture"></a>Krijg inzicht in uw beveiligingshouding

Om u te helpen sneller de informatie te krijgen die u nodig hebt, worden microsoft-verbeteringsacties in groepen georganiseerd:

* Identiteit (Azure AD-accounts & rollen)
* Gegevens (Microsoft Information Protection)
* Apparaat (voorlopig geen verbeteringsacties)
* App (e-mail- en cloud-apps, waaronder Office 365 en Microsoft Cloud App Security)
* Infrastructuur (voorlopig geen verbeteringsacties)

Op de overzichtspagina van Microsoft Secure Score u zien hoe punten worden verdeeld tussen deze groepen en welke punten beschikbaar zijn. De overzichtspagina is ook de plek om een totaalbeeld te krijgen van de totale score, de historische trend van uw veilige score met benchmarkvergelijkingen en geprioriteerdverbeterde verbeteracties die kunnen worden uitgevoerd om uw score te verbeteren.

![](../../media/secure-score/homepage-original.png)
*Overzichtspagina* secure score homepage figuur 1: Microsoft Secure Score overzicht

## <a name="take-action-to-improve-your-score"></a>Onderneem actie om je score te verbeteren

Het tabblad Verbeteracties bevat de beveiligingsaanbevelingen die mogelijke aanvalsoppervlakken aanpakken, samen met hun status (voltooid, niet voltooid, opgelost via derden en genegeerd). U alle verbeteracties zoeken, filteren en groeperen.

### <a name="ranking"></a>Ranking

Ranking is gebaseerd op het aantal resterende punten dat nog te bereiken is, implementatieproblemen, gebruikersimpact en complexiteit. De hoogst gerangschikte verbeteringsacties hebben een groot aantal punten die met lage moeilijkheid, gebruikerseffect, en ingewikkeldheid blijven.

### <a name="actions"></a>Acties

Acties met het label [Niet gescoord] worden niet bijgehouden door Microsoft Secure Score. Je nog steeds actie ondernemen, maar het voltooien ervan heeft geen invloed op je score. Als een actie in de toekomst wordt bijgehouden door Microsoft Secure Score en u deze al hebt voltooid, wordt de wijziging automatisch weergegeven.

Wanneer u een specifieke verbeteringsactie selecteert, verschijnt er een fly out. Als u de actie wilt voltooien, hebt u een aantal opties:

1. Selecteer **Instellingen weergeven** om naar het configuratiescherm te gaan en de wijziging aan te brengen. U krijgt dan de punten die de actie waard is, zichtbaar aan de bovenkant van de fly out. Het kan tot 24 uur duren voordat u de punten bijwerkt.

2. Selecteer **Oplossen via derden** omdat de verbeteringsactie al is aangepakt door een toepassing of software van derden. U krijgt de punten die de actie waard is, zodat uw veilige score beter uw algehele beveiligingshouding weerspiegelt. Als een derde partij het besturingselement niet meer dekt, u de verbeteringsactie als niet voltooid markeren. Houd er rekening mee dat Microsoft geen inzicht heeft in de vraag of aan de scorevereisten is voldaan als de verbeteringsactie is gemarkeerd als opgelost via derden.

3. Selecteer **Negeren** omdat u hebt besloten het risico te accepteren en de verbeteringsactie niet uit te voeren. Zodra u een verbeteringsactie negeert, wordt het totale aantal veilige scorepunten dat u bereiken verminderd. U deze actie in de geschiedenis bekijken of op elk gewenst moment ongedaan maken.

4. Selecteer **Controleren** omdat de verbeteringsactie vereist dat u regelmatig een deel van uw omgeving bekijkt om punten te winnen en te behouden. De regels voor het doorsturen van postvaks moeten bijvoorbeeld wekelijks worden herzien om ervoor te zorgen dat gegevens niet uit uw netwerk worden geëfiltreerd. U hoeft geen wijzigingen aan te brengen, maar er moet wel een actie worden uitgevoerd. Als u regelmatig de regels bekijkt, ontvangt u de punten. Zo niet, dan wordt de score verlaagd.

![Voorbeeld van actie voor veilige scoreverbetering](../../media/secure-score/secure-score1x450.png) ![Voorbeeld van actie voor verbetering van de beoordeling van beveiligde scorebeoordeling](../../media/secure-score/secure-score2x450.png)

*Cijfers 2 & 3: Verbeteractie flyouts*

## <a name="monitor-improvements-over-time"></a>Verbeteringen in de loop van de tijd controleren

U een grafiek van de score van uw organisatie in de loop van de tijd bekijken op het tabblad **Geschiedenis.** Onder de grafiek vindt u een lijst met alle acties die zijn ondernomen in het geselecteerde tijdsbereik en hun kenmerken, zoals resulterende punten en categorie. U een datumbereik aanpassen en filteren op categorie.

## <a name="risk-awareness"></a>Risicobewustzijn

Microsoft Secure Score is een numeriek overzicht van uw beveiligingshouding op basis van systeemconfiguraties, gebruikersgedrag en andere beveiligingsgerelateerde metingen; het is geen absolute meting van hoe waarschijnlijk uw systeem of gegevens zullen worden geschonden. Integendeel, het vertegenwoordigt de mate waarin u beveiligingscontroles hebt aangenomen in uw Microsoft-omgeving, wat kan helpen het risico te compenseren om te worden geschonden. Geen enkele online service is volledig immuun voor inbreuken op de beveiliging, en veilige score mag niet worden geïnterpreteerd als een garantie tegen inbreuk op de beveiliging op enigerlei wijze.

## <a name="whats-new"></a>Wat is er nieuw?

Om van Microsoft Secure Score een betere vertegenwoordiger van uw beveiligingshouding te maken, hebben we een aantal wijzigingen aangebracht.

Zie Wat er komt in Microsoft Secure Score voor meer informatie over geplande [wijzigingen?](microsoft-secure-score-whats-coming.md)

### <a name="removed-not-scored-improvement-actions"></a>Verwijderde "niet gescoorde" verbeteracties

Een van de principes van Secure Score is dat de score moet worden gestandaardiseerd en gemakkelijk te relateren aan. Het hebben van verbeteringsacties die niet meetbaar of bruikbaar zijn, heeft verwarring veroorzaakt. Microsoft Secure Score heeft alleen zin wanneer elke aanbeveling een duidelijk effect op de score kan hebben. Niet gescoorde verbeteracties zijn niet meetbaar.  

Om deze redenen zijn alle verbeteracties die niet zijn gescoord verwijderd. Er is geen actie van uw kant nodig.

### <a name="removed-device-improvement-actions"></a>Acties voor apparaatverbetering verwijderen

Na een evaluatie van de microsoft Secure Score-apparaatcategorie van verbeteracties werd vastgesteld dat deze acties momenteel de beleidsstatus beoordelen en niet de configuratiestatus van apparaten. Aangezien de configuratie direct is gekoppeld aan de beveiligingshouding, waren de bestaande apparaatacties vastbesloten om de organisatiehouding niet volledig weer te geven.  We zullen de huidige acties in de apparaatcategorie verwijderen terwijl we werken aan een reeks aanbevelingen die direct diagnostische gegevens gebruiken om de beveiligingshouding van apparaten vollediger weer te geven.

De volgende verbeteracties zijn verwijderd:

- Microsoft Intune Mobile Device Management inschakelen
- Een Microsoft Intune Compliance Policy voor Android maken
- Een Microsoft Intune Compliance Policy voor Android for Work maken
- Een Microsoft Intune App Protection Policy voor Android maken
- Een Microsoft Intune App Protection Policy voor iOS maken
- Apparaten markeren zonder Microsoft Intune-nalevingsbeleid dat is toegewezen als niet-compatibel
- Een Microsoft Intune Compliance Policy voor iOS maken
- Een Microsoft Intune Compliance Policy voor macOS maken
- Een Microsoft Intune Compliance Policy voor Windows maken
- Een Microsoft Intune-configuratieprofiel voor Android maken
- Een Microsoft Intune-configuratieprofiel voor Android for Work maken
- Een Microsoft Intune-configuratieprofiel voor macOS maken
- Een Microsoft Intune-configuratieprofiel voor iOS maken
- Een Microsoft Intune-configuratieprofiel voor Windows maken
- Verbeterde jailbreakdetectie inschakelen in Microsoft Intune
- Vereisen dat alle apparaten worden gepatcht, anti-virus hebben en firewalls zijn ingeschakeld
- Windows Defender ATP-integratie inschakelen in Microsoft Intune
- Een Microsoft Intune Windows Information Protection Policy maken
- Alle apparaten verplichten geavanceerde beveiligingsconfiguraties te hebben
- Rapport geblokkeerde apparaten wekelijks controleren

### <a name="removed-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a>Verwijderde verbeteracties die niet voldoen aan de verwachtingen voor betrouwbare meting

Om ervoor te zorgen dat de Microsoft Secure Score zinvol is en dat elke verbeteringsactie meetbaar en betrouwbaar is, hebben we de volgende verbeteracties verwijderd:

- Registratie van controlegegevens inschakelen
- Ontdek riskante en niet-conforme schaduw-IT-toepassingen
- Machtigingen controleren & riskante OAuth-toepassingen blokkeren die zijn aangesloten op uw omgeving
- Versiebeheer instellen in SharePoint-onlinedocumentbibliotheken

### <a name="mfa-improvement-action-updates"></a>MFA-actie-updates voor verbetering

Om rekening te houden met de noodzaak voor bedrijven om de hoogste beveiliging te garanderen terwijl ze beleid toepassen dat met hun bedrijf werkt, heeft Microsoft Secure Score drie verbeteracties verwijderd die zijn gericht op multi-factor authenticatie en er twee toegevoegd.

Verwijderde verbeteringsacties:

- Alle gebruikers registreren voor multi-factor authenticatie
- MFA vereisen voor alle gebruikers
- MFA vereisen voor azure AD-bevoorrechte rollen

Verbeterde acties toegevoegd:

- Ervoor zorgen dat alle gebruikers meervoudige verificatie kunnen voltooien voor veilige toegang
- MFA vereisen voor administratieve rollen

 Deze nieuwe verbeteracties vereisen het registreren van uw gebruikers of beheerders voor multi-factor authenticatie (MFA) in uw directory en het vaststellen van de juiste set beleidsregels die passen bij uw organisatiebehoeften. Het belangrijkste doel is flexibiliteit te hebben en ervoor te zorgen dat al uw gebruikers en beheerders kunnen verifiëren met meerdere factoren of op risico's gebaseerde identiteitsverificatieprompts. Dat kan de vorm aannemen van meerdere beleidsregels die scoped-beslissingen toepassen, of beveiligingsstandaardinstellingen instellen (aanstaande 16 maart) waarmee Microsoft kan beslissen wanneer gebruikers voor MFA moeten worden uitdagen.

### <a name="removed-review-improvement-actions"></a>Verwijderde verbeteringsacties voor 'beoordeling'

Een van de principes van Secure Score is dat de score moet worden gestandaardiseerd en gemakkelijk te relateren aan. Het hebben van verbeteringsacties die niet meetbaar of bruikbaar zijn, heeft verwarring veroorzaakt. Eén Microsoft Secure Score heeft alleen zin wanneer elke aanbeveling een duidelijk effect op de score kan hebben. Verbeteracties beoordelen worden niet gemeten volgens dezelfde standaard als andere verbeteracties.  

Om deze redenen zijn alle verbeteracties waarvoor een revisiecadans vereist, tijdelijk verwijderd. Er is geen actie van uw kant nodig.

### <a name="preview-features"></a>Voorbeeldfuncties bekijken

De volgende functies worden opgenomen in de [preview-release:](microsoft-secure-score-preview.md)

* Alle nieuwe metrics en trends views voor CISO en lead level discussies
* Nieuwe manieren om uw score bij te houden en te benchmarken
* Betere tracking en monitoring voor scoreregressies
* Uw verbeteracties filteren, taggen, doorzoeken en groeperen
* Beheer je toekomstige doelen met behulp van scoreprojecties en geplande acties
* Vereenvoudiging van het puntensysteem
* En nog veel meer!

## <a name="we-want-to-hear-from-you"></a>We willen graag van u horen

Als je problemen hebt, laat het ons dan weten door te posten in de community [Security, Privacy & Compliance.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) We houden de gemeenschap in de gaten en zullen hulp bieden.
