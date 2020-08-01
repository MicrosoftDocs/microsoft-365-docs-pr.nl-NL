---
title: Uitzonderingen op het serviceplan
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 826710bf59acd88494adf1f154e5657d1e039af7
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529933"
---
# <a name="exceptions-to-the-service-plan"></a>Uitzonderingen op het serviceplan

Microsoft Managed Desktop biedt een lijst met samengestelde apparaten, [standaard apparaatinstellingen,](device-policies.md)toepassingsvereisten en bepaalde [configureerbare instellingen,](../working-with-managed-desktop/config-setting-overview.md)allemaal ontworpen om een veilige, productieve en aangename ervaring voor eindgebruikers te bieden. Het is het beste om altijd verblijf met de service zoals verstrekt. We erkennen echter dat sommige details van de service mogelijk niet precies aansluiten bij de behoeften van uw organisatie. Als u denkt dat u de service op de een of andere manier moet wijzigen, is het belangrijk dat u de volgende processen volgt om deze wijzigingen op te vragen.
 
## <a name="types-of-exceptions"></a>Soorten uitzonderingen

Een uitzondering is elke toevoeging of wijziging in de basisconfiguratie van Microsoft Managed Desktop; voorbeelden variëren van usb-poortenconfiguratie tot het implementeren van een nieuw apparaatstuurprogramma. We groeperen verschillende uitzonderingen als volgt:

|Type  |Beschrijving  |
|---------|---------|
|Productiviteitssoftware     |  Voorgrondsoftware die door eindgebruikers nodig is, beperkt door de [toepassingsvereisten](mmd-app-requirements.md)       |
|Beveiligingsagenten & VPN's     |  Software die wordt gebruikt om het gedrag van het apparaat of netwerk te beveiligen, te controleren of te wijzigen       |
|Monitoring van digitale ervaring     |  Software die wordt gebruikt om gegevens op het apparaat van een gebruiker bij te houden om te rapporteren aan IT       |
|Hardware- of softwarestuurprogramma's     |   Apparaatstuurprogramma's, beperkt door de [toepassingsvereisten](mmd-app-requirements.md)      |
|Beleid     | Windows 10- of Microsoft 365-apps voor bedrijfsinstellingen op een beheerd apparaat        |
|Apparaten     | Apparaten die niet in de lijst met Microsoft Managed [Desktop-apparaten staan](device-list.md)        |
|Overige     |  Alles wat niet door de andere gebieden wordt gedekt       |
 
## <a name="request-an-exception"></a>Een uitzondering aanvragen

Verzoeken indienen via de Microsoft Managed Desktop Admin-portal door een wijzigingsaanvraag te maken. Zorg ervoor dat u deze gegevens opneemt:

-   Uitzonderingstype: Welke uitzonderingscategorie is het? (zie de vorige tabel)
-   Vereiste: Wat is de specifieke bedrijfseis voor de uitzondering?
-   Voorstel: Welke oplossing vraagt uw bedrijf?
-   Tijdlijn: Hoe lang wilt u dat deze uitzondering duurt? 

## <a name="how-we-assess-an-exception-request"></a>Hoe we een uitzonderingsaanvraag beoordelen

Wanneer we uitzonderingsverzoeken beoordelen, beoordelen we deze factoren in deze volgorde:
 
1.  Sommige toepassingen en beleidsregels die Microsoft Managed Desktop op alle apparaten implementeert, zijn niet onderhandelbaar, dus uw verzoek mag geen invloed hebben op deze toepassingen. Zie [Apparaatconfiguratie](device-policies.md) voor meer informatie.
2.  Beperkte productiviteit software die nodig is door een eindgebruiker om hun werk te doen zal waarschijnlijk worden goedgekeurd. 
3.  Als we aan uw vereisten kunnen voldoen met behulp van Microsoft-technologie, zullen we uw aanvraag waarschijnlijk goedkeuren voor een uitzonderingsmigratieperiode van drie tot twaalf maanden (afhankelijk van de omvang van het project).
4.  Als we niet aan uw vereisten kunnen voldoen door Microsoft-technologie te gebruiken, zullen we uw verzoek waarschijnlijk goedkeuren, tenzij het een van de onderstaande voorwaarden schendt.  

