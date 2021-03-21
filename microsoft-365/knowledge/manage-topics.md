---
title: Onderwerpen beheren in het onderwerpcentrum in Microsoft Viva-onderwerpen
description: Onderwerpen beheren in het Onderwerpcentrum.
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: 2443319d254130b38bb1047a633c85c160eadd8c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925998"
---
# <a name="manage-topics-in-the-topic-center"></a>Onderwerpen beheren in het onderwerpcentrum 

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


In het onderwerpcentrum Viva-onderwerpen kan  een kennismanager de pagina Onderwerpen beheren bekijken om onderwerpen te bekijken die zijn geïdentificeerd in SharePoint-bronlocaties, zoals opgegeven door uw kennisbeheerder.  

   ![Onderwerpcentrum](../media/knowledge-management/topic-center.png) </br> 



Kennismanagers helpen bij het begeleiden van gevonden onderwerpen door de levenscyclus van het onderwerp waarin onderwerpen staan:

- Voorgesteld: een onderwerp is geïdentificeerd door AI en heeft voldoende ondersteunende bronnen, verbindingen en eigenschappen.
- Bevestigd: een onderwerp dat door AI is voorgesteld, wordt gevalideerd. Validatie wordt uitgevoerd door bevestiging van een kennismanager. Bovendien kan een onderwerp worden bevestigd als ten minste twee gebruikers positieve feedback geven via de feedbackvraag op de onderwerpkaart.
- Gepubliceerd: Een bevestigd onderwerp dat is samengesteld: handmatige wijzigingen zijn aangebracht om de kwaliteit te verbeteren.
- Verwijderd: Een onderwerp wordt geweigerd door een knowledge manager en is niet meer zichtbaar voor kijkers. Het onderwerp kan in elke staat zijn wanneer het wordt verwijderd (voorgesteld, bevestigd of gepubliceerd). Wanneer een gepubliceerd onderwerp wordt verwijderd, moet de pagina met de samengestelde details handmatig worden verwijderd via de paginabibliotheek van het onderwerpcentrum.

   ![Grafiek Levenscyclus van onderwerp](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> Op de pagina Onderwerpen beheren kan elke knowledge manager alleen onderwerpen zien waar ze toegang hebben tot de bestanden en pagina's van het onderwerp. Dit wordt weerspiegeld in de onderwerpen die worden weergegeven onder de tabbladen Voorgesteld, Bevestigd, Verwijderd en Gepubliceerd. Het aantal onderwerpen toont echter de totale tellingen in de organisatie.

## <a name="requirements"></a>Vereisten

Als u onderwerpen in het onderwerpcentrum wilt beheren, moet u het volgende doen:
- Een licentie voor Viva-onderwerpen hebben.

- De machtiging [**Wie kan onderwerpen beheren.**](./topic-experiences-user-permissions.md) Kennisbeheerders kunnen gebruikers deze machtiging geven in de instellingen voor onderwerpmachtigingen van Viva Topics. 

U kunt de pagina Onderwerpen beheren niet weergeven in het onderwerpcentrum, tenzij u de machtiging **Wie kan onderwerpen** beheren hebt.

In het onderwerpcentrum kan een knowledge manager onderwerpen bekijken die zijn geïdentificeerd in de SharePoint-bronlocaties die u hebt opgegeven, en deze kunnen worden bevestigd of afgewezen. Een knowledge manager kan ook nieuwe onderwerppagina's maken en publiceren als deze niet zijn gevonden in onderwerpdetectie, of bestaande pagina's bewerken als ze moeten worden bijgewerkt.


## <a name="review-suggested-topics"></a>Voorgestelde onderwerpen bekijken

Op de pagina Onderwerpcentrum Onderwerpen beheren worden onderwerpen weergegeven die zijn gevonden in de opgegeven SharePoint-bronlocaties op **het** tabblad Voorgesteld. Indien nodig kan een kennismanager onbevestigde onderwerpen bekijken en ervoor kiezen om deze te bevestigen of te weigeren.

   ![Voorgestelde onderwerpen](../media/knowledge-management/quality-score.png) </br> 

Een voorgesteld onderwerp bekijken:

1. Selecteer op **de pagina** Onderwerpen beheren het tabblad **Voorgesteld** en selecteer het onderwerp om de onderwerppagina te openen.</br>

2. Bekijk de onderwerppagina op de onderwerppagina en selecteer **Bewerken** als u wijzigingen aan de pagina wilt aanbrengen. Als u wijzigingen publiceert, wordt dit onderwerp verplaatst naar **het tabblad** Gepubliceerd.

3. Ga na het bekijken van het onderwerp terug naar de pagina Onderwerpen beheren. Voor het geselecteerde onderwerp kunt u het volgende doen:

   - Selecteer het vinkje om het onderwerp te bevestigen.
    
   - Selecteer de **x** als u het onderwerp wilt weigeren.

    Bevestigd onderwerpen worden verwijderd uit de lijst **Voorgesteld** en worden nu weergegeven in **de lijst** Bevestigd.

    Afgewezen onderwerpen worden verwijderd uit de lijst **Voorgesteld** en worden nu weergegeven op **het tabblad** Verwijderd.

   </br> 

### <a name="quality-score"></a>Kwaliteitsscore

Aan elk onderwerp dat wordt weergegeven op de pagina Voorgestelde onderwerpen is <b>een</b> kwaliteitsscore toegewezen. De kwaliteitsscore is een weerspiegeling van de hoeveelheid informatie die de gemiddelde gebruiker ziet voor de informatie over het onderwerp, rekening houdend met het feit dat elke gebruiker meer of minder informatie kan zien vanwege de machtigingen die ze wel of niet hebben over de informatie in een onderwerp. 

De kwaliteitsscore kan helpen inzicht te geven in de onderwerpen met de meeste informatie en kan handig zijn voor het vinden van onderwerpen die mogelijk handmatig moeten worden bewerkt.  Een onderwerp met een lagere kwaliteitsscore kan bijvoorbeeld het resultaat zijn van sommige gebruikers die geen SharePoint-machtigingen hebben voor relevante bestanden of sites die AI in het onderwerp heeft opgenomen. Een inzender kan het onderwerp vervolgens bewerken om de informatie op te nemen (indien van toepassing), die vervolgens kan worden bekeken voor alle gebruikers die het onderwerp kunnen bekijken.

De kwaliteitsscore kan variëren van 1 tot 100. Een nieuw ontdekt onderwerp heeft een kwaliteitsscore van 0 totdat twee of meer gebruikers het hebben bekeken. Elke gebruikerskwaliteitsscore wordt bepaald door een aantal factoren, zoals de hoeveelheid inhoud die wordt weergegeven voor de specifieke gebruiker, die wordt bepaald door de machtigingen van de gebruiker, aangezien op elke onderwerppagina beveiligingssnijding is geplaatst voor ai-gegenereerde inhoud. De kwaliteitsscore die wordt weergegeven op het tabblad Voorgestelde onderwerpen is een gemiddelde van elke afzonderlijke score voor gebruikers.

### <a name="impressions"></a>Weergaven

In <b>de</b> kolom Weergaven wordt het aantal keren weergegeven dat een onderwerp is weergegeven aan eindgebruikers. Dit omvat weergaven via onderwerpkaarten in zoekopdrachten, door middel van onderwerppunten en via weergaven in het onderwerpcentrum. De doorklik op deze onderwerpen wordt niet weergegeven, maar het onderwerp is wel weergegeven. De kolom Weergaven wordt weergegeven voor onderwerpen op de tabbladen Voorgesteld, Bevestigd, Gepubliceerd en Verwijderd op de pagina Onderwerpen beheren.


## <a name="confirmed-topics"></a>Bevestigd onderwerpen

Op de pagina Onderwerpen beheren worden onderwerpen weergegeven die zijn gevonden in de opgegeven SharePoint-bronlocaties en die zijn bevestigd door een knowledge manager of  'crowd-sourced' die door twee of meer personen is bevestigd via het feedbackmechanisme voor kaarten, weergegeven op het tabblad Bevestigd. Indien nodig kan een gebruiker met machtigingen voor het beheren van onderwerpen bevestigd onderwerpen bekijken en ervoor kiezen deze te weigeren.

Een bevestigd onderwerp controleren:

1. Selecteer op **het tabblad** Bevestigd het onderwerp om de onderwerppagina te openen.</br>

2. Bekijk de onderwerppagina op de onderwerppagina en selecteer **Bewerken** als u wijzigingen aan de pagina wilt aanbrengen.

Houd er rekening mee dat u er nog steeds voor kunt kiezen om een bevestigd onderwerp te weigeren.  Ga hiervoor naar het geselecteerde onderwerp in de lijst Bevestigd en selecteer de **x** als u het onderwerp wilt weigeren.

## <a name="published-topics"></a>Gepubliceerde onderwerpen
Gepubliceerde onderwerpen zijn bewerkt, zodat specifieke informatie altijd wordt weergegeven voor iedereen die de pagina tegenkomt. Handmatig gemaakte onderwerpen worden hier ook weergegeven.

   ![Onderwerpen beheren](../media/knowledge-management/manage-topics-new.png) </br>