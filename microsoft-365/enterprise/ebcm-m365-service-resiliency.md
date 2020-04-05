---
title: Weerbaarheid Microsoft 365-service
author: chrfox
f1.keywords:
- NOCSH
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Beschrijving van het onderwerp weerbaarheid
ms.openlocfilehash: 8cda7a861b6ea646ed9606674e26aaca551d1024
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42810958"
---
# <a name="built-in-resiliency"></a>Ingebouwde weerbaarheid

Als provider van de Cloud-samenwerking, heeft Microsoft ontdekt dat het belangrijk is om continu aan de vertrouwensrelatie te blijven werken door oplossingen te bieden die consistent functioneren en waar uw gebruikers iets aan hebben. Als een bepaalde service niet beschikbaar is, heet dit downtime. De definitie van downtime varieert voor elke Microsoft 365-service, maar het gaat meestal om een willekeurige periode waarin gebruikers de essentiële functionaliteit van de service niet kunnen gebruiken. Dit is bijvoorbeeld de definitie van downtime voor SharePoint Online, afkomstig uit de serviceovereenkomst van Microsoft 365:

**"Downtime voor SharePoint Online**: Elke periode waarin gebruikers een deel van de SharePoint Online-siteverzameling, waarvoor ze de juiste machtigingen hebben, niet kunnen lezen of schrijven."

U vindt de definities voor downtime voor elke service in de [Serviceovereenkomsten](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37).

Om geplande of onverwachte downtime te voorkomen, ligt de focus bij het ontwerpen van Microsoft 365-services op vier gebieden, die ervoor zorgen dat ze optimaal beschikbaar en bestand tegen storingen zijn, namelijk:

## <a name="activeactive-design"></a>Actief/actief ontwerp

In Microsoft 365 streven we ernaar alle services te ontwerpen en te exploiteren in een actief/actief ontwerp dat de weerbaarheid vergroot. Dit betekent dat er altijd meerdere exemplaren van een service draaien, die op gebruikersaanvragen kunnen reageren, en dat deze worden gehost in geografisch verspreide datacenters. Alle gebruiksverkeer komt binnen via de Microsoft Front Door-service en wordt automatisch doorgestuurd naar het meest optimaal gesitueerde exemplaar van de service, om zo eventuele servicefouten te voorkomen en impact op onze klanten te verminderen.

## <a name="reduce-incident-scope"></a>Impact van incidenten verminderen

De impact van een service-incident wordt gemeten aan de hand van de ernst, hoe lang het duurt en hoeveel klanten er worden beïnvloed. We streven ernaar om de impact van alle incidenten te beperken door:

- meerdere exemplaren van elke service afgescheiden van elkaar in te zetten
- het implementeren van updates op een gecontroleerde, geleidelijke manier met gefaseerde validatie, zodat eventuele problemen met de update zo snel mogelijk kunnen worden ontdekt en opgelost tijdens het implementatieproces. Zo kan de update indien nodig worden teruggeroepen en wordt deze eerst doorgevoerd bij een kleine groep binnen Microsoft (binnenste ring), waarna deze wordt geïmplementeerd in grotere groepen, zoals alle 140.000 Microsoft-werknemers (ring 2), vervolgens bij de early adopters (ring 3) en uiteindelijk bij alle klanten wereldwijd (ring 4).
- verbeteringen in de bewaking door automatisering. Microsoft 365 is zeer groot en de doelstelling voor uptime in de SLA is hoog. Aan het begin was het zo dat er niet snel genoeg gereageerd kon worden om aan de SLA te voldoen als er mensen nodig waren voor het ontdekken en reageren op een service-incident. Automatisering is de sleutel tot het snel en effectief opsporen en oplossen van service-incidenten. Hoe eerder we iets ontdekken, hoe sneller het opgelost kan worden.

In combinatie met de actief/actief-mogelijkheden die zijn ingebouwd in de Microsoft 365-servicearchitectuur, beperken deze activiteiten de ernst, duur en het aantal betrokken klanten gedurende een service-incident.  

## <a name="fault-isolation"></a>Foutisolatie

Net als het feit dat de services zijn ontworpen en worden gebruikt op een actief/actief-manier en van elkaar worden gescheiden om te voorkomen dat een storing in de ene invloed heeft op de ander, is de codebasis van de service ook gebaseerd op een vergelijkbaar afscheidingsprincipe genaamd foutisolatie. Foutisolatiemaatregelen vormen een gefaseerde bescherming binnen de codebasis zelf. Met deze maatregelen wordt voorkomen dat een probleem op één punt een domino-effect heeft op andere delen van de service.
Foutisolatiemaatregelen worden toegepast in verschillende stadia van de ontwikkeling en levering van een service, zoals tijdens de ontwikkeling van de code, service-implementatie, taakverdeling en databasereplicatie.

De Microsoft Security Development Lifecycle (SDL) bevordert de weerbaarheid nog verder en bestaat uit een reeks procedures die ondersteuning biedt voor beveiligings- en nalevingsvereisten. SDL begeleidt onze ontwikkelaars bij het bouwen van robuuste, veilige en betrouwbare services. De belangrijkste elementen van SDL bestaan uit evaluatie van de code, bedreigingsmodellering en gestandaardiseerde processen voor het reageren op incidenten in de Microsoft Cloud.

M365-Services zijn zeer onderling verbonden, maar de systemen en technologie die erachter staan, worden zo ontworpen dat de effecten van een service-incident worden beperkt. Zo zal een probleem dat optreedt in Exchange Online bijvoorbeeld niet van invloed zijn op de kernfunctionaliteit van Teams, en kan een probleem met de zoekfunctionaliteit in SharePoint Online niet van invloed zijn op het uploaden of downloaden van bestanden door gebruikers.

## <a name="continuous-service-improvement"></a>Continue serviceverbetering

Wanneer er een probleem optreedt, nemen we dit serieus. Onze redundante Cloud-architectuur en de rigoureuze interne processen zijn er per slot van rekening om te voorkomen dat onze services ontoegankelijk worden. In het geval van een incident worden de betrokken services snel gedetecteerd door onze bewaking. Indien uw tenant hierdoor wordt getroffen, wordt u hier onmiddellijk middels een verscheidenheid aan kanalen van op de hoogte gebracht. Tegelijkertijd volgen de engineers zorgvuldig opgestelde procedures om het probleem in kaart te brengen en de nodige stappen te zetten om de normale werking zo snel mogelijk te herstellen. Zodra de service weer normaal functioneert, voeren we reviews uit als onderdeel van de cyclus van voortdurende serviceverbetering. Tijdens zo‘n review wordt de onderliggende oorzaak van het incident geïdentificeerd en wordt besproken wat er nodig was om het probleem op te lossen. Vervolgens zetten we alles wat we geleerd hebben van de situatie op een rijtje en passen we dit toe op het ontwerp en de uitvoering van al onze services. Zo voorkomen we dat dezelfde hoofdoorzaak gevolgen heeft voor andere services en klanten.