Deze principes zorgen ervoor dat Microsoft Managed Desktop altijd aan uw behoeften kan voldoen terwijl u afwijkingen van onze standaardsjabloon bijhoudt. 

## <a name="key-conditions"></a>Belangrijkste voorwaarden

We bekijken uitzonderingen om ervoor te zorgen dat ze geen van deze voorwaarden schenden:

-   Een uitzondering mag geen negatieve gevolgen hebben voor de beveiliging van het systeem. 
-   Het handhaven van de uitzondering mag geen aanzienlijke kosten met zich meebrengen voor microsoft managed desktop-bewerkingen of -ondersteuning.
-   Een uitzondering mag de stabiliteit van het systeem niet beïnvloeden, bijvoorbeeld door vastlopen of vastlopen van de kernelmodus te veroorzaken.
-   De wijziging mag ons niet beperken dat de service wordt beheerd of in strijd is met de belangrijkste Microsoft Managed Desktop-technologie.

Deze voorwaarden kunnen in de toekomst veranderen. Als we dergelijke wijzigingen aanbrengen, zullen we 30 dagen van tevoren opzegtermijn geven voordat deze voorwaarden van kracht worden.  Als Microsoft Managed Desktop een alternatieve manier biedt om aan een goedgekeurde uitzondering te voldoen, stelt Microsoft Managed Desktop de klant hiervan op de hoogte als Microsoft Managed Desktop de manier waarop de uitzondering wordt ondersteund, wijzigt. 

## <a name="revoking-approval-for-an-exception"></a>Goedkeuring voor een uitzondering intrekken

Nadat een gevraagde uitzondering is goedgekeurd en geïmplementeerd, is het mogelijk dat we problemen ontdekken die in strijd zijn met de belangrijkste voorwaarden die niet duidelijk waren toen we de wijziging in de eerste plaats goedkeurden. In deze situatie moeten we misschien de goedkeuring voor de uitzondering intrekken.
 
Als dit gebeurt, stellen we u hiervan op de hoogte via de Microsoft Managed Desktop-beheerportal. Vanaf de eerste melding dat we u op de hoogte stellen, hebt u 90 dagen de tijd om de uitzondering te verwijderen voordat de apparaten met uitzondering niet langer gebonden zijn aan microsoft Managed Desktop-serviceniveauovereenkomsten. We sturen je verschillende meldingen volgens een strikte tijdlijn- maar een ernstig incident of bedreiging kan ons verplichten om de tijdlijn of onze beslissingen over een uitzondering te wijzigen. We *verwijderen* geen uitzondering zonder uw toestemming, maar elk apparaat met een ingetrokken uitzondering is niet langer gebonden aan onze serviceniveauovereenkomst. Hier is de tijdlijn van meldingen die we je sturen:

- **Eerste mededeling:** We doen de eerste kennisgeving van ons besluit om de goedkeuring in te trekken, inclusief informatie over waarom we de goedkeuring intrekken, de acties die we u adviseren te ondernemen, de deadline voor die acties en stappen die u moet volgen als u in beroep wilt gaan tegen de beslissing. Dit is 90 dagen van tevoren voordat de uitzondering van alle apparaten moet worden verwijderd. 
- **Tweede bericht (30 dagen later):** Wij verstrekken een tweede kennisgeving, met inbegrip van dezelfde informatie die in de eerste kennisgeving wordt verstrekt. 
- **Derde bericht (60 dagen na de eerste kennisgeving):** Wij verstrekken een derde kennisgeving, inclusief dezelfde informatie in de eerste kennisgeving. 
- **Laatste bericht (1 week voor de termijn van 90 dagen):** Wij bieden een vierde kennisgeving, met dezelfde informatie die in de eerste kennisgeving.
- **90 dagen na de eerste kennisgeving:** Microsoft Managed Desktop-serviceniveauovereenkomsten zijn niet langer van toepassing op apparaten die de ingetrokken uitzondering hebben. U de beslissing op elk gewenst moment aanvechten en aanvullende informatie ter overweging verstrekken, waaronder upgrade, configuratiewijzigingen of softwarewijzigingen. 


