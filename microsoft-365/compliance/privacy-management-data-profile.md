---
title: Persoonlijke gegevens zoeken en visualiseren in Microsoft-privacybeheer (voorbeeld)
f1.keywords:
- CSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- M365-privacy-management
search.appverid:
- MOE150
- MET150
description: Meer informatie over het overzicht en het gegevensprofiel in privacybeheer en hoe u inzicht krijgt in de persoonsgegevens in de Microsoft 365 uw organisatie.
ms.openlocfilehash: d8ea8d3306840244aff7621a12702d0ca19062c0
ms.sourcegitcommit: 022d9d91263994c48efcebe08a84319573dc3a8c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53378507"
---
# <a name="find-and-visualize-personal-data-in-privacy-management-preview"></a>Persoonlijke gegevens zoeken en visualiseren in privacybeheer (voorbeeld)

In dit artikel: meer informatie  over de functies van de overzichts- en gegevensprofielpagina's en hoe ze inzicht kunnen geven in uw gegevens. 

## <a name="purpose-of-the-overview-and-data-profile"></a>Doel van het overzichts- en gegevensprofiel

Microsoft 365 privacybeheer biedt u mogelijkheden om de persoonlijke gegevens in uw omgeving te zoeken en te visualiseren. De oplossing automatiseert de detectie van persoonlijke gegevensactiva in Exchange, SharePoint, OneDrive en Teams en biedt dashboards die belangrijke inzichten geven in de gegevens. Uw privacybeheerders kunnen deze inzichten gebruiken om de privacybenadering van uw organisatie te versterken en risico's te beperken.

### <a name="overview-page"></a>Overzichtspagina

De pagina Overzicht fungeert als een algemeen dashboard voor de oplossing voor privacybeheer, zodat dynamische inzichten over het ecosysteem van persoonlijke gegevens van uw organisatie worden weergegeven. Privacybeheerders kunnen gegevenstrends en -activiteiten bewaken, mogelijke risico's voor persoonlijke gegevens identificeren en onderzoeken en belangrijke activiteiten, zoals beleidsbeheer of acties voor het aanvragen van onderwerprechten, gebruiken. Zie De overzichtspagina verkennen voor meer informatie op de [overzichtspagina.](#explore-the-overview-page)

### <a name="data-profile-page"></a>Pagina Gegevensprofiel

