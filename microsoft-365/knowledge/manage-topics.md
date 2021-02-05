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
- m365initiative-topics
localization_priority: None
ms.openlocfilehash: 45e8f26823998278f9a332d2ea1e362b77f2032b
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107184"
---
# <a name="manage-topics-in-the-topic-center"></a>Onderwerpen beheren in het Onderwerpcentrum 

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


In het Onderwerpcentrum Viva-onderwerpen kan  een Knowledge Manager de pagina Onderwerpen beheren bekijken om onderwerpen te bekijken die zijn geïdentificeerd in SharePoint-bronlocaties, zoals opgegeven door uw kennisbeheerder.  

   ![Onderwerpcentrum](../media/knowledge-management/topic-center.png) </br> 



Kennisbeheerders helpen bij het begeleiden van gevonden onderwerpen in de levenscyclus van onderwerpen:

- Voorgesteld: Een onderwerp is geïdentificeerd door AI en heeft voldoende ondersteunende bronnen, verbindingen en eigenschappen.
- Bevestigd: er wordt een onderwerp gevalideerd dat door AI is voorgesteld. Validatie wordt uitgevoerd door bevestiging van een Knowledge Manager. Bovendien kan een onderwerp worden bevestigd als ten minste twee gebruikers positieve feedback geven via de feedbackvraag op de onderwerpkaart.
- Gepubliceerd: Een bevestigd onderwerp dat is samengesteld: handmatige wijzigingen zijn aangebracht om de kwaliteit te verbeteren.
- Verwijderd: Een onderwerp wordt geweigerd door een Knowledge Manager en is niet meer zichtbaar voor gebruikers. Het onderwerp kan in elke staat zijn wanneer het wordt verwijderd (voorgesteld, bevestigd of gepubliceerd). Wanneer een gepubliceerd onderwerp wordt verwijderd, moet de pagina met de details handmatig worden verwijderd via de paginabibliotheek van het onderwerpcentrum.

   ![Grafiek Levenscyclus van onderwerp](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> Op de pagina Onderwerpen beheren kan elke Knowledge Manager alleen onderwerpen zien waar ze toegang hebben tot de bestanden en pagina's van het onderwerp. Dit wordt weergegeven in de onderwerpen die worden weergegeven op de tabbladen Voorgesteld, Bevestigd, Verwijderd en Gepubliceerd. Het aantal onderwerpen wordt echter wel bij de totale tellingen in de organisatie geteld.

## <a name="requirements"></a>Vereisten

Als u onderwerpen wilt beheren in het onderwerpcentrum, moet u:
- U hebt een licentie voor Viva-onderwerpen.

- De machtiging [**Wie kan onderwerpen beheren?**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions) Knowledge admins can give users this permission in the Viva Topics topic permissions settings. 

U kunt de pagina Onderwerpen beheren niet weergeven in het Onderwerpcentrum, tenzij u de machtiging **Wie kan onderwerpen** beheren hebt.

In het onderwerpcentrum kan een Knowledge Manager onderwerpen bekijken die zijn geïdentificeerd in de SharePoint-bronlocaties die u hebt opgegeven en deze bevestigen of weigeren. Een Knowledge Manager kan ook nieuwe onderwerppagina's maken en publiceren als deze niet zijn gevonden in onderwerpdetectie, of bestaande pagina's bewerken als deze moeten worden bijgewerkt.


## <a name="review-suggested-topics"></a>Voorgestelde onderwerpen bekijken

Op de pagina Onderwerpen beheren in het onderwerpcentrum worden onderwerpen weergegeven die zijn gevonden in de opgegeven SharePoint-bronlocaties op het **tabblad Voorgesteld.** Indien nodig kan een Knowledge Manager niet-bevestigd onderwerpen bekijken en ervoor kiezen om deze te bevestigen of te weigeren.

   ![Voorgestelde onderwerpen](../media/knowledge-management/quality-score.png) </br> 

Een voorgesteld onderwerp bekijken:

1. Selecteer op **de pagina Onderwerpen** beheren het tabblad **Aanbevolen** en selecteer het onderwerp om de onderwerppagina te openen.</br>

2. Bekijk de onderwerppagina op de onderwerppagina en selecteer **Bewerken** als u wijzigingen wilt aanbrengen op de pagina. Als u wijzigingen publiceert, wordt dit onderwerp verplaatst naar **het tabblad** Gepubliceerd.

3. Ga na het lezen van het onderwerp terug naar de pagina Onderwerpen beheren. Voor het geselecteerde onderwerp kunt u het volgende doen:

   - Selecteer het vinkje om het onderwerp te bevestigen.
    
   - Selecteer de **x** als u het onderwerp wilt weigeren.

    Bevestigd onderwerpen worden verwijderd uit de lijst **Voorgesteld** en worden nu weergegeven in de **lijst** Bevestigd.

    Geweigerde onderwerpen worden verwijderd uit de **lijst Voorgesteld** en worden nu weergegeven op het **tabblad** Verwijderd.

   </br> 

### <a name="quality-score"></a>Kwaliteitsscore

Aan elk onderwerp dat wordt weergegeven op de pagina Voorgestelde onderwerpen is een <b>kwaliteitsscore</b> toegewezen. De kwaliteitsscore is een weerspiegeling van de hoeveelheid informatie die de gemiddelde gebruiker ziet voor de informatie over het onderwerp. Houd er rekening mee dat elke gebruiker mogelijk meer of minder informatie ziet vanwege de machtigingen die hij of zij niet heeft voor de informatie in een onderwerp. 

De kwaliteitsscore kan bijdragen aan het geven van inzicht in de onderwerpen met de meeste informatie en kan handig zijn voor het vinden van onderwerpen die mogelijk handmatig moeten worden bewerkt.  Een onderwerp met een lagere kwaliteitsscore kan bijvoorbeeld het resultaat zijn van sommige gebruikers die geen SharePoint-machtigingen hebben voor relevante bestanden of sites die AI in het onderwerp heeft opgenomen. Een medewerker kan vervolgens het onderwerp bewerken om de informatie op te nemen (indien van toepassing), die vervolgens kan worden bekeken voor alle gebruikers die het onderwerp kunnen bekijken.

De kwaliteitsscore kan variëren van 1 tot 100. Een nieuw gevonden onderwerp heeft een kwaliteitsscore van 0 totdat twee of meer gebruikers het hebben bekeken. De kwaliteitsscore van elke gebruiker wordt bepaald door een aantal factoren, zoals de hoeveelheid inhoud die voor de specifieke gebruiker wordt weergegeven. Deze wordt bepaald door de machtigingen van de gebruiker, omdat op elke onderwerppagina beveiligingsbeveiliging is ingeschakeld voor AI-gegenereerde inhoud. De kwaliteitsscore op het tabblad Voorgestelde onderwerpen is een gemiddelde van elke afzonderlijke score van elke gebruiker.

### <a name="impressions"></a>Nen

In de kolom <b>Met</b> de kolom Wordt weergegeven hoe vaak een onderwerp aan eindgebruikers is getoond. Dit geldt ook voor weergaven via onderwerpkaarten in de zoekfunctie, door de belangrijkste punten van een onderwerp en via de weergaven van het onderwerpcentrum. De klik-through over deze onderwerpen wordt niet weergegeven, maar het onderwerp wordt wel weergegeven. De kolom Wordt weergegeven voor onderwerpen op de tabbladen Voorgesteld, Bevestigd, Gepubliceerd en Verwijderd op de pagina Onderwerpen beheren.


## <a name="confirmed-topics"></a>Bevestigd onderwerpen

Op de pagina Onderwerpen beheren worden onderwerpen die zijn gevonden in de opgegeven SharePoint-bronlocaties en die zijn bevestigd door een Knowledge Manager of 'crowd-sourced' die door twee of meer personen is bevestigd via het feedbackmechanisme voor kaarten, weergegeven op het tabblad Bevestigd.  Indien nodig kan een gebruiker met machtigingen voor het beheren van onderwerpen de bevestigd onderwerpen beoordelen en ervoor kiezen om deze te weigeren.

Een bevestigd onderwerp bekijken:

1. Selecteer op **het tabblad Bevestigd** het onderwerp om de onderwerppagina te openen.</br>

2. Bekijk de onderwerppagina op de onderwerppagina en selecteer **Bewerken** als u wijzigingen wilt aanbrengen op de pagina.

U kunt een bevestigd onderwerp toch weigeren.  U doet dit door naar het geselecteerde onderwerp in de lijst Bevestigd te gaan en de **x** te selecteren als u het onderwerp wilt weigeren.

## <a name="published-topics"></a>Gepubliceerde onderwerpen
Gepubliceerde onderwerpen zijn bewerkt, zodat specifieke informatie altijd wordt weergegeven voor de persoon die de pagina tegenkomt. Hier worden ook handmatig gemaakte onderwerpen vermeld.

   ![Onderwerpen beheren](../media/knowledge-management/manage-topics-new.png) </br> 




