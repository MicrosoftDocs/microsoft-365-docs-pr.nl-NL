---
title: Onderwerpen op schaal beheren in Microsoft Viva-onderwerpen
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: lauriellis
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
description: Meer informatie over best practices voor het beheren van de vele onderwerpen in uw organisatie met Behulp van Viva-onderwerpen.
ms.openlocfilehash: dd9fe658d4f698ac50563b5c9ea141a090f6141d
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538409"
---
# <a name="manage-topics-at-scale-in-microsoft-viva-topics"></a>Onderwerpen op schaal beheren in Microsoft Viva-onderwerpen

Wanneer u uw sites SharePoint of uw hele organisatie indexeert voor Viva-onderwerpen, kunnen er veel onderwerpen worden gegenereerd. Wanneer dit gebeurt en u duizenden  voorgestelde onderwerpen ziet op de pagina Onderwerpen beheren, kan het lastig zijn om te weten waar u moet beginnen. In dit artikel wordt beschreven hoe Viva Topics u helpt bij het optimaliseren van de onderwerpen en informatie die worden weergegeven aan gebruikers die informatie zoeken, zelfs in grote organisaties met grote aantallen onderwerpen.

Eerst een herinnering aan de [vier stadia voor onderwerpen:](manage-topics.md#topic-stages)

- **Voorgesteld:** een onderwerp is geïdentificeerd door AI en heeft voldoende ondersteunende bronnen, verbindingen en eigenschappen. (Deze zijn gemarkeerd als een **voorgesteld onderwerp** in de gebruikersinterface.)

- **Bevestigd:** een onderwerp dat door AI is voorgesteld, wordt gevalideerd. Onderwerpvalidatie moet worden bevestigd door een kennismanager. Als u een onderwerp wilt bevestigen, moet er een netto van twee positieve stemmen zijn ontvangen van gebruikers die hebben gestemd met behulp van het feedbackmechanisme op de onderwerpkaart. Als bijvoorbeeld één gebruiker positief heeft gestemd en één gebruiker negatief heeft gestemd voor een bepaald onderwerp, hebt u nog twee positieve stemmen nodig om het onderwerp te bevestigen.
 
- **Gepubliceerd:** Een bevestigd onderwerp dat is samengesteld: er zijn handmatige wijzigingen aangebracht om de kwaliteit te verbeteren.

- **Verwijderd:** een onderwerp wordt geweigerd door een knowledge manager en is niet meer zichtbaar voor kijkers. Een onderwerp kan in elke staat worden verwijderd (voorgesteld, bevestigd of gepubliceerd). Als u een onderwerp wilt verwijderen, moet er een netto van twee negatieve stemmen zijn ontvangen van gebruikers die hebben gestemd met behulp van de feedbackmechanismen op de onderwerpkaart. Als bijvoorbeeld één gebruiker negatief heeft gestemd en één gebruiker positief heeft gestemd voor een bepaald onderwerp, moet u nog twee negatieve stemmen voor het onderwerp verwijderen. Wanneer een gepubliceerd onderwerp wordt verwijderd, moet de pagina met de samengestelde details handmatig worden verwijderd via de paginabibliotheek van het onderwerpcentrum.

## <a name="knowledge-manager-role"></a>Rol van Knowledge Manager 

Wanneer u Viva-onderwerpen configureert, voegt u een groep gebruikers  toe die machtigingen krijgen om de ervaring Onderwerpen beheren in het onderwerpcentrum te zien. Deze wordt alleen weergegeven voor deze gebruikers die de rol van primaire curatie voor de onderwerpen hebben. Ze hebben toegang tot gegevens over de onderwerpen en kunnen lijsten zien met alle onderwerpen die ze kunnen bekijken en curateren.

Werknemers in deze rol moeten uitgebreide machtigingen hebben om een breed scala aan onderwerpen weer te geven. Of als machtigingen zijn gesegmenteerd, wilt u mogelijk een groep gebruikers selecteren die verschillende gebieden van het bedrijf vertegenwoordigen en kunnen curaten voor hun eigen gebieden.

Wanneer u onderwerpen voor het eerst bekijkt in het onderwerpcentrum, zijn voorgestelde onderwerpen puur AI-gedefinieerd. Kennisbeheerders willen ze misschien allemaal bekijken voordat ze Viva-onderwerpen uitrollen naar een brede gebruikersgemeenschap. Wanneer u op schaal werkt, is deze benadering zelden praktisch vanwege de duizenden onderwerpen.

De aanbevolen methode is om een balans te vinden tussen de meest relevante of belangrijke onderwerpen voor uw eerste set gebruikers en de focus te leggen op de curatie van deze onderwerpen voordat Viva-onderwerpen worden uitgerold. Begin feedback te verzamelen van de gebruikers en sta crowdsourcing toe om het gebruik en de bijdragenpatronen van uw gebruikers te bepalen om de strategieën te informeren die in dit artikel worden voorgesteld.

Het is belangrijk om te herkennen dat het systeem alle gebruikers zowel door AI voorgestelde als door mensen samengestelde gepubliceerde onderwerpen identificeert en laat zien. Dit betekent echter niet dat elk voorgesteld onderwerp wordt weergegeven voor alle eindgebruikers. In de beveiligingsinstellingen worden alleen de onderwerpen weer gegeven die elke werknemer kan openen op basis van de machtigingen die zijn ingesteld op de inhoud zelf.

Als kennismanager met machtigingen  voor het weergeven van de pagina Onderwerpen beheren, wordt mogelijk een veel groter aantal onderwerpen weergegeven vanwege uw eigen verhoogde machtigingen, afhankelijk van uw rol in de organisatie en het toegangsniveau. U hebt ook toegang tot weergaven waarmee u onderwerpen op één locatie kunt zien in plaats van ze te openen met behulp van highlights of zoeken.

Daarnaast is er waarschijnlijk een kleiner percentage onderwerpen dat door de meeste gebruikers wordt bekeken en een grotere set meer onderwerpen die veel minder vaak worden gezien vanwege machtigingen. Het is daarom goed om alle curatietaken eerst te richten op de onderwerpen die het belangrijkst zijn voor uw organisatie en die het meest waarschijnlijk breder worden gezien.

In dit artikel worden enkele strategieën voor curatie beschreven. Deze strategieën kunnen betekenen dat de minder vaak voorkomende of minder veelvoorkomende onderwerpen mogelijk niet volledig worden samengesteld door kennisbeheerders. Deze voorgestelde onderwerpen blijven echter nuttig en kunnen een persoon inzicht of een aanwijzer geven, waardoor een werknemer uren kan besparen om naar een beginpunt te zoeken. Het toestaan van crowdsourced-updates voor onderwerpen is gunstig en biedt meer inhoud en dekking voor de minder algemene onderwerpen.

In dit artikel vindt u enkele richtlijnen en best practices voor het benaderen van onderwerpbeheer en curatie.

## <a name="understanding-suggested-topics"></a>Voorgestelde onderwerpen begrijpen

Wanneer onderwerpen worden ontdekt door AI, worden ze gemarkeerd  als een voorgesteld onderwerp **,** zowel op de pagina Onderwerpen beheren als in de onderwerpkaarten die aan gebruikers worden gepresenteerd. Elk onderwerp dat niet is gemarkeerd als verwijderd, wordt weergegeven aan gebruikers, waaronder bevestigd, gepubliceerd en voorgestelde onderwerpen. Onderwerpen in alle drie de staten zijn beschikbaar voor eindgebruikers.

Op een onderwerpkaart of pagina gebruiken we verschillende aanwijzingen om aan te geven hoe de AI de informatie heeft gegenereerd. Het systeem gebruikt diverse gegevens om de resources toe te voegen, voornamelijk via de inhoud zelf.

- Labels geven aan dat er een onderwerp wordt voorgesteld en dat het is ontdekt door Viva Topics.  

   ![Voorbeeldkaart met een voorgesteld onderwerp en bevat voorgestelde personen en voorgestelde bronnen.](../media/knowledge-management/scale-topics-sample-card-suggested-topic.png)

- Informatie op de kaart geeft aan waar een definitie vandaan komt door de bron op te geven.

- Voorgestelde personen worden afgeleid door personen die documenten hebben geschreven of bewerkt te aggregeren met bewijs over het onderwerp. Als een persoon een document schrijft met een onderwerpnaam in de titel en dat document veel weergaven heeft, is er mogelijk slechts één document nodig om de persoon vast te stellen als verwant. In veel gevallen is er echter meer bewijs beter en hebben personen die worden vermeld, aan meerdere documenten gewerkt.  

   ![Pagina met een voorgesteld onderwerp en suggesties voor personen, bestanden en pagina's.](../media/knowledge-management/scale-topics-sample-page-suggested-topic.png)

- Voor de weergegeven bestanden en pagina's geeft het systeem aan hoe vaak het onderwerp in het document is vermeld, maar het onderwerp moet ook worden vermeld in een specifieke context waarin de verwijzing naar het onderwerp van specifiek type (zoals project of team) wordt aangegeven. Dit is wat telt als bewijs voor de AI. In het systeem wordt ook rekening houden met het voorkomen van een onderwerpnaam in de titels van documenten, typen documenten en andere analysefuncties (zoals weergaven).

   ![Afbeelding van een banner met de tekst Voorgesteld onderwerp en Microsoft Viva heeft dit onderwerp ontdekt.](../media/knowledge-management/scale-topics-suggested-you-have-access.png)

   ![Afbeelding van een banner met de tekst Voorgesteld onderwerp en Deze pagina bewerken om uw betrokkenheid bij dit onderwerp te beschrijven.](../media/knowledge-management/scale-topics-suggested-describe-your-involvement.png)

   ![Afbeelding van een banner met de tekst Voorgesteld onderwerp en Deze pagina bewerken als u personen aan het onderwerp kunt toevoegen.](../media/knowledge-management/scale-topics-suggested-add-people.png)

Deze kenmerken tonen aan dat de inhoud is toegevoegd door AI en hoe de AI deze bepaling heeft gemaakt.

### <a name="communication"></a>Communicatie

Wanneer u met uw gebruikers over Viva-onderwerpen communiceert, is het belangrijk om het verschil te verduidelijken tussen AI-voorgestelde onderwerpen en inhoud en hun samengestelde equivalenten.

Als lezer moet u voorgestelde onderwerpen met een kritischer oog bekijken. Ze moeten niet worden gezien als gezaghebbende bronnen van organisatie-waarheid. Ze zijn eerder een hulpmiddel voor het vinden van wegwijsheid om toegang te krijgen tot stilzwijgende kennis die wordt gepresenteerd via de inhoud tot wie u toegang hebt. De AI heeft het onderwerp ontdekt en heeft voldoende bewijs om het aan u weer te geven, maar de waarde ervan is niet bevestigd door een persoon.

### <a name="crowdsourced-controls"></a>Crowdsourced-besturingselementen

Voorgestelde onderwerpen kunnen worden verbeterd door de pagina te cureren en door middel van crowdsourced feedback over het onderwerp.

Wanneer gebruikers werken met een voorgesteld onderwerp, wordt ze mogelijk een eenvoudige vraag gesteld in de gebruikersinterface. Bijvoorbeeld: *Was dit onderwerp relevant voor de pagina?* *Is deze persoon relevant voor het onderwerp?* *Was deze definitie nauwkeurig?* Door de feedback voor dergelijke vragen te gebruiken, kan de nauwkeurigheid van de onderwerpen toenemen zonder dat een benoemde persoon de pagina hoeft te curaçeren.

De startpagina van een onderwerpcentrum is een andere locatie waar feedback over voorgestelde onderwerpen wordt verzameld. In het onderwerpcentrum kan een gebruiker de onderwerpen zien die aan hem of haar zijn gekoppeld en de optie krijgen om deze associatie te bevestigen of deze te laten verwijderen.

   ![Voorbeeld van het onderwerpcentrum met voorgestelde onderwerpen voor de gebruiker om de verbinding met voorgestelde onderwerpen te bevestigen of te verwijderen.](../media/knowledge-management/scale-topics-topic-center-confirm-connections.png)

Wanneer u brede crowdsourcing van onderwerpen toestaat, moet u rekening houden met de volgende factoren:

-   Gebruikers zien de optie **Bewerken** op onderwerppagina's en kunnen de pagina's in dezelfde ervaring bewerken als andere moderne SharePoint pagina's.

-   Sommige **webonderdelen voorgesteld** onderwerp kunnen niet worden verwijderd. De onderwerpnaam, alternatieve namen, definitie, voorgestelde personen en voorgestelde bronnen kunnen niet worden verwijderd.

-   Het kan enige tijd duren voor een voorgesteld of bevestigd onderwerp  dat is gepubliceerd, wordt verplaatst naar de lijst Gepubliceerd op de **pagina Onderwerpen** beheren.

    -   De geschatte tijd dat een onderwerp wordt weergegeven in zoekopdrachten, highlights, hashtags of aantekeningen, is 2 uur.

    -   De geschatte tijd voor een onderwerp  **in** de lijst Gepubliceerd op de pagina Beheerde onderwerpen is in de meeste gevallen niet meer dan 24 uur. U moet ze binnen 2 uur zien, maar omdat er elke 24 uur een volledige synchronisatie is, mag het wachten niet langer dan 24 uur duren.

-   Het is mogelijk dat een gebruiker een gepubliceerd onderwerp in een uitgecheckte of bewerkingstoestand achter laat. Een kennisbeheerder kan deze zien in de paginabibliotheek van het onderwerpcentrum en kan de wijzigingen van de gebruiker negeren om het onderwerp opnieuw te publiceren of contact opnemen met die gebruiker om te vragen of hij of zij het onderwerp wil inchecken.

### <a name="topic-visibility-and-content-is-based-on-a-users-permissions"></a>Zichtbaarheid en inhoud van onderwerp is gebaseerd op machtigingen van een gebruiker

Wanneer u de lijst met voorgestelde onderwerpen als knowledge manager bekijkt, moet u er rekening mee houden dat de inhoud van een voorgesteld onderwerp dynamisch wordt gebaseerd op machtigingen. De voorgestelde inhoud en personen die aan u worden weergegeven, zijn mogelijk niet hetzelfde als personen die worden gepresenteerd aan een gebruiker of een andere knowledge manager.

Op basis van de machtigingen voor het weergeven van inhoud die is gekoppeld aan een onderwerp, kan elke gebruiker een andere set voorgestelde resources, personen, alternatieve namen en definitie zien.

## <a name="prioritize-the-topics-for-curation"></a>Prioriteit geven aan de onderwerpen voor curatie

U kunt de volgende strategieën gebruiken om onderwerpen te identificeren die waarschijnlijk prominent aanwezig zijn en daarom goede kandidaten voor curatie zijn. 

### <a name="taxonomies"></a>Taxonomie

Het gebruik van bestaande taxonomie kan een lijst met onderwerpen bevatten die waarschijnlijk prominent zijn voor gebruikers. Dit kunnen bijvoorbeeld de volgende zijn:

-   Producten en services die uw organisatie levert

-   Teams in uw organisatie

-   High-profile projecten

Deze benadering kan ook worden gebruikt op afdelings- of functioneel niveau, met deskundigen die dit gebied van uw organisatie begrijpen. Het is niet de bedoeling dat ze een selectie of alle onderwerpen bekijken. In plaats van dat ze hun eigen domeinkennis meenemen om selectieve curatie te begeleiden.

### <a name="search"></a>Zoeken

Veelgebruikte zoektermen worden vaak als onderwerpen gevonden. Met behulp van [de belangrijkste queryrapporten in Microsoft Search](/sharepoint/view-search-usage-reports)kunt u de meest voorkomende zoektermen in uw organisatie identificeren. Als er onderwerpen zijn gevonden voor deze voorwaarden, zijn ze goede kandidaten voor curatie. Deze onderwerpen kunnen worden gepresenteerd als antwoordkaarten in Microsoft Search.

Als u momenteel Microsoft [Search-bladwijzers gebruikt,](/microsoftsearch/manage-bookmarks)kunt u overwegen welke van deze bladwijzers kunnen worden vervangen door een onderwerp. Een bladwijzerantwoordkaart bevat een titel, beschrijving en URL. In sommige gevallen kan een onderwerpkaart nuttiger zijn voor een gebruiker, en een onderwerpkaart bevat ook resources en personen.

In de zoekervaring van de gebruiker, wanneer een gebruiker zoekt naar een term zoals *reizen,* worden zoekresultaten weergegeven in de volgende prioriteitsvolgorde in Microsoft Search:

1.  Gepubliceerde of bevestigde onderwerpen

2.  Bladwijzers

3.  Voorgestelde onderwerpen

### <a name="impressions-and-quality-score"></a>Weergaven en kwaliteitsscore

Het [aantal](manage-topics.md#impressions) weergaven en [de kwaliteitsscore](manage-topics.md#quality-score) zijn belangrijke meetwaarden voor het begrijpen van het gedrag van een onderwerp. De waarde van deze metrische gegevens wordt beperkt wanneer alleen kennismanagers of IT-teams toegang hebben tot onderwerpen. Door onderwerpen aan een testgroep gebruikers bloot te stellen, worden representatievere gegevens voor deze metingen gegenereerd.

Onderwerpen met een hoog aantal vertoningen worden waarschijnlijk vaker gebruikt. De kwaliteitsscore voor deze onderwerpen geeft een idee van hoe rijk deze onderwerpen zijn. Onderwerpen met een hoog aantal vertoningen en een lage kwaliteitsscore zijn goede doelen voor curatie.

### <a name="key-terms-from-the-information-architecture-of-larger-organizational-sites"></a>Belangrijke termen uit de informatiearchitectuur van grotere organisatiesites

Grotere portalsites binnen uw organisatie hebben mogelijk tijd geïnvesteerd in het organiseren van hun informatiearchitectuur en het navigeren van hun site rond belangrijke onderwerpgebieden voor hun bedrijfseenheden, productlijnen, belangrijke projecten, en meer. Als u deze termen bekijkt en onderwerpen voor deze termen identificeert en cureert, kunnen gebruikers die op zoek zijn naar informatie over deze gebieden, worden geholpen.

### <a name="leverage-internal-knowledge-bases-or-wiki-sites"></a>Interne kennisbases of wikisites gebruiken

Als uw organisatie heeft geïnvesteerd in kennisbases of wikisites, kunnen deze een lijst met onderwerpen bieden die u kunt gebruiken voor uw eerste curatie-inspanningen. Als ze bijzonder groot zijn, selecteert u de meest bekeken of bewerkte onderwerpen als uitgangspunt.

## <a name="see-also"></a>Zie ook

[Onderwerpen beheren in het onderwerpcentrum](manage-topics.md)

[Overzicht van het onderwerpcentrum](topic-center-overview.md)
