---
title: Aanvalssimulatie traningimplementatieoverwegingen en veelgestelde vragen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie krijgen over implementatieoverwegingen en veelgestelde vragen over aanvalssimulatie en -training in Microsoft 365 E5 of Microsoft Defender voor Office 365 Plan 2-organisaties.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f404e2a47756a611135fc70026bf0cce3eec62c4
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204086"
---
# <a name="attack-simulation-training-deployment-considerations-and-faq"></a>Aanvalssimulatie traningimplementatieoverwegingen en veelgestelde vragen

Training voor aanvalssimulatie is [nu algemeen beschikbaar.](https://techcommunity.microsoft.com/t5/microsoft-security-and/attack-simulation-training-in-microsoft-defender-for-office-365/ba-p/2037291) Met training voor aanvalssimulatie kunnen Microsoft 365 E5- of Microsoft Defender voor Office 365 Plan 2-organisaties risico's voor sociale technologie meten en beheren door het maken en beheren van phishingsimulaties die worden mogelijk gemaakt door real-world, ontwapende phishing-payloads. Hypergerichte training, geleverd in samenwerking met De beveiliging van Terranova, helpt de kennis te verbeteren en het gedrag van werknemers te wijzigen.

Zie Aan de slag met de trainingstraining Aanvalssimulatie voor meer informatie over aan de slag gaan met de trainingstraining [aanvalssimulatie.](attack-simulation-training-get-started.md)

Hoewel de hele ervaring voor het maken en plannen van simulaties is ontworpen om vrij stromend en frictieloos te zijn, vereist het uitvoeren van simulaties op ondernemingsschaal vaak planning. Dit artikel helpt specifieke uitdagingen aan te pakken die we zien wanneer onze klanten simulaties uitvoeren in hun eigen omgeving.

## <a name="issues-with-end-user-experiences"></a>Problemen met eindgebruikerservaringen

### <a name="phishing-simulation-urls-blocked-by-google-safe-browsing"></a>URL's voor phishingsimulatie die zijn geblokkeerd door Google Safe Browsen

Een URL-reputatieservice kan een of meer URL's identificeren die door de training voor de aanvalssimulatie worden gebruikt als onveilig. Google Safe browsen in Google Chrome blokkeert enkele gesimuleerde phishing-URL's met een bericht van **de misleidende site.** Hoewel we met veel URL-reputatieleveranciers werken om altijd onze url's voor simulatie toe te staan, hebben we niet altijd volledige dekking.

![Waarschuwing voor misleidende site in Google Chrome](../../media/attack-sim-chrome-deceptive-site-message.png)

Houd er rekening mee dat dit probleem geen invloed heeft op Microsoft Edge.

Als onderdeel van de planningsfase moet u de beschikbaarheid van de URL in uw ondersteunde webbrowsers controleren voordat u de URL gebruikt in een phishingcampagne. Als de URL's worden geblokkeerd door Google Safe [browsen,](https://support.google.com/chrome/a/answer/7532419) volgt u deze richtlijnen van Google om toegang tot de URL's toe te staan.

Raadpleeg [Aan de slag met training voor aanvalssimulatie](attack-simulation-training-get-started.md) voor de lijst met URL's die momenteel worden gebruikt door de training voor de aanvalssimulatie.

### <a name="phishing-simulation-and-admin-urls-blocked-by-network-proxy-solutions-and-filter-drivers"></a>Phishingsimulatie- en beheerders-URL's die zijn geblokkeerd door netwerkproxyoplossingen en filtert stuurprogramma's

Zowel phishingsimulatie-URL's als beheerders-URL's kunnen worden geblokkeerd of gedropt door uw tussenliggende beveiligingsapparaten of filters. Bijvoorbeeld:

- Firewalls
- WAF-oplossingen (Web Application Firewall)
- Filtert stuurprogramma's van derden (bijvoorbeeld filters in de kernelmodus)

Hoewel er weinig klanten zijn geblokkeerd op deze laag, gebeurt dit wel. Als u problemen ondervindt, kunt u de volgende URL's configureren om het scannen door uw beveiligingsapparaten of filters te omzeilen:

- De gesimuleerde phishing-URL's zoals beschreven in [Aan de slag met de trainingstraining Aanvalssimulatie](attack-simulation-training-get-started.md).
- <https://security.microsoft.com/attacksimulator>
- <https://security.microsoft.com/attacksimulationreport>
- <https://security.microsoft.com/trainingassignments>

### <a name="simulation-messages-not-delivered-to-all-targeted-users"></a>Simulatieberichten die niet aan alle doelgebruikers worden bezorgd

Het is mogelijk dat het aantal gebruikers dat de e-mailberichten voor de simulatie daadwerkelijk ontvangt, kleiner is dan het aantal gebruikers dat het doel van de simulatie heeft. De volgende typen gebruikers worden uitgesloten als onderdeel van doelvalidatie:

- Ongeldige e-mailadressen van geadresseerden.
- Gastgebruikers.
- Gebruikers die niet meer actief zijn in Azure Active Directory (Azure AD).

Alleen geldige, niet-gastgebruikers met een geldig postvak worden opgenomen in de simulaties. Als u distributiegroepen of beveiligingsgroepen met e-mail gebruikt om gebruikers te targeten, kunt u de cmdlet [Get-DistributionGroupMember](/powershell/module/exchange/get-distributiongroupmember) in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) gebruiken om leden van de distributiegroep weer te geven en te valideren.

