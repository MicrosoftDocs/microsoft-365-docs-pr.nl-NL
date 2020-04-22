---
title: Uitzonderingen op het serviceplan
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9dca53ac9e99fd9bc68ee42f78de6a2bc009e42c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636182"
---
# <a name="exceptions-to-the-service-plan"></a>Uitzonderingen op het serviceplan

Microsoft Managed Desktop biedt een samengestelde apparaatlijst, [standaardapparaatinstellingen,](device-policies.md)toepassingenvereisten en bepaalde [configureerbare instellingen,](../working-with-managed-desktop/config-setting-overview.md)allemaal ontworpen om eindgebruikers een veilige, productieve en aangename ervaring te bieden. Het is het beste om altijd verblijf met de service zoals verstrekt. We erkennen echter dat sommige details van de service mogelijk niet precies aansluiten bij de behoeften van uw organisatie. Als u vindt dat u de service op de een of andere manier moet wijzigen, is het belangrijk dat u de volgende processen volgt om deze wijzigingen aan te vragen.
 
## <a name="types-of-exceptions"></a>Soorten uitzonderingen

Een uitzondering is een toevoeging of wijziging in de Microsoft Managed Desktop-basisconfiguratie. voorbeelden variëren van de configuratie van USB-poorten tot het implementeren van een nieuw apparaatstuurprogramma. We groeperen verschillende uitzonderingen als volgt:

|Type  |Beschrijving  |
|---------|---------|
|Productiviteitssoftware     |  Voorgrondsoftware die nodig is voor eindgebruikers, beperkt door de [toepassingsvereisten](mmd-app-requirements.md)       |
|Beveiligingsagenten & VPN's     |  Software die wordt gebruikt om het gedrag van het apparaat of netwerk te beveiligen, te bewaken of te wijzigen       |
|Monitoring van digitale ervaringen     |  Software die wordt gebruikt om gegevens op het apparaat van een gebruiker bij te houden om aan IT te rapporteren       |
|Hardware- of softwarestuurprogramma's     |   Apparaatstuurprogramma's, beperkt door de [toepassingsvereisten](mmd-app-requirements.md)      |
|Beleid     | Windows 10- of Microsoft 365-apps voor bedrijfsinstellingen op een beheerd apparaat        |
|Apparaten     | Apparaten die niet in de lijst met Microsoft Managed [Desktop-apparaten staan](device-list.md)        |
|Andere     |  Alles wat niet onder de andere gebieden valt       |
 
## <a name="request-an-exception"></a>Een uitzondering aanvragen

Dien aanvragen in via de Microsoft Managed Desktop Admin-portal door een wijzigingsaanvraag te maken. Zorg ervoor dat u deze gegevens opneemt:

-   Uitzonderingstype: Welke uitzonderingscategorie is het? (zie de vorige tabel)
-   Vereiste: Wat is de specifieke zakelijke eis voor de uitzondering?
-   Voorstel: Welke oplossing vraagt uw bedrijf?
-   Tijdlijn: Hoe lang wilt u dat deze uitzondering lang duurt? 

## <a name="how-we-assess-an-exception-request"></a>Hoe we een uitzonderingsverzoek beoordelen

Wanneer we uitzonderingsverzoeken beoordelen, beoordelen we deze factoren in deze volgorde:
 
1.  Sommige toepassingen en beleidsregels die Microsoft Managed Desktop implementeert op alle apparaten zijn niet bespreekbaar, dus uw aanvraag mag deze niet beïnvloeden. Zie [Apparaatconfiguratie](device-policies.md) voor meer informatie.
2.  Beperkte productiviteit software die nodig is door een eindgebruiker om hun werk te doen zal waarschijnlijk worden goedgekeurd. 
3.  Als we aan uw eis kunnen voldoen door gebruik te maken van Microsoft-technologie, keuren we uw aanvraag waarschijnlijk goed voor een uitzonderingsmigratieperiode van drie tot twaalf maanden (afhankelijk van het bereik van het project).
4.  Als we niet aan uw eis kunnen voldoen door microsoft-technologie te gebruiken, zullen we uw verzoek waarschijnlijk goedkeuren, tenzij het in strijd is met een van de onderstaande voorwaarden.  

