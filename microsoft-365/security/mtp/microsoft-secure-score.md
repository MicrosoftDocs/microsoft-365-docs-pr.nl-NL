---
title: Microsoft Secure Score
description: Beschrijft de Microsoft Secure Score in het Microsoft 365-beveiligingscentrum, hoe details worden berekend en wat beveiligingsbeheerders kunnen verwachten.
keywords: beveiliging, malware, Microsoft 365, M365, beveiligde score, beveiligingscentrum, verbeteringsacties
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
ms.openlocfilehash: 2094549e63be0a8e3c2bbc7997de13475c19bb0c
ms.sourcegitcommit: d1909d34ac0cddeb776ff5eb8414bfc9707d5ac1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/07/2020
ms.locfileid: "43163896"
---
# <a name="microsoft-secure-score"></a>Microsoft Secure Score

Microsoft Secure Score is een meting van de beveiligingshouding van een organisatie, met een hoger aantal dat aangeeft dat er meer verbeteracties zijn uitgevoerd. Het volgen van de aanbevelingen voor beveiligingsscore kan uw organisatie beschermen tegen bedreigingen. Vanuit een gecentraliseerd dashboard in het Microsoft 365-beveiligingscentrum kunnen organisaties de beveiliging van hun Microsoft 365-identiteiten, gegevens, apps, apparaten en infrastructuur bewaken en eraan werken.

Secure Score helpt organisaties:

* Rapport over de huidige status van de beveiligingshouding van de organisatie.
* Verbeter hun beveiligingshouding door vindbaarheid, zichtbaarheid, begeleiding en controle te bieden.  
* Vergelijk met benchmarks en stel key performance indicators (KPI's) vast.

Organisaties krijgen toegang tot robuuste visualisaties van statistieken en trends, integratie met andere Microsoft-producten, scorevergelijking met vergelijkbare organisaties en nog veel meer. De score kan ook worden weergegeven wanneer oplossingen van derden aanbevolen acties hebben aangepakt.

Bovendien u toegang krijgen tot uw aanbevelingen en score via de [Microsoft Graph API.](https://www.microsoft.com/security/partnerships/graph-security-api) Meer informatie over het [resourcetype Beveiligde score](https://go.microsoft.com/fwlink/?linkid=2092996).

## <a name="how-it-works"></a>Hoe het werkt

U krijgt punten voor het configureren van aanbevolen beveiligingsfuncties, het uitvoeren van beveiligingsgerelateerde taken (zoals het bekijken van rapporten) of het aanpakken van de verbeteringsactie met een toepassing of software van derden. Sommige verbeteringsacties geven alleen punten wanneer ze volledig zijn voltooid, en sommige geven gedeeltelijke punten als ze zijn voltooid voor sommige apparaten of gebruikers.

We laten u de volledige set mogelijke verbeteringen zien, ongeacht de licentie, zodat u de beste beveiligingsprocedures begrijpen en uw score verbeteren. Uw absolute beveiligingshouding wordt vertegenwoordigd door Secure Score, die hetzelfde blijft, ongeacht de productlicenties die uw organisatie bezit. Houd er rekening mee dat beveiliging moet worden afgewogen tegen bruikbaarheid, en niet elke aanbeveling kan werken voor uw omgeving.

Uw score wordt in realtime bijgewerkt om de informatie weer te geven die wordt gepresenteerd in de actiepagina's voor visualisaties en verbeteringen. Secure Score synchroniseert ook dagelijks om systeemgegevens over uw behaalde punten voor elke actie te ontvangen.

### <a name="how-improvement-actions-are-scored"></a>Hoe verbeteracties worden beoordeeld

De meeste worden op een binaire manier gescoord - als u de verbeteringsactie implementeert, zoals een nieuw beleid maken of een specifieke instelling inschakelen, krijgt u 100% van de punten. Voor andere verbeteringsacties worden punten gegeven als percentage van de totale configuratie. Bijvoorbeeld, als de verbetering actie staat krijg je 30 punten door het beschermen van al uw gebruikers met multi-factor authenticatie en je hebt slechts 5 van de 100 totale gebruikers beschermd, zou je een gedeeltelijke score van ongeveer 2 punten (5 beschermd / 100 totaal * 30 max pts = 2 pts partiële score).

### <a name="products-included-in-secure-score"></a>Producten opgenomen in Secure Score

Momenteel zijn er aanbevelingen voor Office 365 (waaronder SharePoint Online, Exchange Online, OneDrive voor Bedrijven, Microsoft Information Protection en meer), Azure AD en Cloud App Security. Aanbevelingen voor andere beveiligingsproducten, zoals Azure ATP en Microsoft Defender ATP, komen binnenkort. De aanbevelingen hebben niet betrekking op alle aanvalsoppervlakken die aan elk product zijn gekoppeld, maar ze zijn een goede basislijn. U de verbeteringsacties ook markeren als gedekt door een derde partij.

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

* SecurityEvents.Read.All (voor alleen-lezen rol)
* SecurityEvents.ReadWrite.All (voor lees- en schrijfrol)

## <a name="gain-visibility-into-your-security-posture"></a>Krijg inzicht in uw beveiligingshouding

Om u te helpen sneller de informatie te verzamelen die u nodig hebt, worden microsoft-verbeteringsacties in groepen georganiseerd:

* Identiteit (Azure AD-accounts & rollen)
* Gegevens (Microsoft-informatiebeveiliging)
* Apparaat (voorlopig geen verbeteringsacties)
* App (e-mail- en cloud-apps, waaronder Office 365 en Microsoft Cloud App Security)
* Infrastructuur (voorlopig geen verbeteracties)

Op de overzichtspagina van Microsoft Secure Score u zien hoe punten worden verdeeld over deze groepen en welke punten beschikbaar zijn. De overzichtspagina is ook de plek om een totaalbeeld te krijgen van de totale score, historische trend van uw beveiligde score met benchmarkvergelijkingen en geprioritteerde verbeteringsacties die kunnen worden ondernomen om uw score te verbeteren.

![Overzichtspagina](../../media/secure-score/homepage-original.png)
van de beveiligde score*homepage figuur 1: Microsoft Secure Score*

## <a name="take-action-to-improve-your-score"></a>Onderneem actie om je score te verbeteren

Het tabblad Verbeteringsacties bevat de beveiligingsaanbevelingen die mogelijke aanvalsoppervlakken aanpakken, samen met hun status (voltooid, niet voltooid, opgelost via derden en genegeerd). U alle verbeteringsacties zoeken, filteren en groeperen.

### <a name="ranking"></a>Ranking

Ranking is gebaseerd op het aantal resterende punten te bereiken, implementatie moeilijkheid, impact van de gebruiker, en complexiteit. De hoogst gerangschikte verbeteringsacties hebben een groot aantal resterende punten met lage moeilijkheidsgraad, impact van de gebruiker en complexiteit.

### <a name="actions"></a>Acties

Acties met het label [Niet gescoord] worden niet bijgehouden door Microsoft Secure Score. Je nog steeds actie ondernemen, maar het voltooien ervan heeft geen invloed op je score. Als een actie in de toekomst wordt bijgehouden door Microsoft Secure Score en u deze al hebt voltooid, wordt de wijziging automatisch weergegeven door uw beveiligde score.

Wanneer u een specifieke verbeteringsactie selecteert, wordt er een fly-out weergegeven. Als u de actie wilt voltooien, hebt u een aantal opties:

1. Selecteer **Weergave-instellingen** om naar het configuratiescherm te gaan en de wijziging aan te brengen. U krijgt dan de punten die de actie waard is, zichtbaar aan de bovenkant van de fly out. Het kan tot 24 uur duren voordat punten zijn bijgewerkt.

2. Selecteer **Oplossen via derden** omdat de verbeteringsactie al is aangepakt door een toepassing of software van derden. U krijgt de punten die de actie waard is, zodat uw veilige score beter weerspiegelt uw algehele veiligheid houding. Als een derde partij het besturingselement niet meer dekt, u de verbeteringsactie markeren als niet voltooid. Houd er rekening mee dat Microsoft geen inzicht heeft in de vraag of aan de scorevereisten is voldaan als de verbeteringsactie is gemarkeerd als opgelost door derden.

3. Selecteer **Negeren** omdat u hebt besloten het risico te accepteren en de verbeteringsactie niet uit te voeren. Zodra u een verbeteringsactie negeert, wordt het totale aantal veilige scorepunten dat u bereiken verminderd. U deze actie in de geschiedenis bekijken of op elk gewenst moment ongedaan maken.

4. Selecteer **Controleren** omdat u door de verbeteringsactie regelmatig een deel van uw omgeving moet controleren om punten te winnen en te behouden. Postvakdoorstuurregels moeten bijvoorbeeld wekelijks worden gecontroleerd om ervoor te zorgen dat gegevens niet worden geëexfiltreerd uit uw netwerk. U hoeft geen wijzigingen aan te brengen, maar er moet wel een actie worden uitgevoerd. Als u de regels regelmatig bekijkt, ontvangt u de punten. Zo niet, dan wordt de score verlaagd.

![Voorbeeld van actie voor verbetering van de veilige score](../../media/secure-score/secure-score1x450.png) ![Voorbeeld van het actievoorbeeld van Secure Score review-verbetering](../../media/secure-score/secure-score2x450.png)

*Cijfers 2 & 3: Verbetering actie flyouts*

## <a name="monitor-improvements-over-time"></a>Verbeteringen in de loop van de tijd bewaken

U een grafiek van de score van uw organisatie in de loop van de tijd bekijken op het tabblad **Historie.** U een datumbereik aanpassen en filteren op categorie.

## <a name="risk-awareness"></a>Risicobewustzijn

Microsoft Secure Score is een numerieke samenvatting van uw beveiligingshouding op basis van systeemconfiguraties, gebruikersgedrag en andere beveiligingsgerelateerde metingen; het is geen absolute meting van hoe waarschijnlijk uw systeem of gegevens zullen worden geschonden. Het vertegenwoordigt in plaats daarvan de mate waarin u beveiligingscontroles hebt aangenomen in uw Microsoft-omgeving, wat kan helpen het risico op schending te compenseren. Geen enkele online service is volledig immuun voor inbreuken op de beveiliging, en veilige score mag op geen enkele manier worden geïnterpreteerd als een garantie tegen inbreuk op de beveiliging.

## <a name="whats-new"></a>Wat is er nieuw?

Om van Microsoft Secure Score een betere vertegenwoordiger van uw beveiligingshouding te maken, hebben we enkele wijzigingen aangebracht.

Zie Wat komt er in Microsoft Secure Score voor meer informatie over geplande [wijzigingen?](microsoft-secure-score-whats-coming.md)

### <a name="march-2020"></a>Maart 2020

#### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a>Ondersteuning van beveiligingsstandaardinstellingen voor Azure AD-verbeteringsacties

Microsoft Secure Score werkt verbeteringsacties bij om [beveiligingsstandaards in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)te ondersteunen, waardoor het eenvoudiger wordt om uw organisatie te beschermen met vooraf geconfigureerde beveiligingsinstellingen voor veelvoorkomende aanvallen.

Het zal van invloed zijn op de volgende verbeteringsacties:

- Zorg ervoor dat alle gebruikers multi-factor authenticatie kunnen voltooien voor veilige toegang
- MFA vereisen voor administratieve rollen
- Beleid inschakelen om verouderde verificatie te blokkeren

#### <a name="removed-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a>Verwijderde verbeteringsacties die niet voldoen aan de verwachtingen voor betrouwbare metingen of geen nuttige weergave van de beveiligingshouding bieden

Om ervoor te zorgen dat de Microsoft Secure Score zinvol is en dat elke verbeteringsactie meetbaar en betrouwbaar is, verwijderen we de volgende verbeteringsacties.

- Gebruikersdocumenten opslaan in OneDrive voor Bedrijven
- Office 365 ATP-beleid voor veilige bijlagen instellen
- Veilige koppelingen voor Office 365 instellen om URL's te verifiëren
- Postvakdelegatie niet toestaan
- Anonieme koppelingen voor het delen van gasten toestaan voor sites en documenten
- Beveiligingconsole van Cloud App inschakelen
- Verlooptijd configureren voor externe koppelingen voor delen
- Controlegegevensregistratie inschakelen
- Ontdek risicovolle en niet-conforme schaduw-IT-toepassingen
- Machtigingen controleren & riskante OAuth-toepassingen blokkeren die zijn verbonden met uw omgeving
- Versiebeheer instellen in SharePoint-onlinedocumentbibliotheken

#### <a name="removed-not-scored-improvement-actions"></a>Verwijderde "niet gescoorde" verbeteringsacties

Een van de principes van Secure Score is dat de score gestandaardiseerd en gemakkelijk te relateren aan. Het hebben van verbeteringsacties die niet meetbaar of uitvoerbaar zijn, heeft verwarring veroorzaakt. Microsoft Secure Score heeft alleen zin wanneer elke aanbeveling een duidelijk effect op de score kan hebben. Niet gescoorde verbeteracties zijn niet meetbaar.  

Om deze redenen zijn alle verbeteringsacties die niet zijn gescoord, verwijderd. Er is geen actie nodig van uw kant.

#### <a name="removed-device-improvement-actions"></a>Verwijderde acties voor apparaatverbetering

Na een evaluatie van de categorie verbeteringsacties van het Microsoft Secure Score-apparaat werd vastgesteld dat deze acties momenteel de beleidsstatus en niet de configuratiestatus van apparaten beoordelen. Aangezien de configuratie rechtstreeks is gekoppeld aan de beveiligingshouding, werden de bestaande apparaatacties bepaald om de organisatorische houding niet volledig weer te geven.  We zullen het verwijderen van de huidige acties in de categorie apparaat als we werken aan een reeks aanbevelingen die rechtstreeks gebruik maken van diagnostische gegevens om meer volledig vertegenwoordigen apparaat beveiliging houding.

De volgende verbeteringsacties zijn verwijderd:

- Microsoft Intune Mobile Device Management inschakelen
- Een Microsoft Intune-nalevingsbeleid voor Android maken
- Een Microsoft Intune-nalevingsbeleid voor Android voor werk maken
- Een Microsoft Intune-appbeveiligingsbeleid voor Android maken
- Een Microsoft Intune-appbeveiligingsbeleid voor iOS maken
- Apparaten markeren zonder Microsoft Intune-nalevingsbeleid dat is toegewezen als niet-compatibel
- Een Microsoft Intune-nalevingsbeleid voor iOS maken
- Een Microsoft Intune-nalevingsbeleid voor macOS maken
- Een Microsoft Intune-nalevingsbeleid voor Windows maken
- Een Microsoft Intune-configuratieprofiel voor Android maken
- Een Microsoft Intune-configuratieprofiel voor Android for Work maken
- Een Microsoft Intune-configuratieprofiel voor macOS maken
- Een Microsoft Intune-configuratieprofiel voor iOS maken
- Een Microsoft Intune-configuratieprofiel voor Windows maken
- Verbeterde jailbreakdetectie inschakelen in Microsoft Intune
- Vereisen dat alle apparaten worden gepatcht, anti-virus hebben en firewalls zijn ingeschakeld
- Windows Defender ATP-integratie inschakelen in Microsoft Intune
- Een Microsoft Intune Windows-beleid voor informatiebescherming maken
- Vereisen dat alle apparaten geavanceerde beveiligingsconfiguraties hebben
- Wekelijks rapport over geblokkeerde apparaten bekijken

#### <a name="mfa-improvement-action-updates"></a>UPDATE-updates voor MFA-verbeteringsacties

Om rekening te houden met de noodzaak voor bedrijven om de grootst mogelijke beveiliging te garanderen en tegelijkertijd beleid toe te passen dat met hun bedrijf werkt, heeft Microsoft Secure Score drie verbeteringsacties verwijderd die zijn gecentreerd op multi-factor authenticatie en twee toegevoegd.

Verwijderde verbeteringsacties:

- Alle gebruikers registreren voor meervoudige verificatie
- MFA vereisen voor alle gebruikers
- MFA vereisen voor ad-bevoegdheden van Azure

Extra verbeteringsacties:

- Zorg ervoor dat alle gebruikers multi-factor authenticatie kunnen voltooien voor veilige toegang
- MFA vereisen voor administratieve rollen

 Deze nieuwe verbeteringsacties vereisen het registreren van uw gebruikers of beheerders voor multi-factor authenticatie (MFA) in uw directory en het vaststellen van de juiste set beleidsregels die passen bij uw organisatiebehoeften. Het belangrijkste doel is flexibiliteit te hebben en ervoor te zorgen dat al uw gebruikers en beheerders kunnen verifiëren met meerdere factoren of op risico's gebaseerde identiteitsverificatieprompts. Dat kan de vorm aannemen van meerdere beleidsregels die scoped-beslissingen toepassen of beveiligingsstandaards instellen (komende 16 maart) waarmee Microsoft kan beslissen wanneer gebruikers voor MFA worden uitdaagd.

#### <a name="removed-review-improvement-actions"></a>Verwijderde verbeteringsacties voor 'beoordeling'

Een van de principes van Secure Score is dat de score gestandaardiseerd en gemakkelijk te relateren aan. Het hebben van verbeteringsacties die niet meetbaar of uitvoerbaar zijn, heeft verwarring veroorzaakt. Eén Microsoft Secure Score heeft alleen zin als elke aanbeveling een duidelijk effect op de score kan hebben. Verbeterverbeteringsacties worden niet gemeten volgens dezelfde standaard als andere verbeteringsacties.  

Om deze redenen zijn alle verbeteringsacties waarvoor een beoordelingscadans nodig was, tijdelijk verwijderd. Er is geen actie nodig van uw kant.

### <a name="preview-features"></a>Voorbeeldfuncties

De volgende functies worden opgenomen in de [preview-release:](microsoft-secure-score-preview.md)

* Alle nieuwe statistieken en trends weergaven voor CISO en lead level discussies
* Nieuwe manieren om je score bij te houden en te benchmarken
* Betere tracking en monitoring voor scoreregressies
* Uw verbeteringsacties filteren, taggen, zoeken en groeperen
* Beheren naar uw toekomstige doelen met behulp van scoreprojecties en geplande acties
* Vereenvoudiging van het puntensysteem
* En meer!

## <a name="we-want-to-hear-from-you"></a>We willen graag van je horen

Als je problemen hebt, laat het ons dan weten door te posten in de [community Beveiliging, Privacy & Compliance.](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/bd-p/security_privacy) We houden de gemeenschap in de gaten en zullen hulp bieden.