## <a name="issues-with-attack-simulation-training-reporting"></a>Problemen met de rapportage van training voor de aanvalssimulatie

### <a name="attack-simulation-training-reports-do-not-contain-any-activity-details"></a>Trainingsrapporten voor aanvalssimulaties bevatten geen activiteitendetails

Aanvalssimulatietraining wordt geleverd met uitgebreide, actievolle inzichten die u op de hoogte houden van de voortgang van de bedreigingsbereidheid van uw werknemers. Als trainingsrapporten voor aanvalssimulaties niet worden gevuld met gegevens, controleert u of de zoekopdracht in het auditlogboek is ingeschakeld in uw organisatie (deze is standaard ingeschakeld).

Auditlogboek zoeken is vereist door training voor de aanvalssimulatie, zodat gebeurtenissen kunnen worden vastgelegd, opgenomen en teruggelezen. Het uitschakelen van het zoeken naar auditlogboek heeft de volgende gevolgen voor de training voor de aanvalssimulatie:

- Rapportagegegevens zijn niet beschikbaar in alle rapporten. De rapporten worden leeg weergegeven.
- Trainingstoewijzingen worden geblokkeerd, omdat er geen gegevens beschikbaar zijn.

Zie Zoeken in auditlogboek in- of uitschakelen als u de zoekfunctie voor auditlogboek [wilt in- of uitschakelen.](../../compliance/turn-audit-log-search-on-or-off.md)

> [!NOTE]
> Lege activiteitsgegevens kunnen ook worden veroorzaakt doordat er geen E5-licenties aan gebruikers worden toegewezen. Controleer of ten minste één E5-licentie is toegewezen aan een actieve gebruiker om ervoor te zorgen dat rapportagegebeurtenissen worden vastgelegd en vastgelegd.

### <a name="simulation-reports-are-not-updated-immediately"></a>Simulatierapporten worden niet onmiddellijk bijgewerkt

Gedetailleerde simulatierapporten worden niet direct bijgewerkt nadat u een campagne hebt gestart. Maakt u zich geen zorgen; dit gedrag wordt verwacht.

Elke simulatiecampagne heeft een levenscyclus. Wanneer de simulatie voor het eerst wordt gemaakt, is de status **Gepland.** Wanneer de simulatie wordt gestart, wordt de voortgangstoestand **uitgevoerd.** Wanneer de simulatie is voltooid, wordt de status **Voltooid** uitgevoerd.

Terwijl een simulatie de status **Gepland** heeft, zijn de simulatierapporten meestal leeg. In deze fase wordt met de simulatie-engine het e-mailadres van de doelgebruiker opgelost, distributiegroepen uitgebreid, gastgebruikers uit de lijst verwijderd, enzovoort:

![Rapportage in de status Gepland](../../media/attack-sim-empty-reporting.png)

