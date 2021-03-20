---
title: 'Microsoft Viva Topics topic discovery and curation  '
description: Overzicht van de manier waarop onderwerpen worden ontdekt.
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
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: 2f4c726849d438738f3c0d432daab53ee27b19ea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917426"
---
# <a name="microsoft-viva-topics-discovery-and-curation"></a>Microsoft Viva Onderwerpen ontdekken en cureren 

Viva Topics organiseert informatie voor kennis in uw Microsoft 365-omgeving. We hebben allemaal ervaring met het lezen van documenten en sitepagina's waar we termen tegenkomen die we niet kennen. Vaak stoppen we met wat we doen om kostbare tijd te besteden aan het zoeken naar meer informatie.

Viva Topics gebruikt Microsoft Graph en AI om onderwerpen **in** uw organisatie te identificeren.  Een onderwerp is een woordgroep of term die een specifieke betekenis heeft voor de organisatie en die resources heeft die mensen kunnen helpen te begrijpen wat het is en meer informatie over het onderwerp te vinden. Er is een groot aantal verschillende soorten onderwerpen dat belangrijk is voor je organisatie. In eerste instantie kunnen de volgende typen onderwerpen worden geïdentificeerd:
- Project
- Gebeurtenis
- Organisatie
- Locatie
- Product
- Creatief werk
- Onderzoeksgebied

AI identificeert personen en inhoud die zijn verbonden met het onderwerp en als er genoeg wordt gevonden, wordt het een voorgesteld onderwerp. Het ziet ernaar uit om de volgende eigenschappen te identificeren en weer te geven op een **pagina Onderwerp:**
- Alternatieve namen en/of acroniems.
- Een korte beschrijving van het onderwerp.
- Personen die mogelijk wat van het onderwerp afweten.
- Bestanden, pagina's en sites die aan het onderwerp zijn gerelateerd.

De eigenschappen worden geïdentificeerd op basis van de bestanden en pagina's die deel uitmaken van het bewijs voor het identificeren van het onderwerp. Alternatieve namen en acroniems worden afkomstig uit deze bestanden en pagina's. De korte beschrijving is afkomstig van deze bestanden en pagina's of van internet via Wikipedia. Naast de voorgestelde eigenschappen wordt verwezen naar het bronbestand, de pagina of het Wikipedia-artikel. Personen worden voorgesteld op basis van hun actieve bijdragen (bijvoorbeeld bewerkingen) aan de bestanden en pagina's. Een verwijzing naar het bedrag van de bijdragen van een bepaalde persoon geeft een hint waarom de persoon is geïdentificeerd. Bestanden, pagina's en sites worden gerangschikt op basis van of ze centraal staan in het onderwerp, of ze nu een overzicht of inleiding tot het onderwerp kunnen geven. 

Niet elk geïdentificeerd onderwerp is nuttig voor uw organisatie. Het kan zijn dat er geen van de juiste alternatieve namen, beschrijvingen, de juiste personen of inhoud zijn geïdentificeerd. De mogelijkheid om onderwerpen toe te voegen die niet zijn geïdentificeerd, voorgestelde onderwerpen te behouden en onderwerpen te curaçeren, is dus essentieel voor het verbeteren van de kwaliteit van de onderwerpen die in uw organisatie kunnen worden gevonden.

Als de context geschikt is, worden deze onderwerpen vervolgens gemarkeerd op alle moderne SharePoint-sitepagina's in uw tenant. Een paginaauteur kan ook rechtstreeks naar het onderwerp op de moderne SharePoint-sitepagina verwijzen. Wanneer een gebruiker nieuwsgierig is naar meer informatie over een onderwerp, kan deze het gemarkeerde onderwerp selecteren om een overzichtskaart onderwerp weer te geven met een korte beschrijving.  En als ze meer willen weten, kunnen ze een koppeling **Onderwerpdetails** selecteren in de samenvatting om de gedetailleerde onderwerppagina te openen.

![Belangrijke kenmerken van Topics](../media/knowledge-management/saturn.png) </br>

Daarnaast kunnen gebruikers ook onderwerpen vinden via Microsoft Search.

## <a name="topic-curation-and-feedback"></a>Onderwerp curatie en feedback

