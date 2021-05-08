---
title: Uitzonderingen op het serviceplan
description: Uitzonderingen op het standaardserviceplan aanvragen
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 59a2b8227eb7e410ecf8506ce288978213537edc
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245514"
---
# <a name="exceptions-to-the-service-plan"></a>Uitzonderingen op het serviceplan

Microsoft Managed Desktop biedt een samengestelde [apparaatlijst,](device-policies.md)standaardapparaatinstellingen, toepassingsvereisten en bepaalde [configureerbare](../working-with-managed-desktop/config-setting-overview.md)instellingen, allemaal ontworpen om gebruikers een veilige, productieve en aangename ervaring te bieden. Het is het beste om altijd bij de service te blijven. We erkennen echter dat bepaalde details van de service mogelijk niet precies aan de behoeften van uw organisatie voldoen. Als u denkt dat u de service op een bepaalde manier moet wijzigen, is het belangrijk dat u de volgende processen volgt om deze wijzigingen aan te vragen.
 
## <a name="types-of-exceptions"></a>Typen uitzonderingen

Een uitzondering is elke toevoeging of wijziging in de Microsoft Managed Desktop basisconfiguratie; Voorbeelden variëren van configuratie van USB-poorten tot het implementeren van een nieuw apparaatt stuurprogramma. We groepeert verschillende uitzonderingen als volgt:

|Type  |Omschrijving  |
|---------|---------|
|Productiviteitssoftware     |  Voorgrondsoftware die nodig is voor gebruikers, beperkt door de [toepassingsvereisten](mmd-app-requirements.md)       |
|Beveiligingsagenten & VPN's     |  Software die wordt gebruikt om het gedrag van het apparaat of netwerk te beveiligen, te bewaken of te wijzigen       |
|Monitoring van digitale ervaring     |  Software die wordt gebruikt om gegevens op het apparaat van een gebruiker bij te houden om te rapporteren aan IT       |
|Hardware- of software-stuurprogramma's     |   Apparaat stuurprogramma's, beperkt door de [toepassingsvereisten](mmd-app-requirements.md)      |
|Beleid     | Windows 10 of Microsoft 365-apps voor ondernemingen instellingen op een beheerd apparaat        |
|Apparaten     | Apparaten die niet in de lijst met Microsoft Managed Desktop [staan](device-list.md)        |
|Overige     |  Alles wat niet onder de andere gebieden valt       |
 
## <a name="request-an-exception"></a>Een uitzondering aanvragen

Verzend aanvragen via de Microsoft Managed Desktop-beheerportal door een wijzigingsaanvraag te maken. Zorg ervoor dat u de volgende details op wilt nemen:

- Uitzonderingstype: Welke uitzonderingscategorie is het? (zie de vorige tabel)
- Vereiste: Wat is de specifieke bedrijfsvereiste voor de uitzondering?
- Voorstel: Welke oplossing vraagt uw bedrijf?
- Tijdlijn: Hoe lang wilt u deze uitzondering laten duren? 

## <a name="how-we-assess-an-exception-request"></a>Hoe we een uitzonderingsaanvraag beoordelen

Wanneer we uitzonderingsaanvragen bekijken, beoordelen we deze factoren in deze volgorde:
 
1. Sommige toepassingen en beleidsregels die Microsoft Managed Desktop worden geïmplementeerd op alle apparaten, zijn niet bespreekbaar, dus uw aanvraag mag geen invloed hebben op deze toepassingen. Zie [Apparaatconfiguratie](device-policies.md) voor meer informatie.
2. Software voor beperkte productiviteit die een gebruiker nodig heeft om zijn of haar werk te doen, wordt waarschijnlijk goedgekeurd. 
3. Als we aan uw vereisten kunnen voldoen met behulp van Microsoft-technologie, zullen we uw aanvraag voor een uitzonderingsmigratieperiode van drie tot twaalf maanden waarschijnlijk goedkeuren (afhankelijk van het bereik van het project).
4. Als we niet aan uw vereisten kunnen voldoen met behulp van Microsoft-technologie, zullen we uw aanvraag waarschijnlijk goedkeuren, tenzij deze in strijd is met een van de onderstaande voorwaarden.  