Wanneer de simulatie het stadium **In voortgang** binnenkomt, ziet u dat de informatie in de rapportage begint te druppelen:

![Rapportage in de status In progress](../../media/attack-sim-in-progress.png)

Het kan tot 30 minuten duren voordat de afzonderlijke simulatierapporten zijn bijgewerkt na de overgang naar **de status In voortgang.** De rapportgegevens blijven worden opgebouwd totdat de simulatie de status **Voltooid** heeft bereikt. Rapportage-updates vinden plaats met de volgende intervallen:

- Elke 10 minuten voor de eerste 60 minuten.
- Elke 15 minuten na 60 minuten tot 2 dagen.
- Elke 30 minuten na 2 dagen tot 7 dagen.
- Elke 60 minuten na 7 dagen.

Widgets op de **pagina Overzicht** bieden een snelle momentopname van de beveiligingshouding van uw organisatie op basis van een simulatie in de tijd. Omdat deze widgets uw algehele beveiligingshouding en reis in de tijd weerspiegelen, worden deze bijgewerkt nadat elke simulatiecampagne is voltooid.

> [!NOTE]
> U kunt de optie **Exporteren** op de verschillende rapportagepagina's gebruiken om gegevens op te halen.

### <a name="messages-reported-as-phishing-by-users-arent-appearing-in-simulation-reports"></a>Berichten die zijn gerapporteerd als phishing door gebruikers worden niet weergegeven in simulatierapporten

Simulatierapporten in de training Aanvalssimulator geven informatie over gebruikersactiviteit. Bijvoorbeeld:

- Gebruikers die op de koppeling in het bericht hebben geklikt.
- Gebruikers die hun referenties hebben opgeslagen.
- Gebruikers die het bericht als phishing hebben gerapporteerd.

Als berichten die gebruikers als phishing hebben gerapporteerd, niet worden vastgelegd in trainingssimulatierapporten voor aanvallen, is er mogelijk een Exchange-regel voor de e-mailstroom (ook wel een transportregel genoemd) die de bezorging van de gerapporteerde berichten aan Microsoft blokkeert. Controleer of e-mailstroomregels de bezorging van de volgende e-mailadressen niet blokkeren:

- junk@office365.microsoft.com
- abuse@messaging.microsoft.com
- phish@office365.microsoft.com
- niet \_ junk@office365.microsoft.com

## <a name="other-frequently-asked-questions"></a>Andere veelgestelde vragen

### <a name="q-what-is-the-recommended-method-to-target-users-for-simulation-campaigns"></a>V: Wat is de aanbevolen methode om gebruikers te targeten voor simulatiecampagnes?

A: Er zijn verschillende opties beschikbaar voor doelgebruikers:

- Alle gebruikers opnemen (momenteel beschikbaar voor organisaties met minder dan 40.000 gebruikers).
- Kies specifieke gebruikers.
- Selecteer gebruikers in een CSV-bestand.
- Targeting op basis van Azure AD-groep.

We hebben vastgesteld dat campagnes waarbij de beoogde gebruikers worden geïdentificeerd door Azure AD-groepen, over het algemeen gemakkelijker te beheren zijn.

### <a name="q-are-there-any-limits-in-targeting-users-while-importing-from-a-csv-or-adding-users"></a>V: Zijn er limieten voor het targeten van gebruikers tijdens het importeren van een CSV of het toevoegen van gebruikers?

A: De limiet voor het importeren van geadresseerden uit een CSV-bestand of het toevoegen van afzonderlijke geadresseerden aan een simulatie is 40.000.

Een geadresseerde kan een individuele gebruiker of een groep zijn. Een groep kan honderden of duizenden geadresseerden bevatten, zodat er geen werkelijke limiet wordt geplaatst voor het aantal afzonderlijke gebruikers.

Het beheren van een groot CSV-bestand of het toevoegen van veel afzonderlijke geadresseerden kan lastig zijn. Als u Azure AD-groepen gebruikt, wordt het algehele beheer van de simulatie vereenvoudigd.

### <a name="q-does-microsoft-provide-payloads-in-other-languages"></a>V: Levert Microsoft payloads in andere talen?