Deze principes zorgen ervoor dat Microsoft Managed Desktop altijd aan uw behoeften kan voldoen en afwijkingen van onze standaardsjabloon kan bijhouden. 

## <a name="key-conditions"></a>Belangrijkste voorwaarden

We controleren uitzonderingen om ervoor te zorgen dat ze niet in strijd zijn met een van deze voorwaarden:

-   Een uitzondering mag geen nadelige gevolgen hebben voor de systeembeveiliging. 
-   Het handhaven van de uitzondering mag geen aanzienlijke kosten met zich meebrengen voor Microsoft Managed Desktop-bewerkingen of ondersteuning.
-   Een uitzondering mag geen invloed hebben op de stabiliteit van het systeem, bijvoorbeeld door het veroorzaken van kernel mode crashes of vastloopt.
-   De wijziging mag ons niet beperken om de service te gebruiken of in strijd te zijn met de belangrijkste Microsoft Managed Desktop-technologie.

Deze voorwaarden kunnen in de toekomst veranderen. Als we dergelijke wijzigingen aanbrengen, zullen we 30 dagen van tevoren opzegtermijn voordat deze voorwaarden in werking treden.  Als Microsoft Managed Desktop een alternatieve manier biedt om aan een goedgekeurde uitzondering te voldoen, stelt Microsoft Managed Desktop de klant op de hoogte als Microsoft Managed Desktop de manier wijzigt bij het ondersteunen van de uitzondering. 

## <a name="revoking-approval-for-an-exception"></a>Intrekking van de goedkeuring voor een uitzondering

Nadat een aangevraagde uitzondering is goedgekeurd en geïmplementeerd, is het mogelijk dat we problemen ontdekken die in strijd zijn met de belangrijkste voorwaarden die niet duidelijk waren toen we de wijziging in de eerste plaats goedkeurden. In deze situatie moeten we de goedkeuring voor de uitzondering mogelijk intrekken.
 
Als dit gebeurt, stellen we u hiervan op de hoogte via de Microsoft Managed Desktop-beheerportal. Vanaf de eerste keer dat we u op de hoogte stellen, hebt u 90 dagen de tijd om de uitzondering te verwijderen voordat de apparaten met uitzondering niet langer gebonden zijn aan overeenkomsten op Microsoft Managed Desktop-serviceniveau. We sturen u verschillende meldingen volgens een strikte tijdlijn- maar een ernstig incident of bedreiging kan vereisen dat we de tijdlijn of onze beslissingen over een uitzondering wijzigen. We *verwijderen* geen uitzondering zonder uw toestemming, maar elk apparaat met een ingetrokken uitzondering is niet langer gebonden aan onze servicelevelovereenkomst. Hier is de tijdlijn van meldingen die we u sturen:

- **Eerste bericht:** We geven de eerste kennisgeving van onze beslissing om de goedkeuring in te trekken, inclusief informatie over waarom we deze intrekken, de acties die we u adviseren te ondernemen, de deadline voor die acties en stappen die moeten worden gevolgd als u bezwaar wilt maken tegen de beslissing. Dit is 90 dagen van tevoren voordat de uitzondering van alle apparaten moet worden verwijderd. 
- **Tweede bericht (30 dagen later):** We geven een tweede kennisgeving, met dezelfde informatie die in de eerste kennisgeving wordt verstrekt. 
- **Derde bericht (60 dagen na de eerste kennisgeving):** We geven een derde kennisgeving, met inbegrip van dezelfde informatie die in de eerste kennisgeving. 
- **Eindbericht (1 week voor de deadline van 90 dagen):** We geven een vierde kennisgeving, met dezelfde informatie in de eerste kennisgeving.
- **90 dagen na de eerste kennisgeving:** Overeenkomsten op serviceniveau van Microsoft Managed Desktop zijn niet langer van toepassing op apparaten met de ingetrokken uitzondering. U de beslissing op elk gewenst moment aanvechten en aanvullende informatie ter overweging verstrekken, waaronder upgrade, configuratiewijzigingen of wijziging van software. 