Deze principes zorgen ervoor dat Microsoft Managed Desktop altijd aan uw behoeften kan voldoen terwijl u de afwijkingen van onze standaardsjabloon bij kunt houden. 

## <a name="key-conditions"></a>Belangrijke voorwaarden

We controleren uitzonderingen om ervoor te zorgen dat ze geen van deze voorwaarden schenden:

- Een uitzondering mag geen negatieve invloed hebben op de systeembeveiliging. 
- Het behouden van de uitzondering mag geen aanzienlijke kosten met zich mee Microsoft Managed Desktop of ondersteuning.
- Een uitzondering mag geen invloed hebben op de systeemstabiliteit, bijvoorbeeld door ervoor te zorgen dat de kernelmodus vast loopt of vast loopt.
- De wijziging mag ons niet beperken om de service te gebruiken of conflicteren met de Microsoft Managed Desktop kerntechnologie.

Deze voorwaarden kunnen in de toekomst veranderen. Als we dergelijke wijzigingen aanbrengen, geven we 30 dagen van tevoren op voordat deze voorwaarden van kracht worden.  Als Microsoft Managed Desktop een alternatieve manier biedt om te voldoen aan een goedgekeurde uitzondering, Microsoft Managed Desktop de klant op de hoogte wanneer Microsoft Managed Desktop manier moet wijzigen om de uitzondering te ondersteunen. 

## <a name="revoking-approval-for-an-exception"></a>Goedkeuring voor een uitzondering inroepen

Nadat een aangevraagde uitzondering is goedgekeurd en geïmplementeerd, is het mogelijk dat we problemen kunnen ontdekken die in strijd zijn met de belangrijkste voorwaarden die niet duidelijk waren toen we de wijziging in de eerste plaats goedkeurden. In deze situatie moeten we de goedkeuring voor de uitzondering mogelijk intrekken.
 
Als dit gebeurt, wordt u hiervan op de hoogte Microsoft Managed Desktop de beheerportal. Vanaf de eerste keer dat we u op de hoogte stellen, hebt u 90 dagen de tijd om de uitzondering te verwijderen voordat de apparaten met de uitzondering niet meer gebonden zijn aan Microsoft Managed Desktop serviceniveauovereenkomsten. We sturen u verschillende meldingen op basis van een strikte tijdlijn, maar bij een ernstig incident of een ernstige bedreiging moeten we mogelijk de tijdlijn of onze beslissingen over een uitzondering wijzigen. We verwijderen geen uitzondering *zonder* uw toestemming, maar elk apparaat met een ingetrokken uitzondering is niet langer gebonden aan onze serviceovereenkomst. Hier is de tijdlijn van meldingen die we u sturen:

- **Eerste bericht:** We geven de eerste kennisgeving van ons besluit om de goedkeuring in te trekken, inclusief informatie over waarom we deze intrekken, de acties die u moet ondernemen, de deadline voor deze acties en de stappen die u moet volgen als u in beroep wilt gaan tegen de beslissing. Deze melding vindt 90 dagen van tevoren plaats voordat de uitzondering van alle apparaten moet worden verwijderd. 
- **Tweede kennisgeving (30 dagen later):** We geven een tweede kennisgeving, inclusief dezelfde informatie die in de eerste kennisgeving wordt verstrekt. 
- **Derde kennisgeving (60 dagen na de eerste kennisgeving):** We geven een derde kennisgeving, inclusief dezelfde informatie die in de eerste kennisgeving wordt verstrekt. 
- **Laatste kennisgeving (één week vóór de deadline van 90 dagen):** We geven een vierde kennisgeving, inclusief dezelfde informatie die in de eerste kennisgeving wordt verstrekt.
- **90 dagen na de eerste kennisgeving:** Microsoft Managed Desktop overeenkomsten op serviceniveau zijn niet meer van toepassing op apparaten met de ingetrokken uitzondering. U kunt de beslissing op elk moment aandagen en aanvullende informatie ter overweging geven, zoals upgrade, configuratiewijzigingen of wijziging van software. 


