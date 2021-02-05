---
title: 'Onderwerpdetectie en -curation voor Microsoft Viva-onderwerpen  '
description: Overzicht van de manier waarop onderwerpen worden gevonden.
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-topics
localization_priority: None
ms.openlocfilehash: 435544de1016552c6ce3d39c73f7127223f36331
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107706"
---
# <a name="microsoft-viva-topics-discovery-and-curation"></a>Discovery en curation over Microsoft Viva-onderwerpen 

In Viva-onderwerpen vindt u informatie over kennis in uw Microsoft 365-omgeving. We hebben allemaal ervaring met het lezen van documenten en sitepagina's, waar we termen tegenkomen die we niet bekend zijn. Vaak stoppen we met wat we doen om kostbare tijd te besteden aan het zoeken naar meer informatie.

Voor Viva-onderwerpen worden Microsoft Graph en AI gebruikt om **onderwerpen** in uw organisatie te identificeren.  Een onderwerp is een woordgroep of term die een specifieke betekenis heeft voor de organisatie en informatiebronnen die anderen kunnen helpen begrijpen wat het is en om meer informatie over het onderwerp te vinden. Er zijn veel verschillende soorten onderwerpen die belangrijk zijn voor uw organisatie. In eerste instantie kunt u de volgende typen onderwerpen identificeren:
- Project
- Gebeurtenis
- Organisatie
- Locatie
- Product
- Creatief werk
- Onderzoeksveld

AI identificeert personen en inhoud die aan het onderwerp zijn gekoppeld, en als er genoeg wordt ontdekt, wordt het een voorgesteld onderwerp. De volgende eigenschappen worden weergegeven op een **onderwerppagina:**
- Alternatieve namen en/of acroniemen.
- Een korte beschrijving van het onderwerp.
- Personen die mogelijk iets weten over het onderwerp.
- Bestanden, pagina's en sites die aan het onderwerp zijn gerelateerd.

De eigenschappen worden geïdentificeerd aan de bestanden en pagina's die deel uitmaken van het bewijs voor het identificeren van het onderwerp. Alternatieve namen en acroniemen zijn afkomstig van deze bestanden en pagina's. De korte beschrijving is afkomstig van deze bestanden en pagina's, of van internet via Wikipedia. Naast de voorgestelde eigenschappen wordt ook verwezen naar het bronbestand, de pagina of het Wikipedia-artikel. Personen worden voorgesteld op basis van hun actieve bijdragen aan de bestanden en pagina's (bijvoorbeeld bewerkingen). Een verwijzing naar het bedrag aan bijdragen van een bepaalde persoon geeft aan waarom de persoon is geïdentificeerd. Bestanden, pagina's en sites worden gerangschikt op basis van of ze van centraal tot het onderwerp zijn, of ze een overzicht of inleiding tot het onderwerp kunnen geven. 

Niet elk geïdentificeerd onderwerp is nuttig voor uw organisatie. Mogelijk zijn niet de juiste alternatieve namen, beschrijvingen, de juiste personen of inhoud geïdentificeerd. De mogelijkheid om onderwerpen toe te voegen die niet zijn geïdentificeerd, voorgestelde onderwerpen te behouden en onderwerpen te organiseren is essentieel voor het verbeteren van de kwaliteit van de onderwerpen die in uw organisatie kunnen worden gevonden.

In het geval van de context worden deze onderwerpen vervolgens op alle moderne SharePoint-sitepagina's in uw tenant gemarkeerd. Een auteur van een pagina kan ook rechtstreeks naar het onderwerp op de moderne SharePoint-sitepagina verwijzen. Wanneer een gebruiker meer wil weten over een onderwerp, kan  deze het gemarkeerde onderwerp selecteren om een onderwerpoverzichtskaart met een korte beschrijving weer te geven. En als ze meer willen weten, kunnen ze een koppeling **onderwerpdetails** in het overzicht selecteren om de gedetailleerde onderwerppagina te openen.

![Belangrijkste punten van het onderwerp](../media/knowledge-management/saturn.png) </br>

Daarnaast kunnen gebruikers ook onderwerpen vinden via Microsoft Search.

## <a name="topic-curation-and-feedback"></a>Onderwerp curation en feedback