Viva Topics is blij met de menselijke bijdrage om de kwaliteit van uw onderwerpen te verbeteren. Hoewel AI in eerste instantie onderwerpen identificeert en suggereert, zijn handmatig wijzigingen aangebracht in inhoud van inzenders, handmatig toegevoegde onderwerpen, bevestiging van gebruikers voor door AI ontdekte eigenschappen en inhoud en feedback over het nut van onderwerpen essentieel.

- Onderwerpen kunnen worden beoordeeld door **kennisbeheerders** in uw organisatie. De knowledge manager kan onderwerpen bekijken die hij of zij mag zien. Op de pagina Onderwerpen beheren in het Onderwerpcentrum kunnen ze ervoor kiezen om door AI gegenereerde onderwerpen ('voorgestelde onderwerpen') als geldig te bevestigen, onderwerpen te weigeren om te voorkomen dat de inhoud wordt bekeken als een onderwerp, onderwerpen te maken die niet zijn ontdekt door AI, of onderwerpen te identificeren die nuttiger of nauwkeuriger kunnen zijn bij enkele bewerkingen door deskundigen. Zie Onderwerpen beheren [in het onderwerpcentrum voor meer informatie.](manage-topics.md)

- U kunt *machtigingen voor het* maken en bewerken van onderwerpen toewijzen aan uw gelicentieerde gebruikers, zodat ze wijzigingen kunnen aanbrengen in bestaande onderwerpen of nieuwe onderwerpen kunnen maken. Hierdoor kunnen gebruikers met kennis van zaken over het onderwerp de onderwerppagina rechtstreeks bijwerken om correcties aan te brengen of aanvullende informatie toe te voegen. Ze kunnen ook nieuwe onderwerpen toevoegen die AI niet heeft kunnen identificeren. Als er voldoende informatie is over deze handmatig toegevoegde onderwerpen en AI dit type onderwerp kan identificeren, kunnen aanvullende suggesties van AI deze handmatig toegevoegde onderwerpen verbeteren. Samen kunnen mensen en AI kennis nauwkeurig houden in de tijd en deze rust niet op één persoon hebben. Zie Een nieuw onderwerp [maken en](./create-a-topic.md) Een onderwerp bewerken voor [meer informatie.](./edit-a-topic.md)

- Zelfs gebruikers die alleen toegang hebben tot onderwerp (onderwerpkijkers) worden gevraagd het nut van specifieke onderwerpen te controleren. Feedbackvragen worden gesteld op de **overzichtskaart Onderwerp** om de waarde van het onderwerp en de informatie te verbeteren. Vragen over de kwaliteit en het nut van de AI-suggesties worden een voor een aan gebruikers gepresenteerd. Vragen zijn:</br>

    1. Of het identificeren van het onderwerp op de SharePoint-pagina nuttig was. Er is een mogelijkheid om de markering te verwijderen als deze niet nauwkeurig of nuttig is. Als voldoende personen aangeven dat een onderwerp niet correct is geïdentificeerd op een bepaalde pagina, wordt deze markering uiteindelijk verwijderd voor alle gebruikers. 

    2. Of het voorgestelde onderwerp waardevol is voor de organisatie. Als voldoende personen aangeven dat het voorgestelde onderwerp waardevol is, wordt het onderwerp automatisch bevestigd. Als het voorgestelde onderwerp niet waardevol is, wordt het onderwerp ook automatisch geweigerd. Knowledge Manager kan deze activiteit waarnemen in de weergave Onderwerpen beheren.

    3. Of de personen en resourcesuggesties nuttig zijn.

    4. Op de startpagina onderwerpcentrum ziet u de onderwerpen in uw organisatie waarmee u verbinding hebt. U kunt ervoor kiezen om vermeld te blijven in het onderwerp of uzelf te verwijderen. Deze feedback wordt weergegeven voor iedereen die dit onderwerp ontdekt. Zie [Het overzicht van het onderwerpcentrum](./topic-center-overview.md) voor meer informatie op de startpagina van het onderwerpcentrum.

Zelfs bij menselijke bewerkingen zal AI voortdurend op zoek gaan naar meer informatie over onderwerpen en wordt er naar menselijke verificatie ge zoeken. Als AI bijvoorbeeld denkt dat u een persoon bent die moet worden vermeld als een expert in een onderwerp, wordt u gevraagd dit te bevestigen. 


## <a name="see-also"></a>Zie ook