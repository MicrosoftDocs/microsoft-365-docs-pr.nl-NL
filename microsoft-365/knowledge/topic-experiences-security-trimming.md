---
title: Beveiligingsknippen voor Microsoft Viva-onderwerpen
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
description: Overzicht van de manier waarop beveiliging wordt gebruikt om onderwerpen weer te geven.
ms.openlocfilehash: 12a2ad34c55cd63468266abca1fa053048053dd2
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279330"
---
# <a name="microsoft-viva-topics-security-trimming"></a>Beveiligingsknippen voor Microsoft Viva-onderwerpen 

Gebruikers van Viva-onderwerpen kunnen geen informatie bekijken in onderwerpen die hun bestaande Office 365-machtigingen niet kunnen zien. Alles wat een gebruiker op een onderwerppagina ziet (bijvoorbeeld SharePoint-sites, documenten en bestanden), is informatie die hij of zij al mag zien. Viva-onderwerpen brengen geen wijzigingen aan in bestaande machtigingen.

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a>Waarom twee gebruikers mogelijk verschillende weergaven van hetzelfde onderwerp hebben

Wanneer een onderwerp wordt gemaakt via AI of handmatige curation, kan het een beschrijving bevatten van het onderwerp, alternatieve namen, personen die aan het onderwerp zijn gekoppeld, evenals sites, pagina's en bestanden met betrekking tot het onderwerp. Wanneer deze informatie wordt weergegeven op een onderwerppagina, is het mogelijk dat twee gebruikers die hetzelfde onderwerp bekijken, dezelfde informatie niet zien.
  
Wanneer Gebruiker 1 bijvoorbeeld de onderwerppagina Van Nieuw bekijkt, kan deze weergave van de onderwerppagina worden weergegeven.

![Toegangsonderwerp voor gebruiker 1](../media/knowledge-management/user2-topic-view.png) </br> 

Wanneer Gebruiker 2 echter naar dezelfde Pagina van het Onderwerp kijkt, verschilt de weergave van Gebruiker 1.  Gebruiker 2 kan het bestand *DG-2000* Product  overview zien in de sectie Vastgemaakte bestanden en pagina's van de onderwerppagina, die niet wordt weergegeven voor Gebruiker 1. 

![Het onderwerp Van 365 voor gebruiker 2](../media/knowledge-management/user1-topic-view.png) </br> 

Het verschil met wat gebruikers over hetzelfde onderwerp kunnen zien, is dat gebruikers mogelijk niet over de office 365-machtigingen voor het weergeven van een gerelateerde site of een gerelateerd bestand zijn.  Viva-onderwerpen respecteert de machtigingen die zijn ingesteld voor items in een onderwerp en kunnen de toegang tot deze items niet wijzigen. In ons voorbeeld kan Gebruiker 1 het bestand *DG-2000 Product Overview* niet weergeven op de onderwerppagina voor Deze omdat Gebruiker 1 geen Office 365-machtigingen heeft om het bestand te bekijken.

Als een gebruiker niet voldoende informatie in een onderwerp kan zien om het nuttig te maken, is het onderwerp niet beschikbaar voor de gebruiker. Wanneer dit gebeurt, ziet de gebruiker het gemarkeerde onderwerp niet. Een andere gebruiker die over machtigingen beschikt om meer informatie hierover te lezen, kan het onderwerp bekijken.


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>Onderwerpmachtigingen voor kennisbeheerders en onderwerpbijdragers

Gebruikers aan wie een machtiging is toegewezen om onderwerpen te beheren (knowledge managers) kunnen alleen informatie bekijken die ze over machtigingen voor het bekijken van onderwerpen hebben.

Op dezelfde manier kunnen gebruikers die onderwerpmachtigingen (onderwerpbijdragen) hebben, alleen informatie bekijken die ze over machtigingen voor weergave in onderwerpen hebben. 


## <a name="ai-versus-manually-curated-topic-information"></a>AI versus handmatig curated topic information

Onderwerpen kunnen informatie bevatten die wordt gegenereerd door AI en informatie die is toegevoegd of bewerkt door onderwerpbijdragers of knowledge managers.

 - De informatie in een onderwerp dat door AI is toegevoegd, is alleen zichtbaar voor personen die toegang hebben tot de broninhoud.
 - Informatie over onderwerpbeschrijvingen en personen die handmatig zijn toegevoegd of bewerkt door een onderwerpbijdrager of Knowledge Manager, is zichtbaar voor iedereen die het onderwerp kan zien.
 - Bestanden, pagina's en sites zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud, ongeacht of ze handmatig zijn toegevoegd of toegevoegd door AI.

In de volgende tabel wordt beschreven wat gebruikers , onderwerpbekijkers, medewerkers en kennismanagers, in een bepaald onderwerp kunnen zien op basis van hun machtigingen.

|Onderwerpitem|Wat gebruikers kunnen zien|
|:---------|:------------------|
|Onderwerpnaam|Gebruikers kunnen de onderwerpnaam van alle onderwerpen in het onderwerpcentrum zien. Sommige onderwerpen zijn mogelijk niet zichtbaar als ze een lage relevantie voor de gebruiker hebben.|
|Onderwerpbeschrijving|Door AI gegenereerde beschrijvingen zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud. Handmatig ingevoerde of bewerkte beschrijvingen zijn zichtbaar voor alle gebruikers.|
|Personen|Vastgemaakte personen zijn zichtbaar voor alle gebruikers. Voorgestelde personen zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.|
|Bestanden|Bestanden zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.|
|Pagina's|Pagina's zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.|
|Sites|Sites zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.|




## <a name="see-also"></a>Zie ook

