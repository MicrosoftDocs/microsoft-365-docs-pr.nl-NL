---
title: Microsoft 365 Tenantisolatie in de Microsoft-Graph en Delve
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In dit artikel vindt u een uitleg over hoe Microsoft 365 tenantisolatie werkt in de Office Graph en in Delve.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 966f02726a2cce18e30e4d5bc7ab0beb5db51a29
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332386"
---
# <a name="microsoft-365-tenant-isolation-in-the-microsoft-graph-and-delve"></a>Microsoft 365 Tenantisolatie in de Microsoft-Graph en Delve

## <a name="tenant-isolation-in-the-microsoft-graph"></a>Tenantisolatie in de Microsoft-Graph

De [Microsoft Graph](https://developer.microsoft.com/graph) modellen activiteiten in Microsoft 365-services, waaronder Exchange Online, SharePoint Online, Yammer, Skype voor Bedrijven, Azure Active Directory en meer, en in externe services, zoals andere Microsoft-services- of services van derden. Microsoft Graph onderdelen worden overal Microsoft 365. De Microsoft-Graph vertegenwoordigt een verzameling inhoud en activiteit en de relaties tussen de inhoudssuites die in de Office worden. Het maakt gebruik van geavanceerde technieken voor machine learning om mensen te verbinden met de relevante inhoud, gesprekken en personen om hen heen. De tenantindex in SharePoint Online heeft bijvoorbeeld een Microsoft Graph-index die wordt gebruikt voor het leveren van Delve-query's, de Analytics Processing Engine in SharePoint Online wordt gebruikt om signalen op te slaan en inzichten te berekenen, en Exchange Online berekent de cache van elke gebruiker als input in tenantanalyse.

De Microsoft Graph bevat informatie over ondernemingsobjecten, zoals personen en documenten, evenals de relaties en interacties tussen deze objecten. De relaties en interacties worden weergegeven als *randen.* De Microsoft-Graph wordt gesegmenteerd per tenant, zodat er alleen randen tussen knooppunten *in* dezelfde huurperiode kunnen bestaan. Een *knooppunt* is een entiteit met een URI (Uniform Resource Identifier), knooppunttype, lijst met toegangsbesturingselementen en een set facets met *metagegevens* en randen. Elk knooppunt heeft bijbehorende metagegevens en randen, gerangschikt in *facets,* zoals in het gemeenschappelijke kennismodel. *Metagegevens* zijn benoemde eigenschappen die zijn opgeslagen op een knooppunt dat kan worden gebruikt voor zoeken, filteren of analyseren in de Microsoft-Graph. Een *facet* is een logische verzameling metagegevens en randen op een knooppunt. In elk facet wordt één aspect van een knooppunt beschreven. 

De Microsoft Graph niet alle gegevens in één opslagplaats. in plaats van metagegevens en relaties op te slaat over gegevens die ergens anders wonen. De Microsoft Graph bestaat uit verschillende gegevensopslag- en verwerkingsonderdelen:

- De Tenant Graph Store biedt bulkopslag die is geoptimaliseerd voor efficiënte analyse.
- De cache met actieve inhoud biedt snelle willekeurige toegang tot actief knooppunt en randen om gebruikerservaringen te verbeteren.
- De invoerrouter waarschuwt onderdelen interne en externe wijzigingen in de tenantgrafiek.

Analyses binnen elke werkbelasting leiden inzichten af die relevant zijn voor de tenantberekeningen en ze naar de tenantgrafiek pushen. Tenantanalyse heeft redenen voor alle activiteiten in een huurperiode om inzicht te krijgen in gedragspatronen. U kunt bijvoorbeeld Exchange Online voor elke gebruiker de cache van de geadresseerde berekent met analyses die efficiënt over het postvak van elke gebruiker redeneren. Deze analyse per gebruiker produceert een set *recipientcacheranden* voor elke persoon, die op hun beurt naar de tenantgrafiek worden geduwd. Hierdoor blijft het grootste deel van de analyseverwerking zo dicht mogelijk bij de brongegevens.

## <a name="tenant-isolation-in-delve"></a>Tenantisolatie in Delve

Zoals eerder is vermeld, biedt microsoft Graph mogelijkheden om mensen te helpen bij het ontdekken en samenwerken aan huidige activiteiten in hun bedrijf, en biedt het een entiteitscentrisch platform voor analyse om te redeneren over inhoud en activiteit in alle werkbelastingen en daarbuiten Microsoft 365. Delve is de eerste ervaring die wordt mogelijk gemaakt door de Microsoft-Graph.
Delve is een Microsoft 365 webervaring die inhoud van Microsoft 365 en Yammer Enterprise naar Microsoft 365 gebruikers via de Microsoft-Graph. In de webervaring worden gegevens weergegeven als verschillende borden, elk met een bepaald onderwerp, zoals *Trending around me* of *Modified by me*. Elk bord bestaat uit verschillende documentkaarten met samenvattingstekst en een afbeelding uit het document. Met de kaart kunnen gebruikers dingen doen zoals het document openen of een Yammer pagina voor het document. Er is een pagina voor elke persoon in een Microsoft 365-tenant met de meest relevante documenten voor deze persoon en pictogrammen die Exchange Online of Skype voor Bedrijven kunnen aanroepen voor interactie met die persoon. Omdat Delve is gebaseerd op de Microsoft Graph API, is deze afhankelijk van de tenantisolatie van die API.