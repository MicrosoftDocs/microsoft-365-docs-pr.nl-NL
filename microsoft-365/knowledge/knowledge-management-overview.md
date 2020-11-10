---
title: Overzicht van kennisbeheer (preview)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Overzicht van de Knowledge Management in Project cortex.
ms.openlocfilehash: 27ce6457f2329ccaa4738d6868b4f2051c0c0a51
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988840"
---
# <a name="knowledge-management-overview-preview"></a>Overzicht van kennisbeheer (preview)

> [!Note] 
> De inhoud in dit artikel is bedoeld voor project cortex private preview. [Meer informatie over Project Cortex](https://aka.ms/projectcortex).

Knowledge Management gebruikt Microsoft AI-technologie, Microsoft 365, Delve, Search en andere onderdelen en services voor het maken van een kennis netwerk in uw Microsoft 365-omgeving. 

   ![Kennisbeheer stroom](../media/content-understanding/knowledge-management-flowchart.png) </br> 

Het is van doel om informatie te verstrekken aan gebruikers in apps die ze dagelijks gebruiken, zoals Outlook, teams en SharePoint.

Gebruikers zien bijvoorbeeld onbekende voorwaarden in hun e-mailberichten, SharePoint-sites of in team gesprekken waarover ze meer willen weten. Met de functie AI kunt u met AI automatisch zoeken naar en identificeren van deze onderwerpen, en informatie over deze **onderwerpen** samenstellen, zoals een korte beschrijving, onderhevige experts voor het onderwerp en sites, bestanden en pagina's die hieraan zijn gerelateerd. U kunt ervoor kiezen om de informatie over het onderwerp naar wens bij te werken. Vervolgens kunt u de beschikbare onderwerpen voor uw gebruikers maken, wat inhoudt voor elk exemplaar van het onderwerp dat wordt weergegeven in apps zoals Outlook, teams en SharePoint, wordt de tekst gemarkeerd. Gebruikers kunnen kiezen om het onderwerp te selecteren, waarover u meer wilt weten over de details van het onderwerp.


## <a name="topic-indexing"></a>Onderwerp indexeren

Knowledge Management gebruikt Microsoft AI-technologie om **onderwerpen** te identificeren in de Office 365-omgeving.

Een onderwerp is een woordgroep of term die in de organisatie belangrijk of belangrijk is. Deze heeft een specifieke betekenis van de organisatie en bevat bronnen die hieraan kunnen werken zodat ze meer informatie kunnen vinden.

Wanneer een onderwerp wordt geïdentificeerd, wordt er een **onderwerp** gemaakt met informatie die is verzameld via het indexeren van onderwerpen, zoals:

- Alternatieve namen en/of acroniemen.
- Een korte beschrijving van het onderwerp.
- Gebruikers die misschien informatie willen over het onderwerp.
- Bestanden, pagina's en sites die zijn gerelateerd aan het onderwerp.


## <a name="topic-discovery"></a>Onderwerp detecteren
Wanneer een onderwerp wordt genoemd in inhoud op SharePoint-nieuws en-pagina's, ziet u dat het is gemarkeerd. Open het onderwerp met een overzicht van de markering. Open het onderwerp Details van de titel van het overzicht. <!--(msg for Efren: not sure if I should use discovery for this; we use discovered in-product for indexing?)--> Het vermelde onderwerp kan automatisch worden geïdentificeerd of toegevoegd aan de pagina, met een directe verwijzing naar het onderwerp door de auteur van de pagina.

U kunt ook onderwerpen ontdekken via Microsoft Search.


## <a name="topic-management"></a>Onderwerp beheren

Het beheer van het onderwerp wordt uitgevoerd in het **onderwerp centrum** van uw organisatie. De site centrum site wordt tijdens de installatie gemaakt en fungeert als uw kennis punt voor uw organisatie. Het bevat een lijst met alle onderwerpen die zijn gevonden in uw omgeving, en alle topic pagina's die zijn gemaakt voor deze onderwerpen. 

Gebruikers die de juiste machtigingen hebben, kunnen het volgende doen in het onderwerp:

- Onderwerpen die zijn gevonden in de Tenant bevestigen of negeren.
- Maak handmatig nieuwe onderwerpen om zo nodig handmatig te maken (als u bijvoorbeeld niet voldoende informatie hebt opgegeven om te ontdekken via AI).
- Bestaande topic pagina's bewerken.</br>

Zie [werken met onderwerpen in het onderwerp centrum](work-with-topics.md) voor meer informatie.  


## <a name="admin-controls"></a>Beheerders besturingselementen

Met beheer besturingselementen in het Microsoft 365-Beheercentrum kunt u uw kennis netwerk beheren. Een Microsoft 365-beheerder of SharePoint-beheerder kan het volgende doen:

- Bepalen welke gebruikers in uw organisatie de functies van de clienttoepassingen of in zoekresultaten van SharePoint mogen zien.
- Bepalen welke SharePoint-sites worden verkend om naar onderwerpen te zoeken.
- U kunt zoeken naar specifieke voorwaarden uitsluiten die u niet wilt opnemen in een onderwerp.
- Bepalen welke gebruikers onderwerpen in het onderwerp centrum kunnen bevestigen of afwijzen.
- Bepalen welke gebruikers onderwerpen kunnen maken en bewerken in het onderwerp centrum.

Zie [uw kennis netwerk beheren](topic-experiences-discovery.md) voor meer informatie. 

## <a name="topic-curation--feedback"></a>Onderwerp & feedback

AI biedt voortdurend suggesties voor het verbeteren van uw onderwerpen wanneer er wijzigingen worden aangebracht in uw omgeving.

Gebruikers die u toegang wilt geven tot de onderwerpen op hun dagelijkse werk, kunnen suggesties doen om ze te verbeteren. Als een gebruiker bijvoorbeeld de onderwerpenpagina weergeeft en informatie ziet die niet klopt of die moet worden toegevoegd, kunt u de gegevens rechtstreeks bewerken via een koppeling op de onderwerpenpagina. Een ander voorbeeld: als een gebruiker een markering op een SharePoint-nieuwspagina bekijkt, vindt u vragen die aangeven of het gemarkeerd is voor uw organisatie. Met uw antwoord wordt bepaald wat er wordt weergegeven in de overzichts overzichten en de details van het onderwerp.

Daarnaast kunnen gebruikers met de juiste machtigingen items markeren zoals een Yammer-gesprek dat relevant is voor een onderwerp en ze aan een specifiek onderwerp toevoegen. <!--(msg for Efren: changed to Yammer, because we will not have shipped Teams yet)-->


## <a name="see-also"></a>Zie ook
[Kennisbeheer instellen](set-up-topic-experiences.md)</br>
[Overzicht van topic Center](topic-center-overview.md)
