---
title: Onderwerp Ervaar beveiligingsbeperkingen (preview)
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Overzicht van de manier waarop beveiliging wordt gebruikt om onderwerpen weer te geven.
ms.openlocfilehash: 7e503082494d27f9418b8e09b8d20d01e4708fe9
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698864"
---
# <a name="topic-experiences-security-trimming-preview"></a>Onderwerp Ervaar beveiligingsbeperkingen (preview)

> [!Note] 
> De inhoud in dit artikel is bedoeld voor project cortex private preview. [Meer informatie over Project Cortex](https://aka.ms/projectcortex).

Met behulp van een onderwerp kunnen gebruikers niet informatie weergeven in onderwerpen die hun bestaande Office 365-machtigingen niet kunnen zien. Alles wat een gebruiker op een onderwerp ziet (zoals SharePoint-sites,-documenten en-bestanden), is informatie die ze al mogen zien. De onderwerp-ervaringen maken geen wijzigingen in bestaande machtigingen.

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a>Waarom twee gebruikers verschillende weergaven van hetzelfde onderwerp kunnen hebben

Wanneer u een onderwerp maakt met AI of handmatige curator, kan dit een beschrijving van het onderwerp, alternatieve namen, personen die zijn gekoppeld aan het onderwerp, bevatten, en sites, pagina's en bestanden die betrekking hebben op het onderwerp. Wanneer deze informatie op een onderwerpenpagina wordt weergegeven, is het mogelijk dat twee gebruikers die hetzelfde onderwerp bekijken, niet dezelfde informatie zien.
  
Wanneer user 1 bijvoorbeeld de Neptune-topic bevat, is dit wat ze kunnen zien.

![Neptune onderwerp voor gebruiker 1](../media/knowledge-management/user2-topic-view.png) </br> 

Wanneer op de site van User 2 echter dezelfde Neptune-topic wordt weergegeven, verschilt de weergave van gebruiker 1.  Gebruiker 2 kan het bestand *DG-2000-product overzicht* weergeven in de sectie **vastgemaakte bestanden en pagina's** van de onderwerpenpagina, die niet voor gebruiker 1 wordt weergegeven. 

![Neptune onderwerp voor gebruiker 2](../media/knowledge-management/user1-topic-view.png) </br> 

Het verschil in wat gebruikers in hetzelfde onderwerp kunnen zien, is omdat gebruikers mogelijk niet beschikken over de machtigingen van Office 365 voor het weergeven van een gerelateerde site of een bestand.  Met onderwerpen wordt rekening gehouden met de machtigingen die zijn ingesteld voor items in een onderwerp en kan de toegang niet worden gewijzigd. In ons voorbeeld is gebruiker 1 het bestand *DG-2000 product Overview* niet weergegeven in de onderwerppagina voor Neptune omdat gebruikers 1 geen Office 365-machtigingen hebben voor het weergeven van het bestand.

Als een gebruiker niet voldoende informatie in een onderwerp kan zien, zodat het onderwerp nuttig kan zijn, is het onderwerp niet beschikbaar voor de gebruiker. In dit voorbeeld wordt de gebruiker het gemarkeerde onderwerp niet weergegeven. Een andere gebruiker die in het onderwerp is gemachtigd om meer informatie in het onderwerp te gebruiken, kan het onderwerp dan ook zien.


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>Machtigingen voor het onderwerp van kennis beheerders en medewerkers van een onderwerp

Gebruikers die zijn toegewezen aan de onderwerpen over het beheren van onderwerpen-Knowledge managers-kunnen alleen informatie weergeven die ze hebben, en kunnen de inhoud van de onderwerpen bekijken.

Ook gebruikers die machtigingen voor het onderwerp hebben gemaakt en bewerken-met het onderwerp medewerkers van een onderwerp kunnen alleen informatie weergeven die ze hebben gemachtigd om binnen de onderwerpen te zien. 


## <a name="ai-versus-manually-curated-topic-information"></a>AI versus handmatig gecuratore informatie over het onderwerp

De onderwerpen kunnen gegevens bevatten die worden gegenereerd door de AI-en informatie die zijn toegevoegd of bewerkt door medewerkers of kennis beheerders van het onderwerp.

 - Informatie in een onderwerp dat door AI is toegevoegd, is alleen zichtbaar voor personen die toegang hebben tot de broninhoud.
 - Gegevens die handmatig zijn toegevoegd of bewerkt door een onderwerpassistent of Knowledge Manager, zijn zichtbaar voor iedereen die het onderwerp kan zien.

In de volgende tabel wordt beschreven welke gebruikers van een onderwerp, medewerkers en kennis managers van de gebruikers, kunnen zien in een bepaald onderwerp op basis van hun machtigingen.

|Onderwerp|Wat gebruikers kunnen zien|
|:---------|:------------------|
|Naam onderwerp|Gebruikers kunnen de naam van het onderwerp van alle onderwerpen in het onderwerp centrum zien. Sommige onderwerpen zijn mogelijk niet zichtbaar als ze een lage relevantie voor de gebruiker hebben.|
|Beschrijving onderwerp|Met AI gegenereerde beschrijvingen zijn alleen zichtbaar voor gebruikers die zijn gemachtigd voor de broninhoud. Handmatig ingevoerde of bewerkte beschrijvingen zijn zichtbaar voor alle gebruikers.|
|Personen|Vastgemaakte personen zijn zichtbaar voor alle gebruikers. Voorgestelde personen zijn alleen zichtbaar voor gebruikers die zijn gemachtigd voor de broninhoud.|
|Bestanden|Bestanden zijn alleen zichtbaar voor gebruikers die zijn gemachtigd voor de broninhoud.|
|Pagina's|Pagina's zijn alleen zichtbaar voor gebruikers die zijn gemachtigd voor de broninhoud.|
|Sites|Sites zijn alleen zichtbaar voor gebruikers die zijn gemachtigd voor de broninhoud.|




## <a name="see-also"></a>Zie ook

