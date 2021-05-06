---
title: Zoekstatistieken in Advance eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Valideer uw zoekresultaten door de statistieken weer te geven die worden gegenereerd nadat u een verzamelingszoekactie hebt uitgevoerd in Advanced eDiscovery.
ms.openlocfilehash: 5b6cfdaffc7851a00035a4edcc9d490b229c455d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/05/2021
ms.locfileid: "52161650"
---
# <a name="search-statistics-in-advanced-ediscovery"></a>Zoekstatistieken in Advanced eDiscovery

Een van de manier waarop u uw zoekresultaten kunt valideren, is door de statistieken rond uw resultaten te bekijken om te controleren of deze aan uw verwachtingen voldoen. Wanneer een zoekopdracht is voltooid, worden statistieken op hoog niveau weergegeven in de flyout met zoekdetails:

- Aantal en het volume van de items die door de zoekopdracht zijn opgehaald

- Aantal en volume van gedeeltelijk geïndexeerde of niet-geïndexeerde items die zijn gevonden in de zoeklocaties

- Aantal gezochte postvakken en locaties.
Als u gedetailleerdere statistieken wilt bekijken, klikt u op 'Statistieken' in de flyout met zoekdetails.

## <a name="summary-view"></a>Overzichtsweergave

In de overzichtsweergave ziet u de zoekresultaten die zijn onderverdeeld op locatietype (bijvoorbeeld Exchange). Voor elk locatietype kunt u het volgende zien:

- Aantal locaties met items die overeenkomen met de zoekvoorwaarden

- Het aantal items van deze locaties dat aan de zoekvoorwaarden heeft voldaan

- Totale hoeveelheid items die overeenkomen met de zoekvoorwaarden.

## <a name="top-locations-view"></a>Weergave Toplocaties

In de weergave Toplocaties ziet u de afzonderlijke locaties met de meeste overeenkomsten. Voor elke locatie ziet u:

- Locatienaam (bijvoorbeeld SharePoint URL)

- Locatietype

- Aantal items dat aan de zoekvoorwaarden heeft voldaan

- Totale hoeveelheid items die overeenkomen met de zoekvoorwaarden.

## <a name="queries-view"></a>Query'sweergave

Als u trefwoord- of trefwoordrijen in de query hebt gebruikt (c:s), kunt u de uitsplitsing van de query zien in de weergave Query's per locatietype. Voor elk locatietype ziet u:

- Onderdeel: deze kolom heeft het woord 'Primair' of 'Trefwoord'. 'Primair' betekent dat de rij statistieken voor de hele query presenteert, terwijl 'Trefwoord' een van de queryonderdelen betekent.

- Query: het werkelijke queryonderdeel waar de rij naar verwijst. Als onderdeel 'Primair' is, is dit de hele query. als Onderdeel 'Trefwoord' was, ziet u hier een van de queryonderdelen.
  
  - Wanneer u alle inhoud in postvakken zoekt (door geen trefwoorden op te geven), is de werkelijke query (grootte >= 0) zodat alle items worden geretourneerd
  
  - Wanneer u op SharePoint Online en OneDrive voor Bedrijven sites, worden de twee volgende onderdelen toegevoegd:
    
    - NOT IsExternalContent:1 - sluit inhoud uit van een on-premises SharePoint organisatie
    
    - NOT isOneNotePage: 1 - sluit alle OneNote uit, omdat dit duplicaten zijn van elk document dat overeenkomt met de zoekquery.

- Aantal locaties met items die overeenkomen met de zoekvoorwaarden.

- Het aantal items van deze locaties dat aan de zoekvoorwaarden heeft voldaan.

- Totale hoeveelheid items die overeenkomen met de zoekvoorwaarden.
