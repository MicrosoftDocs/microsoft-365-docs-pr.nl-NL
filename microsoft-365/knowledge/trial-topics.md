---
title: Een proefversie van Microsoft Viva-onderwerpen uitvoeren
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: ''
search.appverid: ''
localization_priority: Normal
description: Meer informatie over het plannen en uitvoeren van een proefprogramma voor Microsoft Viva-onderwerpen in uw organisatie.
ms.openlocfilehash: 128e82e7664a76baa55d37e983319c9f344624fd
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327089"
---
# <a name="run-a-trial-of-microsoft-viva-topics"></a>Een proefversie van Microsoft Viva-onderwerpen uitvoeren

In dit artikel wordt beschreven hoe u een proefprogramma voor het implementeren van Viva-onderwerpen in uw organisatie kunt instellen en uitvoeren. In dit artikel worden ook aanbevolen aanbevolen procedures voor de proefversie.

## <a name="sign-up-for-a-trial"></a>Registreren voor een proefabonnement

Proefversies zijn openbaar beschikbaar vanuit een van de volgende bronnen. Deze proefversies bieden 25 gebruikers 30 dagen lang toegang tot Viva-onderwerpen.

- De [productpagina Viva-onderwerpen](https://www.microsoft.com/microsoft-viva/topics?activetab=pivot:overviewtab)

- De [Microsoft 365-beheercentrum](https://admin.microsoft.com)
    1.  Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com).
    2.  Ga naar   >  **Factureringsaankoopservices.**
    3.  Schuif omlaag naar de **sectie Invoegtoepassingen.**
    4.  Selecteer details **op de tegel** **Onderwerpervaringen.**
    5.  Selecteer **Gratis proefversie downloaden.**
    6.  Volg de resterende wizardstappen om het proefabonnement te bevestigen.

U moet een globale Microsoft 365 of factureringsbeheerder zijn om een proefabonnement te activeren.

> [!NOTE]
> Openbare proefversies kunnen slechts eenmaal worden toegevoegd voor elke Microsoft 365 tenant.

### <a name="who-should-be-involved-in-a-trial"></a>Wie moet betrokken zijn bij een proefversie

|Rol  |Activiteit  |
|---------|---------|
|Microsoft 365 globale beheerder of factureringsbeheerder  |   De proefversie activeren en licenties toewijzen      |
|Microsoft 365 globale beheerder of SharePoint beheerder    |       Viva-onderwerpen configureren en onderwerpcentra maken  |
|Zakelijke gebruiker     |   Kennisbeheer, onderwerpbetaler en rollen van de onderwerp-consument uitvoeren      |

### <a name="before-you-activate-a-trial"></a>Voordat u een proefabonnement activeert

Planning is essentieel voor een effectieve proefversie van Viva-onderwerpen. De proefperiode is beperkt en moet onderwerpdetectie bevatten en het verkennen van de ervaringen van onderwerpkwaliteit, beheer en eindgebruikers.

#### <a name="discovery"></a>Detectie

Er zijn twee strategieopties op hoog niveau voor de configuratie van onderwerpdetectie tijdens een proefversie:

- Alle of het grootste deel van uw online SharePoint indexeren.
   - Het kan maximaal twee weken duren voordat grote tenants volledig zijn geïndexeerd. Hoewel onderwerpen in deze periode stapsgewijs worden gegenereerd, kan volledige indexering maximaal de helft van de proefperiode kosten.
   - Voor tenants met een aanzienlijk gegevensvolume kan deze optie een zeer groot aantal onderwerpen, misschien wel tienduizenden, opleveren.

- Identificeer een subset van uw SharePoint sites voor indexering.

De keuze van deze strategieën is een evenwicht tussen de volgende twee factoren:

- Voldoende gegevens om zinvolle onderwerpen te genereren. De AI in Viva-onderwerpen is afgestemd op het werken met grote gegevenssets, ideaal degenen met meer dan 10.000 documenten.
- Het genereren van niet zo veel onderwerpen tijdens de proefperiode dat het evalueren ervan tijdens de beschikbare periode overweldigend is.

Voor de meeste organisaties levert de tweede strategie het beste resultaat op.

> [!NOTE]
> Vanwege het aantal documenten dat door de AI is vereist, raden we u aan om proefversies van Viva Topics uit te voeren op een productieten tenant. Er is geen invloed op de prestaties van de tenant in deze periode. Alleen gebruikers met een proeflicentie hebben toegang tot de gebruikerservaringen van Viva Topics.

#### <a name="roles"></a>Rollen

Tijdens de proefversie moeten er drie rollen actief zijn, die in de volgende tabel worden beschreven.

|Rol  |Activiteit  |
|---------|---------|
|Knowledge manager     |   Beheer de levenscyclusfasen van onderwerpen; onderwerpen bevestigen en verwijderen; fungeren als communitymanager voor onderwerpcontribuanten      |
|Onderwerpbetaler    |      Experts op het gebied van inhoud, die:<br> Onderwerpen bekijken om de kwaliteit van ai-gedefinieerde inhoud te evalueren<br>Onderwerpen met aanvullende inhoud op curate<br>Extra onderwerpen maken die niet zijn ontdekt door AI   |
|Onderwerp consument    |     Onderwerpen gebruiken via pagina-highlights en zoeken<br>Feedback geven over de waarde van de gepresenteerde onderwerpen    |

#### <a name="expected-topics"></a>Verwachte onderwerpen

Het kan handig zijn om de onderwerpen te documenteren die u verwacht te genereren door de AI, zelfs als dit alleen is gebaseerd op aannames. Deze taak is het gemakkelijkst voltooid wanneer u een gedefinieerde subset van uw SharePoint sites indexeert waarvoor kleine en middelgrote ondernemingen gemakkelijk kunnen worden geïdentificeerd.

Als u een gedocumenteerde lijst hebt, kunt u het volgende doen:

- Bekijk de lijst met door AI gegenereerde onderwerpen, die mogelijk groter zijn dan u verwacht.
- Ken de onderwerpen die u mogelijk handmatig moet maken of die prioriteiten zijn voor curatie.

Er is altijd behoefte aan een combinatie van door AI gedefinieerde en door de mens gemaakte onderwerpen in een succesvolle implementatie of proefversie van Viva-onderwerpen.

## <a name="activate-a-trial"></a>Een proefversie activeren

Wanneer u een proefabonnement start, moet u het volgende doen:

- Licenties toewijzen aan de relevante gebruikers.
- Voer [aanvullende installatie van](set-up-topic-experiences.md) Viva-onderwerpen uit.

Wanneer de proefversie is geactiveerd, begint het proces voor het ontdekken van onderwerpen.

## <a name="during-a-trial"></a>Tijdens een proefabonnement

De proefperiode moet worden gebruikt om de volgende onderdelen van Viva-onderwerpen te evalueren:

- De AI-voorgestelde onderwerpen en onderwerpinhoud
- De ervaringen van eindgebruikers, het bekijken van onderwerpkaarten op moderne SharePoint pagina's en in Microsoft Search

Houd rekening met deze factoren:

- Als Viva-onderwerpen de maximale waarde willen leveren, moet de inhoud in onderwerpen een combinatie zijn van ai-gedefinieerde inhoud en door mensen samengestelde inhoud.
- Alle gebruikerservaringen zijn 'machtigingen bijgesneden' (inclusief de weergave van de knowledge manager op **de pagina Onderwerpen** beheren). Gebruikers zien alleen een onderwerp als ze machtigingen hebben om een aantal bronnen weer te geven die zijn gebruikt om het onderwerp te genereren. Dit betekent dat verschillende gebruikers verschillende inhoud op dezelfde onderwerppagina kunnen zien.
- Gebruikers zien mogelijk meerdere onderwerpen met dezelfde naam op de **pagina Onderwerpen** beheren. Deze onderwerpen zijn niet per se duplicaten, maar kunnen worden veroorzaakt door één term die in meerdere contexten in de gegevens wordt gebruikt, zoals een projectcodenaam die door twee afzonderlijke projecten wordt gebruikt.

## <a name="after-a-trial"></a>Na een proefversie

Op basis van de uitkomst van de proef kunt u bepalen of u door wilt gaan met het productiegebruik van Viva-onderwerpen.

### <a name="proceed-to-production-use"></a>Ga verder met het gebruik van de productie

Als u de continuïteit van de service wilt garanderen, moet u het vereiste aantal licenties kopen en deze licenties toewijzen aan gebruikers. Proefgebruikers die aan het einde van de proefperiode geen volledige licentie hebben, hebben geen toegang tot ervaringen met Viva-onderwerpen.

### <a name="dont-proceed-to-production-use"></a>Ga niet verder met het gebruik van de productie

Als u na de proefversie geen licenties koopt:

- Onderwerpdetectie stopt.
- Gebruikers zien geen highlights of kaarten meer van het onderwerp.
- Het onderwerpcentrum wordt niet verwijderd, maar de voorgestelde onderwerpen en het beheren van onderwerpen zijn niet beschikbaar.
- Alle door AI gedefinieerde onderwerpen gaan verloren.
- Onderwerpen die door een inzender van het onderwerp zijn bewerkt, blijven in de bibliotheek met pagina's van het onderwerpcentrum staan. Alleen de handmatig verstrekte inhoud blijft op deze pagina's staan, geen AI-voorgestelde inhoud.

## <a name="see-also"></a>Zie ook

[Aan de slag met de implementatie van Microsoft Viva-onderwerpen](topics-adoption-getstarted.md)