De pagina gegevensprofiel in privacybeheer biedt een momentopnameweergave van de persoonlijke gegevens die uw organisatie op Microsoft 365. Op deze manier kunt u visualiseren waar persoonlijke gegevens zich leven, welke typen het meest voorkomen in uw organisatie en hoeveel verschillende typen er zijn in uw Microsoft 365 services. U kunt ook persoonlijke gegevens vanaf deze locatie verkennen. Zie De pagina gegevensprofiel verkennen voor [meer informatie.](#explore-the-data-profile-page)

## <a name="explore-the-overview-page"></a>De overzichtspagina verkennen

De overzichtspagina bestaat uit drie hoofdsecties. Tegels boven aan de pagina bevatten essentiële recente statistieken over uw gegevens. De sectie Key Insights biedt onderzoeksmogelijkheden voor trends en gebieden die van groot belang zijn. Raadpleeg de trendlijngrafieken voor meer informatie over uw gegevensomgeving. Raadpleeg de onderstaande secties voor meer informatie over deze gebieden.

### <a name="top-tiles"></a>Bovenste tegels

#### <a name="policy-matches-over-past-7-days"></a>Beleidswedstrijden in de afgelopen 7 dagen

Wanneer beleidsregels zijn ingesteld in privacybeheer, worden uw gegevens geëvalueerd op bepaalde voorwaarden die privacyrisico's kunnen met zich meebrengen. Beleidswedstrijden geven aan dat gegevens worden ontdekt die mogelijk nader moeten worden beoordeeld of moeten worden gesaneerd. Op deze kaart ziet u het aantal beleidswedstrijden dat zich in de afgelopen zeven dagen heeft voorgedaan. Overeenkomsten worden hier opgedoken, ongeacht of beleid is aan- of uitgevoerd in de testmodus, zodat u de resultaten van al uw actieve beleid kunt zien. Als u op deze tegel klikt, gaat u naar een gefilterde weergave van de pagina Beleid van privacybeheer, met het beleid dat de afgelopen zeven dagen een overeenkomst heeft gehad.

#### <a name="items-with-personal-data"></a>Items met persoonlijke gegevens

Als u de geautomatiseerde detectiemogelijkheden van de privacybeheeroplossing op het werk wilt zien, bekijkt u de tegel Items met persoonlijke gegevens. Op deze manier wordt weergegeven hoeveel nieuwe items met persoonlijke gegevens zijn gevonden in de Microsoft 365 van uw organisatie in de afgelopen zeven dagen. Als u op deze tegel klikt, wordt een weergave geladen van de nieuwste 100 items die zijn gevonden.

#### <a name="subject-rights-requests"></a>Verzoeken om rechten van onderwerp

De bovenste tegels van de overzichtspagina bevatten twee tegels die betrekking hebben op aanvragen voor onderwerprechten. De eerste toont het aantal aanvragen dat de afgelopen zeven dagen is gemaakt. De tweede tegel wordt hoger weergegeven dan aanvragen die te laat zijn en die mogelijk direct aandacht nodig hebben. Als u op deze tegels klikt, hebben gebruikers de juiste machtigingen nodig voor de pagina met het verzoek om privacy.

### <a name="key-insights"></a>Belangrijke inzichten

#### <a name="content-items-with-the-most-personal-data"></a>Inhoudsitems met de meest persoonlijke gegevens

Inhoud in de Microsoft 365 van uw organisatie die een grote hoeveelheid persoonlijke gegevens bevat, kan een hoger risico op blootstelling met zich brengen. Mogelijk wilt u deze items controleren om ervoor te zorgen dat deze worden gedekt door een privacybeleid. Om deze items onder de aandacht te brengen, biedt de overzichtspagina een weergave van uw inhoudsitems met de meest persoonlijke gegevens. Hier ziet u het aantal unieke typen persoonlijke gegevens dat is gedetecteerd, hoeveel unieke inhoudseigenaren zijn geïdentificeerd en hoeveel gegevensonderwerpen zijn geïdentificeerd op basis van de instellingen voor gegevensmatching voor aanvragen voor onderwerprechten.

Selecteer Overzicht weergeven voor een overzichtsweergave van de gevonden items. U kunt er ook voor kiezen om deze bevindingen te verkennen om een voorbeeld van afzonderlijke bestanden te bekijken. In deze weergave ziet u een maximum van 100 items. Gebruikers in de rollengroep Privacybeheer kunnen bestanden selecteren om details te bekijken en relevantie te bepalen, en de lijst exporteren in .csv indeling voor verwijzing.

#### <a name="policies-with-the-most-matches-in-the-last-week"></a>Beleid met de meeste overeenkomsten in de afgelopen week

In dit inzicht wordt getoond welke beleidsregels de afgelopen zeven dagen het vaakst zijn afgestemd, in de modus 'Aan' of 'Testen'. Op deze manier kunt u zowel de prestaties van uw beleid als de effecten van doorlopend werk illustreren wanneer uw privacybeheergebruikers training ontvangen en zijn ze in staat om problemen met inhoud op te lossen en hun privacygedrag te verfijnen.

Selecteer Overzicht weergeven voor een overzicht van de tien belangrijkste beleidsregels die zijn gekoppeld en de inhoudseigenaren van de bijbehorende inhoud. U ziet ook hoeveel gebruikersmeldingen zijn verzonden als gevolg van deze beleidswedstrijden en hoeveel gebruikersacties zijn ondernomen. Selecteer Onderzoeken om de beleidspagina weer te geven in privacybeheer, gefilterd om het beleid weer te geven vanuit de overzichtsweergave. Deze onderzoeksweergave toont statistieken voor de volledige levensduur van het beleid. Selecteer deze optie om details te zien, zoals wanneer overeenkomende items in eerste instantie zijn gedetecteerd.

#### <a name="users-with-the-most-policy-matched-in-the-last-week"></a>Gebruikers met het meest overeenkomende beleid in de afgelopen week

Dit inzicht heeft ook betrekking op overeenkomsten met beleidsregels in de modus 'Testen' of 'Aan'. Hiermee kunt u een overzicht bekijken van de gebruikers met de meeste beleidsregels van de afgelopen week en welk beleid ze overeenkomen. Dit omvat totalen van de eigenaren van unieke inhoud, meldingen die naar deze gebruikers zijn verzonden en hoeveel acties er zijn ondernomen vanuit deze meldingen. Als u Onderzoeken selecteert, gaat u naar de pagina Beleid, gefilterd om het beleid weer te geven vanuit de overzichtsweergave. In de onderzoeksweergave vindt u geen gebruikersgegevens, maar kunt u een beleid selecteren om beleidsdetails te zien die betrekking hebben op deze overeenkomsten.

#### <a name="items-with-the-most-data-subject-content"></a>Items met de meeste inhoud van het onderwerp

Dit inzicht betreft informatie uit de functie gegevensmatching in aanvragen voor onderwerprechten en items die zijn gevonden in Microsoft 365 die de meeste gegevensonderwerpen in hun inhoud bevatten. Zie Aanvragen voor onderwerprechten beheren voor meer informatie over [deze instelling.](privacy-management-subject-rights-requests.md)

Met deze items kunt u uw configuratie voor gegevensmatching bevestigen en kunt u privacyrisico's met betrekking tot deze items beperken. Selecteer Overzicht weergeven voor een overzichtsweergave. Selecteer Verkennen voor een gedetailleerde weergave van maximaal 100 van deze items. Hier kunt u een voorbeeld van deze items bekijken en de relevantie bepalen en de lijst exporteren in .csv indeling.

### <a name="trendline-graphs"></a>Trendlijngrafieken

Raadpleeg de trendlijngrafieken voor dynamische visualisaties van trends in de gegevens van uw organisatie. Deze grafieken kunnen worden gefilterd op kenmerken die relevant zijn voor de verstrekte gegevens, zoals tijdsspanne, gegevenstype of de locaties van gegevens. Gebruik de vervolgkeuzen om de weergave aan te passen. Als u de muisaanwijzer op lijnen in de grafiek houdt, kunt u statistieken zien die betrekking hebben op dat specifieke punt in de tijd.

Resultaten met betrekking tot beleidsregels bevatten gegevens uit beleidsregels in de modus Testen en Aan. Als er geen beleid van een bepaald type actief is, worden in de gerelateerde grafieken geen resultaten weergegeven.

#### <a name="active-policy-alerts"></a>Actieve beleidswaarschuwingen

In dit gebied ziet u een momentopname van actieve waarschuwingen die worden geactiveerd door beleidswedstrijden. Met deze weergave kunt u na een tijdsweergave gemakkelijker afwijkingen opsporen, zoals grote pieken in volume. Selecteer Waarschuwingen weergeven om naar de beleidspagina binnen privacybeheer te gaan, waar u waarschuwingen verder kunt onderzoeken en problemen kunt maken voor herstel.

#### <a name="personal-data-found-in-organization"></a>Persoonsgegevens gevonden in organisatie

In deze grafiek ziet u trends in hoeveel persoonlijke gegevens in de afgelopen tijd zijn ontdekt in uw Microsoft 365 omgeving en waar deze zich bevinden. De inhoud wordt ingevuld nadat privacybeheer al voldoende tijd is uitgevoerd en nadat inhoud met persoonlijke gegevens is gevonden binnen SharePoint, OneDrive, Teams en/of Exchange.

#### <a name="data-transfers-detected-in-organization"></a>Gegevensoverdrachten gedetecteerd in organisatie

Deze grafiek is gerelateerd aan beleid voor gegevensoverdracht. Het biedt een overzicht van de manier waarop gegevens binnen uw organisatie worden verplaatst, tussen afdelingen of tussen regio's voor multi-geo-organisaties.

#### <a name="unused-personal-data"></a>Ongebruikte persoonlijke gegevens

Deze grafiek is gerelateerd aan beleid voor gegevensminimatie. Het geeft inzicht in hoe uw organisatie inhoud met persoonlijke gegevens opslaat en hoe uw beleid de verwerking van deze gegevens in de tijd kan verbeteren.

#### <a name="overexposed-personal-data"></a>Overbelichte persoonlijke gegevens

Deze grafiek is gerelateerd aan beleid voor gegevens overbelichting. Het kan u helpen bij het identificeren van het gedrag van delen in de tijd binnen uw organisatie en locaties waar inhoud met persoonlijke gegevens mogelijk overbelicht is, bijvoorbeeld door openbaar te worden gedeeld, te delen met een externe gebruiker of veel gedeeld binnen uw organisatie.

#### <a name="subject-rights-requests-by-regulation"></a>Verzoeken om rechten van onderwerp door regelgeving

In deze weergave krijgt u inzicht in de regelgeving die het meest van toepassing is op uw verzoeken om onderwerprechten in de tijd. De legenda van deze grafiek toont verschillende voorschriften. Wanneer u de muisaanwijzer boven de trendlijnen beweegt, worden de totalen van aanvragen voor onderwerprechten die gedurende de geselecteerde tijd voor die verordening zijn geopend, voor die verordening laten zien.

#### <a name="subject-rights-requests-by-status"></a>Verzoeken om rechten van onderwerp per status

In deze grafiek ziet u hoe uw organisatie het doet met het invullen van aanvragen voor onderwerprechten, onderverdeeld in aanvragen die actief, gesloten of achterstallig zijn. De resultaten hier kunnen helpen om aan te geven waar u baat bij hebt bij het toewijzen van meer resources aan het sluiten van uw aanvragen en doelstellingen voor het bereiken van doelen.

### <a name="additional-data-views"></a>Aanvullende gegevensweergaven

#### <a name="subject-rights-requests-at-a-glance"></a>Aanvragen voor onderwerprechten in één oogopslag

Deze weergave biedt een weergave op hoog niveau van actieve aanvragen voor onderwerprechten, inclusief de resterende tijd om aanvragen te voltooien op basis van de gedefinieerde deadlines. Het overzicht van het totale aantal aanvragen dat u hebt, hoeveel er actief zijn en hoeveel er zijn gesloten. Selecteer Alle aanvragen weergeven om naar de pagina met aanvragen voor onderwerprechten te gaan, waar u meer details kunt bekijken en kunt werken aan de actieve aanvragen om ze door te sturen naar voltooiing.

#### <a name="subject-rights-requests-by-residency"></a>Verzoeken om rechten van onderwerp door ingezetenschap

Met deze kaartweergave kunt u uw hoeveelheid aanvragen voor onderwerprechten visualiseren door de woonplaats van de gegevensonderwerpen. Wanneer u de muisaanwijzer boven een bellenballon beweegt, worden de regio en het totaal van de aanvragen voor onderwerprechten die namens de bewoners daar zijn geopend, identificeren.

## <a name="explore-the-data-profile-page"></a>De pagina gegevensprofiel verkennen

### <a name="personal-data-type-instances-detected-in-microsoft-365"></a>Exemplaren van het type persoonlijke gegevens die zijn gedetecteerd in Microsoft 365

Met deze kaart kunt u visualiseren hoeveel persoonlijke gegevens er in uw Microsoft 365-omgeving aanwezig zijn en hoe deze gegevens worden verdeeld over Exchange, OneDrive, SharePoint en Teams.

In de staafgrafiek ziet u het statistische totaal aantal unieke exemplaren van het type persoonlijke gegevens in uw inhoud. Voorbeelden van gegevenstypen zijn bijvoorbeeld creditcardnummers en socialezekerheidsnummers. Daarom zou een gevonden bestand met drie creditcardnummers en één sociaal-zekerheidsnummer twee unieke typen persoonlijke gegevens en vier exemplaren bevatten. De onderste persoon van deze kaart toont de unieke typen persoonlijke gegevens op elke Microsoft 365 locatie. Het biedt een overzicht van de diversiteit van typen persoonlijke gegevens die zijn gedetecteerd in de inhoud van uw organisatie.

### <a name="top-personal-data-types-across-your-organization"></a>De belangrijkste typen persoonlijke gegevens in uw organisatie

Deze kaart bevat een momentopname van de belangrijkste typen persoonlijke gegevens die in uw omgeving zijn gedetecteerd, samen met informatie over het aantal items dat persoonlijke gegevenstype bevat en op welke locaties.

### <a name="personal-data-by-region"></a>Persoonsgegevens per regio

Voor multi-geo-omgevingen worden met deze kaart regionaal persoonsgegevens in uw inhoud samengevoegd, op basis van de regio's waarin deze inhoud wordt gehost. Voor organisaties met één regio wordt op deze kaart één punt voor uw Microsoft 365 servicelocatie. Wanneer u de muisaanwijzer boven puntjes op de kaart beweegt, wordt het geschatte aantal exemplaren van het type persoonlijke gegevens weergegeven dat in dat gebied is gevonden.

### <a name="exploring-content"></a>Inhoud verkennen

Als **u Verkennen** selecteert op een gegevensprofielkaart, wordt de inhoudsverkenner geopend. Op dit moment kunt u niet zoeken naar een specifiek inhoudsitem en ziet u geen Teams in deze weergave. Dit betekent dat getallen in de inhoudsverkenner mogelijk niet overeenkomen met de getallen die worden weergegeven op de pagina met gegevensprofiel, omdat de pagina met gegevensprofiel wel Teams bevat. Privacybeheerders die meer inzicht willen in hun privacygegevens, kunnen dit hier doen op basis van het type persoonlijke gegevens (type gevoelige informatie) of op locatie (Exchange, OneDrive of SharePoint).