A: Er zijn momenteel 5 gelokaliseerde payloads beschikbaar. We hebben gemerkt dat directe of automatische vertalingen van bestaande payloads naar andere talen leiden tot onnauwkeurigheden en verminderde relevantie.

Dat gezegd hebbende, kunt u uw eigen payload maken in de taal van uw keuze met behulp van de aangepaste ervaring voor het maken van laadvermogen. We raden u ook ten zeerste aan om bestaande payloads te gebruiken die zijn gebruikt om gebruikers in een bepaalde geografie te targeten. Met andere woorden: laat de aanvallers de inhoud voor u localiseren.

### <a name="q-how-can-i-switch-to-other-languages-for-my-admin-portal-and-training-experience"></a>V: Hoe kan ik overschakelen naar andere talen voor mijn beheerportal en trainingservaring?

A: In Microsoft 365 of Office 365 is taalconfiguratie specifiek en gecentraliseerd voor elk gebruikersaccount. Zie Uw weergavetaal en tijdzone wijzigen in Microsoft 365 voor Bedrijven voor instructies over het wijzigen [van de taalinstelling.](https://support.microsoft.com/office/6f238bff-5252-441e-b32b-655d5d85d15b)

Houd er rekening mee dat het 30 minuten kan duren voordat de configuratiewijziging voor alle services wordt gesynchroniseerd.

### <a name="q-can-i-trigger-a-test-simulation-to-understand-what-it-looks-like-prior-to-launching-a-full-fledged-campaign"></a>V: Kan ik een testsimulatie activeren om te begrijpen hoe deze eruitziet voordat ik een volledige campagne start?

A: Ja dat kan! Op de laatste pagina **Controlesimulatie** in de wizard om een nieuwe simulatie te maken, is er een optie om **een test te verzenden.** Met deze optie wordt een voorbeeld van een phishingsimulatiebericht naar de momenteel aangemelde gebruiker gestuurd. Nadat u het phishingbericht in uw Postvak IN hebt gevalideerd, kunt u de simulatie indienen.

![Een testknop verzenden op de pagina Controlesimulatie](../../media/attack-sim-review-simulation-page.png)

### <a name="q-can-i-target-users-that-belong-to-a-different-tenant-as-part-of-the-same-simulation-campaign"></a>V: Kan ik gebruikers targeten die deel uitmaken van een andere tenant als onderdeel van dezelfde simulatiecampagne?

A: Nee. Op dit moment worden cross-tenantsimulaties niet ondersteund. Controleer of al uw beoogde gebruikers zich in dezelfde tenant hebben. Alle gebruikers van verschillende tenants of gastgebruikers worden uitgesloten van de simulatiecampagne.

### <a name="q-how-does-region-aware-delivery-work"></a>V: Hoe werkt bezorging op regio-bewust?

A: Regiobewuste bezorging gebruikt het kenmerk TimeZone van het postvak van de beoogde gebruiker en 'not before' logica om te bepalen wanneer het bericht moet worden bezorgd. Houd bijvoorbeeld rekening met het volgende scenario:

- Om 7:00 uur in de pacific time zone (UTC-8) maakt en plant een beheerder een campagne om op dezelfde dag om 9:00 uur te beginnen.
- UserA bevindt zich in de oostelijke tijdzone (UTC-5).
- UserB bevindt zich ook in de pacific time zone.

Om 9:00 uur op dezelfde dag wordt het simulatiebericht verzonden naar UserB. Met regiobewuste bezorging wordt het bericht niet op dezelfde dag naar UserA verzonden, omdat 9:00 am Pacific time 12:00 uur 12:00 uur Oostelijke tijd is. In plaats daarvan wordt het bericht verzonden naar UserA om 9:00 am Eastern time op de volgende dag.

Dus tijdens de eerste run van een campagne met regiobewuste bezorging ingeschakeld, lijkt het erop dat het simulatiebericht alleen is verzonden naar gebruikers in een bepaalde tijdzone. Maar naarmate de tijd verstrijkt en er meer gebruikers in het bereik komen, worden de beoogde gebruikers groter.