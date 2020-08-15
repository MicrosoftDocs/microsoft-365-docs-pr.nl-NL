---
title: Microsoft 365-Tenant isolatie in Microsoft Graph en Delve
ms.author: josephd
author: JoeDavies-MSFT
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
description: In dit artikel vindt u een beschrijving van de manier waarop Microsoft 365-Tenant isolatie werkt in Office Graph en Delve.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ab9b216656e076cc3ba02a4ef6c75b25b94547fe
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689281"
---
# <a name="microsoft-365-tenant-isolation-in-the-microsoft-graph-and-delve"></a>Microsoft 365-Tenant isolatie in Microsoft Graph en Delve

## <a name="tenant-isolation-in-the-microsoft-graph"></a>Tenant isolatie in Microsoft Graph

De activiteiten van [Microsoft Graph](https://developer.microsoft.com/graph) -modellen in microsoft 365-Services, waaronder Exchange Online, SharePoint Online, Yammer, Skype voor bedrijven, Azure Active Directory en meer, en in externe services, zoals andere Microsoft-services of services van derden. Microsoft Graph-onderdelen worden overal in Microsoft 365 gebruikt. De Microsoft Graph vertegenwoordigt een verzameling inhoud en activiteiten, en de relaties tussen de functies die in de volledige Office-Suite plaatsvinden. Het maakt gebruik van verfijnde Leer technieken voor machines om mensen te verbinden met de relevante inhoud, gesprekken en personen. De Tenant index in SharePoint Online heeft bijvoorbeeld een Microsoft Graph-index die wordt gebruikt voor het uitvoeren van Delve-query's, de analyse-engine in SharePoint Online wordt gebruikt voor het opslaan van signalen en het berekenen van inzichten, en Exchange Online berekent de cache voor geadresseerden van elke gebruiker als invoer in de Tenant analyses.

Microsoft Graph bevat informatie over Ondernemingsobjecten, zoals personen en documenten, evenals de relaties en interacties tussen deze objecten. De relaties en interacties worden als *randen*weergegeven. Microsoft Graph is gesegmenteerd door Tenant, zodat er geen randen kunnen bestaan tussen *knooppunten* in dezelfde pacht. Een *knooppunt* is een entiteit met een URI (Uniform Resource Identifier), knooppunttype, toegangsbeheerlijst en een set facetten met *metagegevens* en randen. Aan elk knooppunt zijn metagegevens en randen gekoppeld en zijn ze *ingedeeld als in* het gemeenschappelijke kennis model. *Metagegevens* hebben de naam eigenschappen die zijn opgeslagen op een knooppunt waarmee u kunt zoeken, filteren of analyseren in Microsoft Graph. Een *facet* is een logische verzameling metagegevens en randen op een knooppunt. Elke facet beschrijft een hoogte van een knooppunt. 

In Microsoft Graph worden niet alle gegevens naar één bibliotheek overgebracht. in plaats daarvan worden metagegevens en relaties opgeslagen over gegevens die elders liggen. Microsoft Graph bevat diverse onderdelen voor het opslaan en verwerken van gegevens:

- Het Tenant grafiek archief biedt bulkopslag geoptimaliseerd voor efficiënte analyses.
- De actieve inhouds cache biedt snel willekeurige toegang tot actieve knooppunten en randen om de gebruikerservaring te berijden.
- De invoer router waarschuwt interne en externe wijzigingen in de Tenant grafiek.

Analyse binnen elke werkbelasting de inzichten die relevant zijn voor de berekeningen van de Tenant en deze naar de Tenant grafiek te duwen. Tenant analyses redenen voor alle activiteit in een pacht om inzicht te krijgen in gedragspatronen. Met Exchange Online wordt bijvoorbeeld de cache voor de ontvanger berekend voor elke gebruiker met analyses die op een efficiënte manier overstapt op het postvak van een gebruiker. Met deze analyses per gebruiker wordt een set *RecipientCache-randen* weergegeven voor elke persoon die wordt gebruikt voor het aanduwen van de Tenant-grafiek. Zo kunt u de analytische verwerking zo veel mogelijk bijhouden.

## <a name="tenant-isolation-in-delve"></a>Tenant isolatie in Delve

Zoals eerder is vermeld, bieden de functies van Microsoft Graph een functie waarmee mensen de huidige activiteiten in hun onderneming kunnen ontdekken en hieraan kunnen samenwerken, en een entiteits gerichte platform voor analyses om te zorgen dat de inhoud en activiteiten in de werkstroom en buiten Microsoft 365. Delve is de eerste keer dat u Microsoft Graph uitvoert.
Delve is een Microsoft 365-webervaring waarmee inhoud van Microsoft 365 en Yammer Enterprise voor Microsoft 365-gebruikers via Microsoft Graph wordt geoppereerd. Met de webervaring worden gegevens weergegeven als verschillende borden, elk met een bepaald onderwerp, zoals een *trending rondom mij* of *door mij gewijzigd*. Elk bord bevat diverse document kaarten waarin de samenvattingstekst en een afbeelding uit het document worden weergegeven. Met de kaart kunnen gebruikers zoals het document of een Yammer-pagina voor het document openen. Er is een pagina voor elke persoon in een Microsoft 365-Tenant waarmee de meest relevante documenten voor deze persoon worden weergegeven en pictogrammen waarmee Exchange Online of Skype voor bedrijven kan worden aangeroepen voor interactie met die persoon. Aangezien Delve is gebaseerd op de Microsoft Graph-API, wordt dit gebonden aan de isolatie van de Tenant op basis van die API.