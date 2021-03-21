---
title: Beveiliging van Microsoft Viva-onderwerpen
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
ms.openlocfilehash: a7146592edb356b4d46a5a178b5754dc0de6a7c0
ms.sourcegitcommit: 30c3054004ddc9d6059c11d55577552aa2464810
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/20/2021
ms.locfileid: "50939621"
---
# <a name="microsoft-viva-topics-security-trimming"></a>Beveiliging van Microsoft Viva-onderwerpen 

Gebruikers van Viva-onderwerpen kunnen geen informatie weergeven in onderwerpen die door hun bestaande Office 365-machtigingen niet kunnen worden bekeken. Alles wat een gebruiker ziet op een onderwerppagina (bijvoorbeeld SharePoint-sites, documenten, bestanden) zijn gegevens die ze al mogen zien. Viva-onderwerpen brengen geen wijzigingen aan in bestaande machtigingen.

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a>Waarom twee gebruikers verschillende weergaven van hetzelfde onderwerp hebben

Wanneer een onderwerp wordt gemaakt via AI of handmatige curatie, kan het een beschrijving bevatten van het onderwerp, alternatieve namen, personen die aan het onderwerp zijn gekoppeld, evenals sites, pagina's en bestanden met betrekking tot het onderwerp. Wanneer deze informatie wordt weergegeven op een onderwerppagina, is het mogelijk dat twee gebruikers die hetzelfde onderwerp bekijken, dezelfde informatie niet zien.
  
Als gebruiker 1 bijvoorbeeld de onderwerppagina van Den Oudsten bekijkt, kunnen ze deze weergave van de onderwerppagina zien.

![Onderwerp Van Den Oudsten voor gebruiker 1](../media/knowledge-management/user2-topic-view.png) </br> 

Wanneer gebruiker 2 echter naar dezelfde onderwerppagina van Neptunus kijkt, verschilt de weergave van gebruiker 1.  Gebruiker 2 kan het *BESTAND PRODUCToverzicht VAN DG-2000* zien in de sectie Vastgemaakte bestanden en pagina's van de onderwerppagina, die niet wordt weergegeven voor gebruiker 1.  

![Onderwerp Van Den Oudsten voor gebruiker 2](../media/knowledge-management/user1-topic-view.png) </br> 

Het verschil in wat gebruikers over hetzelfde onderwerp kunnen zien, is omdat gebruikers mogelijk niet de machtigingen van Office 365 hebben om een gerelateerde site of bestand te bekijken.  Viva-onderwerpen respecteert de machtigingen die zijn ingesteld voor items in een onderwerp en kunnen de toegang tot items niet wijzigen. In ons voorbeeld kan gebruiker 1 het *BESTAND DG-2000 Productoverzicht* niet weergeven op de onderwerppagina voor Neptunus, omdat gebruiker 1 geen Office 365-machtigingen heeft om het bestand te bekijken.

Als een gebruiker onvoldoende informatie in een onderwerp kan zien om het nuttig te maken, is het onderwerp niet beschikbaar voor de gebruiker. Wanneer dit gebeurt, ziet de gebruiker het gemarkeerde onderwerp niet. Een andere gebruiker die machtigingen heeft voor meer informatie in het onderwerp, kan het onderwerp zien.


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a>Onderwerpmachtigingen voor kennismanagers en onderwerpcontribuanten

Gebruikers aan wie machtigingen zijn toegewezen voor het beheren van onderwerpen - kennisbeheerders - kunnen alleen informatie bekijken die ze in onderwerpen kunnen zien.

Op dezelfde manier kunnen gebruikers die onderwerpmachtigingen ( onderwerpcontribuanten) hebben, alleen informatie bekijken die ze in onderwerpen kunnen zien. 


## <a name="ai-versus-manually-curated-topic-information"></a>AI versus handmatig samengestelde onderwerpgegevens

Onderwerpen kunnen informatie bevatten die wordt gegenereerd door AI en informatie die is toegevoegd of bewerkt door onderwerpcontribuanten of kennisbeheerders.

 - Informatie in een onderwerp dat door AI is toegevoegd, is alleen zichtbaar voor personen die toegang hebben tot de broninhoud.
 - Onderwerpbeschrijving en personengegevens die handmatig zijn toegevoegd of bewerkt door een inzender of kennisbeheerder van het onderwerp, zijn zichtbaar voor iedereen die het onderwerp kan zien.
 - Bestanden, pagina's en sites zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud, ongeacht of ze handmatig zijn toegevoegd of toegevoegd door AI.

In de volgende tabel wordt beschreven wat gebruikers - kijkers van onderwerpen, medewerkers en kennisbeheerders - kunnen zien in een bepaald onderwerp op basis van hun machtigingen.

|Onderwerpitem|Wat gebruikers kunnen zien|
|:---------|:------------------|
|Onderwerpnaam|Gebruikers kunnen de onderwerpnaam van onderwerpen zien in het onderwerpcentrum. Sommige onderwerpen zijn mogelijk niet zichtbaar als gebruikers geen machtigingen voor de broninhoud hebben of een lage relevantie voor de gebruiker hebben.|
|Beschrijving van onderwerp|Door AI gegenereerde beschrijvingen zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud. Handmatig ingevoerde of bewerkte beschrijvingen zijn zichtbaar voor alle gebruikers.|
|Personen|Vastgemaakte personen zijn zichtbaar voor alle gebruikers. Voorgestelde personen zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.|
|Bestanden|Bestanden zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.|
|Pagina's|Pagina's zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.|
|Sites|Sites zijn alleen zichtbaar voor gebruikers die machtigingen hebben voor de broninhoud.|




## <a name="see-also"></a>Zie ook