Viva Topics verwelkomt een menselijke bijdrage om de kwaliteit van uw onderwerpen te verbeteren. Hoewel AI in eerste instantie onderwerpen identificeert en suggereert, zijn handmatig bewerkte inhoud van medewerkers, handmatig toegevoegde onderwerpen, bevestiging van gebruikers voor AI-eigenschappen en -inhoud, en feedback over de bruikbaarheid van onderwerpen essentieel.

- Onderwerpen kunnen worden gecontroleerd door **kennisbeheerders** in uw organisatie. De Knowledge Manager kan onderwerpen bekijken die hij of zij mag bekijken. Op de pagina Onderwerpen beheren in het Onderwerpcentrum kunnen ze kiezen voor het bevestigen van door AI gegenereerde onderwerpen ('voorgestelde onderwerpen') als geldig, het weigeren van onderwerpen om te voorkomen dat de inhoud wordt bekeken als een onderwerp, onderwerpen te maken die niet door DE AI zijn gevonden, of onderwerpen te identificeren die nuttiger of nauwkeuriger kunnen zijn door enkele bewerkingen door deskundigen. Zie Onderwerpen beheren [in het onderwerpcentrum voor meer informatie.](manage-topics.md)

- U kunt *machtigingen voor het maken* en bewerken van onderwerpen toewijzen aan al uw gebruikers met een licentie, zodat ze wijzigingen kunnen aanbrengen in bestaande onderwerpen of nieuwe onderwerpen kunnen maken. Hierdoor kunnen gebruikers met kennis van het onderwerp de onderwerppagina rechtstreeks bijwerken om correcties aan te brengen of aanvullende informatie toe te voegen. Ze kunnen ook nieuwe onderwerpen toevoegen die ai niet kon identificeren. Als er voldoende informatie beschikbaar is over deze handmatig toegevoegde onderwerpen en AI dit type onderwerp kan identificeren, kunnen aanvullende suggesties van AI deze handmatig toegevoegde onderwerpen verbeteren. Samen kunnen mensen en AI kennis in de tijd nauwkeurig houden en niet op één persoon rust. Zie Een nieuw onderwerp maken [en](https://docs.microsoft.com/microsoft-365/knowledge/create-a-topic) [een onderwerp bewerken voor meer informatie.](https://docs.microsoft.com/microsoft-365/knowledge/edit-a-topic)

- Zelfs gebruikers die alleen leestoegang hebben tot het onderwerp (onderwerpgebruikers) worden gevraagd de bruikbaarheid van specifieke onderwerpen te verifiëren. Er worden feedbackvragen gesteld op de **overzichtskaart** Onderwerp om de waarde van het onderwerp en de informatie te verbeteren. Vragen over de kwaliteit en bruikbaarheid van de AI-suggesties worden één voor één aan gebruikers gepresenteerd. Vragen zijn onder meer:</br>

    1. Of het identificeren van het onderwerp op de SharePoint-pagina nuttig was. U kunt de markering verwijderen als deze niet nauwkeurig of nuttig is. Als er voldoende personen zijn die aangeven dat een onderwerp op een bepaalde pagina niet correct is geïdentificeerd, wordt deze markering uiteindelijk voor alle gebruikers verwijderd. 

    2. Of het voorgestelde onderwerp waardevol is voor de organisatie. Als er voldoende personen aangeven dat het voorgestelde onderwerp waardevol is, wordt het onderwerp automatisch bevestigd. Als het voorgestelde onderwerp niet waardevol is, wordt het onderwerp automatisch geweigerd. Knowledge Manager kan deze activiteit zien in de weergave Onderwerpen beheren.

    3. Of de personen en resourcesuggesties nuttig zijn.

    4. Op de startpagina van het onderwerpcentrum ziet u de onderwerpen in uw organisatie waarmee u verbinding hebt. U kunt ervoor kiezen om bij het onderwerp te blijven of uzelf te verwijderen. Deze feedback is te zien aan iedereen die dit onderwerp aan het ontdekken is. Zie [het overzicht van het onderwerpcentrum](https://docs.microsoft.com/microsoft-365/knowledge/topic-center-overview) voor meer informatie op de startpagina van het onderwerpcentrum.

Zelfs bij menselijke bewerkingen zal AI voortdurend naar meer informatie over onderwerpen zoeken en zoeken naar menselijke verificatie. Als AI bijvoorbeeld denkt dat u een persoon bent die als expert op een onderwerp moet worden vermeld, wordt u gevraagd dit te bevestigen. 


## <a name="see-also"></a>Zie ook
